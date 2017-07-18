---
layout: post
title:  "Playing Around With NGS"
date:   2015-03-12 
tag:
- Bioinformatics
category: blog
author: jamie
---

<p>Here I will walk you through how to take reads from a sequencer and assemble/map a genome and generate a VCF file + do some functional predictions. </p>

<h2 id="setup_2">
<a class="head_anchor" href="#setup_2" rel="nofollow"> </a>Set-up</h2>
<p>Install/download samtools (1.2), bwa, picard (sourceforge version), GATK + Java 7 (won’t work with other versions of Java) and SnpEFF You’ll need a computer that can run UNIX and about 50 GB of hard disk space (+ a fast internet connection makes things way better) </p>
<h2 id="getting-test-data_2">
<a class="head_anchor" href="#getting-test-data_2" rel="nofollow"> </a>Getting test data</h2>
<p>In terminal type <code class="prettyprint">"ftp ftp.broadinstitute.org"</code> (username:  gsapubftp-anonymous, password: your email); change directory (cd) to  <code class="prettyprint">/bundle/2.8/hg19</code> and download <code class="prettyprint">ucsc.hg19.fasta.gz</code> with the get command and uncompress the reference with the gunzip command. Then download <code class="prettyprint">dbsnp_138.hg19.vcf.gz</code> and it’s idx from the same location. </p>

<p>Repeat the above steps with <code class="prettyprint">ftp-trace.ncbi.nih.gov</code> (username: anonymous, password: your email); navigate to <code class="prettyprint">/giab/ftp/technical/garvan_data</code> and download all the .fastq files that don’t say “trimmed” e.g. <code class="prettyprint">"NIST7035_TAAGGCGA_L001_R1_001.fastq.gz"</code></p>
<h2 id="pair-end-sequence-assembly_2">
<a class="head_anchor" href="#pair-end-sequence-assembly_2" rel="nofollow"> </a>Pair end Sequence Assembly</h2>
<p>[Note - for running bwa and samtools  commands it might be necessary to be on the directory where bwa or samtools is located and use ./bwa or ./samtools] </p>

<p>The first thing we need to do in order to use bwa is construct an index for our reference genome. We do this by running the following command: <br>
<code class="prettyprint">bwa index -a bwtsw [reference.fasta]</code>. Once the reference index is built, sequence alignment indices of our fastq files need to be built, we do that with the following commands: <code class="prettyprint">bwa aln [reference.fasta] [short_pair_1.fastq] &gt; [short_pair_1.sai]</code> <code class="prettyprint">bwa aln [reference.fasta] [short_pair_2.fastq] &gt; [short_pair_2.sai]</code></p>

<p>We can now combine our reference index, the two alignment indices, and our two fastq files to create a single sequence alignment map<br>
<code class="prettyprint">bwa sampe [reference.fasta] [short_pair_1.sai] [short_pair_2.sai] [short_pair_1.fastq] [short_pair_2.fastq] &gt; [short_pair.sam]</code></p>

<p>Next we need to change “<em>” to “o” as a flag for unaligned reads, ajust mate pair info and add read headers, which can all be done with Picard using the following commands <code class="prettyprint">java -Xmx[memory]g -jar ValidateSamFile.jar I=[.bam or .sam]</code> This command should display MAPQ flag error, mate-pair error, and header error <code class="prettyprint">java -Xmx[memory]g -jar FixMateInformation.jar I=[.bam] O=[.bam] VALIDATION_STRINGENCY=LENIENT</code> <br>
<code class="prettyprint">java -Xmx[memory]g -jar ValidateSamFile.jar I=[fixed.bam] IGNORE=INVALID_MAPPING_QUALITY</code> Next we need to validate file accepting MAPQ flag “</em>” <code class="prettyprint">java -Xmx[memory]g -jar AddOrReplaceReadGroups.jar I=[.bam] O=[.bam] LB=anything PL=illumina PU=anything SM=anything</code>  </p>

<p>Next we need to re-sort the picard output and we’ll get as an output an unsorted bam file which has to be converted to binary and sorted using samtools.  To sort it we use the following commands: <code class="prettyprint">samtools view -bS -o [output.bam] [input.bam or .sam]</code> <code class="prettyprint">samtools sort [input.bam] [output.sorted.bam]</code></p>

<p>To view the bam file we use the command <code class="prettyprint">samtools tview file.bam</code> (if the file appears all white you can press n to see colors. You should see something like this: <br>
<a href="https://svbtleusercontent.com/z9jx6bvmh1ejbg.png" rel="nofollow"><img src="https://svbtleusercontent.com/z9jx6bvmh1ejbg_small.png" alt="Screen Shot 2015-02-11 at 4.08.05 PM.png"></a></p>
<h2 id="the-vcf-file_2">
<a class="head_anchor" href="#the-vcf-file_2" rel="nofollow"> </a>The VCF file</h2>
<p>A VCF file (Variant Call Format) is a text file containing information about the mutations in our genome. </p>

<p>The first thing we need to do is generate the VCF file, which on samtools 1.2 is generated using the following command: <code class="prettyprint">./samtools mpileup -ugf [reference.fasta]  [sorted.bam] |./bcftools/bcftools call -vmO z -o [output.vcf]</code></p>

<p>To use GATK we’ll need to generate a .dict and a .fasta.fai file to allow efficient random access to the reference. To generate the fasta.fai we use the following samtools command <code class="prettyprint">samtools faidx reference.fa</code> and to generate the .dict we use the following Picard command <code class="prettyprint">java -jar CreateSequenceDictionary.jar -REFERENCE=reference.fa -OUTPUT=reference.dict</code></p>

<p>Next we’ll use the dbsnp file we downloaded at the beginning to annotate the VCF file (and add the rsID for the mutations that are both in our VCF and the dbsnp, to do that we run the following GATK command <code class="prettyprint">java -Xmx[memory]g -jar GenomeAnalysisTK.jar -R [ref.fasta] -T VariantAnnotator -o [output.vcf] --variant [input.vcf] --dbsnp [dbsnp.vcf]</code></p>

<p>Next we’ll run variant filtration to create a couple of filters that tell us how confident we are on the mutation; to do that we run the following GATK command `<code class="prettyprint">java -Xmx[memory]g -jar GenomeAnalysisTK.jar    -R [reference.fasta]    -T VariantFiltration    -o [output.vcf] --variant [input.vcf]   --filterExpression "DP &gt; 10 &amp;&amp; DP &lt; 25" --filterName "low" --filterExpression "DP &gt; 25 &amp;&amp; DP &lt; 50" --filterName "mid" --filterExpression "DP &gt; 50 &amp;&amp; DP &lt; 150" --filterName "high" --filterExpression "DP &gt; 150" --filterName "Xtreme" --filterExpression "DP &lt; 10" --filterName "PASS"</code></p>
<h3 id="troubleshooting_3">
<a class="head_anchor" href="#troubleshooting_3" rel="nofollow"> </a>Troubleshooting</h3>
<p>If you can’t run variant annotator because the variant contigs are not the same as the reference contigs run the following (with picard 1.121 or greater) <code class="prettyprint">java -Xmx2g -jar picard.jar SortVcf INPUT=[input.vcf] OUTPUT=[output.vcf] SEQUENCE_DICTIONARY=[reference.fasta]</code> Then you might have to edit the output vcf and remove the #contigs from the header.</p>
<h2 id="functional-predictions-with-snpeffgatk_2">
<a class="head_anchor" href="#functional-predictions-with-snpeffgatk_2" rel="nofollow"> </a>Functional predictions with SnpEFF/GATK</h2>
<p>Finally we’ll use SnpEFF and GATK to generate some functional predictions. We just need two commands to do this: <code class="prettyprint">java -Xmx[memory]G -jar snpEff.jar  -c snpEff.config -v -o gatk hg19 [input.vcf] &gt; [output.snpeff.vcf]</code> (run with snpEFF) and with GATK <code class="prettyprint">java -Xmx[memory]g -jar GenomeAnalysisTK.jar -T VariantAnnotator -R [ref.fasta] -A SnpEff --variant [input.vcf (same input than the last algorithm)] --snpEffFile [input.snpeff.vcf] -L [input.vcf] -o [output.gatk.vcf]</code></p>

<p>At the end your VCF should look similar to this: <br>
<a href="https://svbtleusercontent.com/270jxqp31gnxba.png" rel="nofollow"><img src="https://svbtleusercontent.com/270jxqp31gnxba_small.png" alt="Screen Shot 2015-03-12 at 6.36.02 PM.png"></a></p>

<p>And the SnpEFF output should look similar to this: <a href="http://materechm.github.io/Bioinformatics/snpEFF_summary.html" rel="nofollow">http://materechm.github.io/Bioinformatics/snpEFF_summary.html</a></p>

<p>You can get a lot of information from the SnpEFF output, for example I decided to look into ALS and AD mutations and generated a table and a graph with the number of mutations in some genes associated these diseases divided by their functional impact. You can see the table and graph below: <br>
<a href="https://svbtleusercontent.com/cqyf3nu9cwmsq.png" rel="nofollow"><img src="https://svbtleusercontent.com/cqyf3nu9cwmsq_small.png" alt="Screen Shot 2015-03-12 at 1.35.11 PM.png"></a><br>
<a href="https://svbtleusercontent.com/1p2su0nijoria.png" rel="nofollow"><img src="https://svbtleusercontent.com/1p2su0nijoria_small.png" alt="Screen Shot 2015-03-12 at 1.37.58 PM.png"></a></p>

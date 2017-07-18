---
layout: post
title:  "Mutation Conservation in Mendelian Genes"
date:   2015-08-12
tag:
- Bioinformatics
category: blog
author: jamie
---

<p>This is a follow up to the mutation conservation analyses I’ve been doing (you can see the analysis for NPC1 <a href="http://mtc.science/mutation-conservation-across-organisms-in-npc1" rel="nofollow">here</a> and for a set of genes that were found to be replaceable <a href="http://mtc.science/humanization-of-yeast-genes-part-2" rel="nofollow">here</a>) </p>

<p>For this analysis I started off with a list of 260 genes associated with mendelian diseases that affect all organelles (the list came mainly from <a href="http://edit.tigem.it/en/research/researchers/antonella-de-matteis/disease-genes" rel="nofollow">here</a>). Then, for each gene I downloaded the protein sequences for human, mouse, drosophila, zebrafish, c. elegans and yeast (as many as were available) from HomoloGene. If a sequence was missing I checked on OMA browser as well. </p>

<p>Afterwards I created a multiple sequence alignment using CLUSTAL W2. I then used Princeton’s Protein Residue Conservation Prediction tool to calculate the Jensen Shannon Divergence, Shannon Entropy and Sum of Pairs scores throughout the protein. I proceeded to search Clinvar for mutations associated with the gene of interest and inputed this information to a <a href="https://github.com/materechm/plabData/blob/master/yeast_replaceable_genes/test.py" rel="nofollow">program I wrote</a>.</p>
<h2 id="results-first-130-genes_2">
<a class="head_anchor" href="#results-first-130-genes_2" rel="nofollow"> </a>Results: first 130 genes</h2>
<p>Throughout all methods pathogenic mutations are on average more conserved than the average amino acid in the protein (Jensen Shannon Divergence p: 3.19E0-5, Shannon Entropy p: 6.06E-09, Sum of Pairs p: 2.77E-09), and more conserved than benign mutations (Jensen Shannon Divergence p: 2.75E-10, Shannon Entropy p: 4.51E-18, Sum of Pairs p: 6.32E-18) <br>
<a href="https://svbtleusercontent.com/6bdzk5g6df3da.png" rel="nofollow"><img src="https://svbtleusercontent.com/6bdzk5g6df3da_small.png" alt="jsDivergence.png"></a><br>
<a href="https://svbtleusercontent.com/dbjz1qacv42f5q.png" rel="nofollow"><img src="https://svbtleusercontent.com/dbjz1qacv42f5q_small.png" alt="sEntropy.png"></a><br>
<a href="https://svbtleusercontent.com/y5lhkkxfx4pdrw.png" rel="nofollow"><img src="https://svbtleusercontent.com/y5lhkkxfx4pdrw_small.png" alt="sumOfPairs.png"></a></p>

<p>The average number of mutations per gene is 12.10852713, and 21% are benign. On average 5.611111111 mutations are fully conserved which make up about 3% of the fully conserved amino acids on the proteins. </p>

<p>Notably, the difference in conservation between pathogenic mutations and the average amino acid seems to be more significant when we have more mutations, and the relationship (pearson correlation: -0.397501) appears to follow a power trend, which means we get a stronger signal as mutations increase as expected, which again could be the reason why we did not reach statistical significance on our (previous mutation conservation analysis)[<a href="http://mtc.science/humanization-of-yeast-genes-part-2" rel="nofollow">http://mtc.science/humanization-of-yeast-genes-part-2</a>]<br>
<a href="https://svbtleusercontent.com/w7jb6lw5mzrdw.png" rel="nofollow"><img src="https://svbtleusercontent.com/w7jb6lw5mzrdw_small.png" alt="corr_n_p.png"></a><br>
There does not seem to be a relationship between number of mutations and percentage fully conserved mutations. This means that even though the difference in conservation between pathogenic and the average is more significant as mutation number increases, the percentage of fully conserved mutations does not depend on how many mutations we have. <br>
<a href="https://svbtleusercontent.com/6zccscs5hbgfeq.png" rel="nofollow"><img src="https://svbtleusercontent.com/6zccscs5hbgfeq_small.png" alt="corr_n_conservation.png"></a><br>
And there does not seem to be a correlation between the percentage fully conserved mutations or the p value with the number of species where there was a homolog, which means we aren’t getting a stronger signal just because there are less species. <br>
<a href="https://svbtleusercontent.com/hj7snz6fthtqea.png" rel="nofollow"><img src="https://svbtleusercontent.com/hj7snz6fthtqea_small.png" alt="corr_species_p.png"></a><br>
<a href="https://svbtleusercontent.com/j1u6pscnqxyg0w.png" rel="nofollow"><img src="https://svbtleusercontent.com/j1u6pscnqxyg0w_small.png" alt="corr_species_conservation.png"></a></p>
<h2 id="some-visual-examples-of-mutation-conservation_2">
<a class="head_anchor" href="#some-visual-examples-of-mutation-conservation_2" rel="nofollow"> </a>Some visual examples of mutation conservation</h2>
<p>In the following graphs amino acids highlighted in purple indicate fully conserved pathogenic mutations, in red are mutations that are not fully conserved and all amino acids with an * below are fully conserved. </p>
<h3 id="1-clcn5_3">
<a class="head_anchor" href="#1-clcn5_3" rel="nofollow"> </a>1) CLCN5</h3>
<p>CLCN5 has 18 pathogenic mutations, all of which are fully conserved and make up 2.80% of the fully conserved amino acids in the protein. Pathogenic mutations are more conserved than the average amino acid in the protein (Jensen Shannon Divergence p: 0.013477584, Shannon Entropy p: 3.35166E-09, Sum of Pairs p: 0.002770766)<br>
<a href="https://svbtleusercontent.com/186i4qbmwfc1q.jpeg" rel="nofollow"><img src="https://svbtleusercontent.com/186i4qbmwfc1q_small.jpeg" alt="CLCN5.jpeg"></a></p>
<h3 id="2-cln3_3">
<a class="head_anchor" href="#2-cln3_3" rel="nofollow"> </a>2) CLN3</h3>
<p>CLN3 has 29 pathogenic mutations, 58.62% which are fully conserved and make up 21.79% of the fully conserved amino acids in the protein. Pathogenic mutations are more conserved than the average amino acid in the protein (Jensen Shannon Divergence p: 0.000347195, Shannon Entropy p: 0.000670302, Sum of Pairs p: 0.000207668)<br>
<a href="https://svbtleusercontent.com/zxm75fatgz1ga.jpg" rel="nofollow"><img src="https://svbtleusercontent.com/zxm75fatgz1ga_small.jpg" alt="CLN3.jpg"></a></p>
<h3 id="3-dhcr7_3">
<a class="head_anchor" href="#3-dhcr7_3" rel="nofollow"> </a>3) DHCR7</h3>
<p>DHCR7 has 30 pathogenic mutations, 93.33% which are fully conserved and make up 8.16% of the fully conserved amino acids in the protein. Pathogenic mutations are more conserved than the average amino acid in the protein (Jensen Shannon Divergence p: 1.15794E-05, Shannon Entropy p: 1.36185E-05, Sum of Pairs p: 0.000107308)<br>
<a href="https://svbtleusercontent.com/l2o0arhwit3geg.jpg" rel="nofollow"><img src="https://svbtleusercontent.com/l2o0arhwit3geg_small.jpg" alt="DHCR7.jpg"></a></p>
<h3 id="4-dnm2_3">
<a class="head_anchor" href="#4-dnm2_3" rel="nofollow"> </a>4) DNM2</h3>
<p>DNM2 has 17 pathogenic mutations, all of which are fully conserved and make up 2.39% of the fully conserved amino acids in the protein. Pathogenic mutations are more conserved than the average amino acid in the protein (Jensen Shannon Divergence p: 0.003927946, Shannon Entropy p: 6.44148E-08, Sum of Pairs p: 0.000504219)<br>
<a href="https://svbtleusercontent.com/347c8jlgeplhg.jpg" rel="nofollow"><img src="https://svbtleusercontent.com/347c8jlgeplhg_small.jpg" alt="DNM2.jpg"></a></p>
<h3 id="5-hexa_3">
<a class="head_anchor" href="#5-hexa_3" rel="nofollow"> </a>5) HEXA</h3>
<p>HEXA has 40 pathogenic mutations, 85.00% are fully conserved and make up 12.45% of the fully conserved amino acids in the protein. Pathogenic mutations are more conserved than the average amino acid in the protein (Jensen Shannon Divergence p: 0.001007446, Shannon Entropy p: 3.23795E-06, Sum of Pairs p: 1.93499E-06)<br>
<a href="https://svbtleusercontent.com/qlnkdjmenxn8a.jpg" rel="nofollow"><img src="https://svbtleusercontent.com/qlnkdjmenxn8a_small.jpg" alt="HEXA.jpg"></a></p>
<h2 id="data_2">
<a class="head_anchor" href="#data_2" rel="nofollow"> </a>Data</h2>
<p>All data is here: <a href="https://github.com/materechm/plabData" rel="nofollow">https://github.com/materechm/plabData</a></p>
<h2 id="references_2">
<a class="head_anchor" href="#references_2" rel="nofollow"> </a>References</h2>
<p><a href="http://edit.tigem.it/en/research/researchers/antonella-de-matteis/disease-genes" rel="nofollow">http://edit.tigem.it/en/research/researchers/antonella-de-matteis/disease-genes</a></p>

<p>Landrum MJ, Lee JM, Riley GR, Jang W, Rubinstein WS, Church DM, Maglott DR. ClinVar: public archive of relationships among sequence variation and human phenotype. Nucleic Acids Res. 2014 Jan 1;42(1)</p>

<p>Thompson, J D, D G Higgins, and T J Gibson. “CLUSTAL W: Improving the Sensitivity of Progressive Multiple Sequence Alignment through Sequence Weighting, Position-Specific Gap Penalties and Weight Matrix Choice.” Nucleic Acids Research 22.22 (1994): 4673–4680. Print.</p>

<p>Capra JA and Singh M. Predicting functionally important residues from sequence conservation. Bioinformatics, 23(15):1875-82, 2007</p>

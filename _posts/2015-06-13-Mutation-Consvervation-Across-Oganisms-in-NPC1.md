---
layout: post
title:  "Mutation Conservation Across Organisms in NPC1"
date:   2015-06-13
categories: Bioinformatics
---

<p>As I mentioned in my previous post, something really important while using model organisms (I used yeast as an example but this is true for every model organism, like mice, flies, fish, worms) is figuring out whether the results are translatable. Given that I am interning at Perlstein Lab and they are interested in Niemann-Pick Disease, I decided to see if mutations in NPC1 are in conserved amino acids. </p>

<p>I got the protein sequences for NPC1 in humans, mice, drosophila, c. elegans, zebrafish, and yeast from Entrez Protein. I then performed a multiple sequence alignment (MSA) using CLUSTALW2. The way MSA typically works is that you have a set S of k sequences</p>

<p><a href="https://svbtleusercontent.com/3ru8auikt72p5q.png" rel="nofollow"><img src="https://svbtleusercontent.com/3ru8auikt72p5q_small.png" alt="eqn1.png"></a> <br>
Let M be an MSA for the set S of k sequences. The alignment of s_i with s_j induced by M is generated as follows: <br>
Remove from M all rows except i and j, then remove all columns that contain only blanks<br>
The sum of pairs score of M is the sum of all pairwise induced alignment scores. The optimal MSA for S with respect to sum of pairs is the MSA with the highest sum of pairs score out of all possible MSA for S. Then to compute the best possible alignment d(i,j) for every pair of prefixes (lengths i, j) we use the following formula</p>

<p><a href="https://svbtleusercontent.com/dkckona2av9baw.png" rel="nofollow"><img src="https://svbtleusercontent.com/dkckona2av9baw_small.png" alt="eqn3.png"></a></p>

<p>The problem with this method is that it quickly gets complex; to compute the best possible alignment d(i,j,k) for every triple of prefixes (lengths i,j,k) we would have to use the following formula<br>
<a href="https://svbtleusercontent.com/eq6xjhgbhzbtq.png" rel="nofollow"><img src="https://svbtleusercontent.com/eq6xjhgbhzbtq_small.png" alt="eqn4.png"></a></p>

<p><a href="https://svbtleusercontent.com/srpf20w1et3wyw.png" rel="nofollow"><img src="https://svbtleusercontent.com/srpf20w1et3wyw_small.png" alt="eqn5.png"></a></p>

<p>For k sequences of length n we have to perform the following number of computations<br>
<a href="https://svbtleusercontent.com/hdmcunkpetyqzg.png" rel="nofollow"><img src="https://svbtleusercontent.com/hdmcunkpetyqzg_small.png" alt="eqn6.png"></a></p>

<p>CLUSTALW2 uses a two step method that is faster. The main idea is to find strong signals (highly conserved blocks) first, outliers are added last and it increases the chances that conserved blocks survive. </p>

<p>The first step is to compute a guide phylogenic tree. To do this it computes all pairwise alignments and stores them in a similarity matrix M<br>
<a href="https://svbtleusercontent.com/us4wptlomabzcw.png" rel="nofollow"><img src="https://svbtleusercontent.com/us4wptlomabzcw_small.png" alt="eqn7.png"></a><br>
It then computes the guide tree using hierarchical clustering. It chooses the smallest M[i,j] then forms a new branch of the tree with s_i and s_j. It then computes the distance from the ancestor of s_i and s_j to all other sequences as the average of the distances to s_i and s_j; to do this it sets M’ = M, deletes rows and columns i and j, adds a new column and row (ij) and then <a href="https://svbtleusercontent.com/c2wptmuofrolg.png" rel="nofollow"><img src="https://svbtleusercontent.com/c2wptmuofrolg_small.png" alt="eqn8.png"></a><br>
It finally iterates until M’ has only one column/row</p>

<p>The second step is progressive MSA. It computes pairwise alignment in the order given by the guide tree. To align a MSA M_1 with a MSA M_2 it uses the usual global alignment algorithm and to score a column it computes the average score over all pairs of symbols in the column.</p>

<p>After all this we end up having to perform less computations </p>

<p><a href="https://svbtleusercontent.com/thozd5nodyca.png" rel="nofollow"><img src="https://svbtleusercontent.com/thozd5nodyca_small.png" alt="eqn9.png"></a></p>

<p>You can see a part of the alignment file below. </p>

<p><a href="https://svbtleusercontent.com/phoyspa1q6fxg.png" rel="nofollow"><img src="https://svbtleusercontent.com/phoyspa1q6fxg_small.png" alt="Screen Shot 2015-06-15 at 8.59.43 AM.png"></a></p>

<p>I got a list of mutations in the NPC1 gene from ClinVar. I got a total of 51 amino acid changes, 6 of which were benign/likely benign. I then searched for the amino acid in which the mutations occur in the sequence alignment and saw whether the amino acid was conserved or not. </p>

<p>To see if the amino acids were conserved I used 3 different methods: Jensen Shannon Distribution, Shannon Entropy and Sum of Pairs. For consistency Shannon entropy scores were scaled to the range [0,1] and then subtracted from 1, so that higher scores indicate greater conservation. </p>

<p>To see if pathogenic mutations are in amino acids that are more conserved than average and more conserved than benign mutations, I calculated the average scores across the entire protein (1278 amino acids for the human protein), the amino acids implicated in pathogenic mutations, and the amino acids implicated in benign mutations. </p>

<p><a href="https://svbtleusercontent.com/9xjn6o5qjzxomq.png" rel="nofollow"><img src="https://svbtleusercontent.com/9xjn6o5qjzxomq_small.png" alt="Screen Shot 2015-06-14 at 11.07.05 PM.png"></a></p>

<p>As expected the average score for pathogenic mutations was higher than the average for the entire protein and the benign mutations. To figure out if the difference was statistically significant I then calculated the standard deviation for these values and the p values for the relationships whole protein - pathogenic and pathogenic - benign and found that the difference between all of these relationships throughout the 3 methods for pathogenic - benign and 2 methods (Jensen-Shannon Divergence, Shannon Entropy) for whole protein - pathogenic were statistically significant (p &lt; 0.05) </p>

<p><a href="https://svbtleusercontent.com/qgz1izk56y2wna.png" rel="nofollow"><img src="https://svbtleusercontent.com/qgz1izk56y2wna_small.png" alt="Screen Shot 2015-06-27 at 3.06.12 PM.png"></a></p>

<p>You can see the full mutation data here: <a href="https://github.com/materechm/Bioinformatics/blob/gh-pages/NPC1MutationConservationData.xlsx" rel="nofollow">https://github.com/materechm/Bioinformatics/blob/gh-pages/NPC1MutationConservationData.xlsx</a><br>
The commands I used to generate the p values on R here: <a href="https://gist.github.com/materechm/a673f4034f7a087ae04a" rel="nofollow">https://gist.github.com/materechm/a673f4034f7a087ae04a</a><br>
And the alignment file here: <a href="https://github.com/materechm/Bioinformatics/blob/gh-pages/proteinAligmentNPC1.pdf" rel="nofollow">https://github.com/materechm/Bioinformatics/blob/gh-pages/proteinAligmentNPC1.pdf</a></p>

<p>If you have any comments or suggestions on interesting things that can be done with this data shoot me an email at <a href="mailto:maria@perlsteinlab.com" rel="nofollow">maria@perlsteinlab.com</a> </p>

<p><strong>References</strong></p>

<p>Landrum MJ, Lee JM, Riley GR, Jang W, Rubinstein WS, Church DM, Maglott DR. ClinVar: public archive of relationships among sequence variation and human phenotype. Nucleic Acids Res. 2014 Jan 1;42(1)</p>

<p>Thompson, J D, D G Higgins, and T J Gibson. “CLUSTAL W: Improving the Sensitivity of Progressive Multiple Sequence Alignment through Sequence Weighting, Position-Specific Gap Penalties and Weight Matrix Choice.” Nucleic Acids Research 22.22 (1994): 4673–4680. Print.</p>

<p>Capra JA and Singh M. Predicting functionally important residues from sequence conservation. Bioinformatics, 23(15):1875-82, 2007</p>

# buty_full
## Introduction
MOVED TO buty_phyl https://github.com/caozhichongchong/buty_phyl
* buty_full infers traits by 16S
* input: otu table (-t) and otu sequences (-s)
* requirement: mafft
* Optional: fasttree
![alt text](https://raw.githubusercontent.com/caozhichongchong/buty_full/master/Methodology.png)

## Install
`pip install buty_full`\
in preparation: `anaconda download caozhichongchong/buty_full`

## Availability
in preparation: https://anaconda.org/caozhichongchong/buty_full

https://pypi.org/project/buty_full

## How to use it
1. test the buty_full\
`buty_full --test`

2. try your data\
`buty_full -t your.otu.table -s your.otu.seqs`\
`buty_full -t your.otu.table -s your.otu.seqs -top 2000`

3. try different traits (default is butyrate production)\
predicting butyrate production\
`buty_full -t your.otu.table -s your.otu.seqs --rs your.own.reference.16s`\
or\
`buty_full -t your.otu.table -s your.otu.seqs --rs your.own.reference.16s --rt b`\
predicting sulfate reduction (in preparation, not yet)\
`buty_full -t your.otu.table -s your.otu.seqs --rs your.own.reference.16s --rt s`\
predicting nitrate reduction (in preparation, not yet)\
`buty_full -t your.otu.table -s your.otu.seqs --rs your.own.reference.16s --rt n`

4. use your own traits\
`buty_full -t your.otu.table -s your.otu.seqs --rs your.own.reference.16s --rt your.own.reference.traits`

* your.own.reference.16s is a fasta file containing the 16S sequences of your genomes\
\>Genome_ID1\
ATGC...\
\>Genome_ID2\
ATGC...

* your.own.reference.traits is a metadata of whether there's trait in your genomes (0 for no and 1 for yes)\
Genome_ID1   0\
Genome_ID1   1

## Results
The result dir of "Bayers_model":
* `filename.infertraits.txt`: the OTUs inferring as butyrate-producing bacteria (1.0, 0.5) 
and non-butyrate-producing bacteria (0.0).
* `filename.infertraits.abu`: the total abundance of butyrate-producing bacteria in all samples.
* `filename.infertraits.otu_table`: the otu_table of butyrate-producing bacteria in all samples.

The result dir of "Filtered_OTU":
* Some temp files of filtered OTUs, alignment, and tree.

## Copyright
Copyright: An Ni Zhang, Prof. Eric Alm, Alm Lab in MIT\
Citation: Not yet, coming soon!\
Contact: anniz44@mit.edu

# Analysis of Transcriptional Profile of Mammalian Cardiac Regeneration with mRNA-Seq
The objective of this project is to explore/verify findings from Transcriptional Profile of Mammalian Cardiac Regeneration with mRNA-Seq. Researchers are trying to uncover the secret of heart regeneration, a function which will be lost during adulthood. In this project, acquired, processed, and analyzed sequencing data generated from different stages of mice reproduce one result in the paper and better understand the difference on the gene expressions between the period when neonatal mice are able to regenerate their heart tissue and when they lose this ability later in development.

# Contributors
Data Curator: pre-computed.

**Programmer: Neha Gupta.**

Analyst: pre-computed.

**Biologist: Neha Gupta.**


# Repository Contents

## Programmer

**tophat.qsub** - Takes input paired end read1.fastq and read2.fastq files, mm9 reference genome. Command for it's execution is qsub tophat.qsub. Output files are accepted_hits.bam files. 

**RSeQC.qsub** - Takes accepted_hits.bam, accepted_hits.bam.bai and mm9.bed files as input and gives geneBody_coverage, inner_distanceplots and one quality control metrice as output files. Command is qsub reseqc.qsub for execution. 

**cufflinks.qsub** - Input files are accepted_hits.bam, mm9.gtf and mm9.fa as inputs and gives FPKM_tracing file as output. Execution is done through qsub cufflink,qsub command.

**cuffdiff.qsub** - Takes accepted_hits.bam files for P0_1, P0_2, AD_1 and AD_2 as input files. Output files is gene_exp.diff. Command is same qsub cuffdiff.qsub

## Biologist

Input files are FPKM_tracing files for P0_1, P0_2, AD_1, AD_2, P4_1, P4_2, P7_1 and P7_2. Output files are lin graph with FPKM values of representative Sarcomere, Mitochondria and cell cycle genes which were significant and differentially expressed. Also a clustered heatmap of top 1000 DEG were reported. Execution was done on R Studio. 

Alternative to run on command line:

`module load R/4.0.2`

`Rscript BIOLOGIST.R`



# codon-usage-frquency-graph
Genomic sequence analysis in R programming  GC content calculation, DNA-to-RNA transcription, codon frequency profiling, and start/stop codon detection using the Biostrings package.This R script performs fundamental genomic sequence analysis on a FASTA file (.fna) using the Bioconductor Biostrings package.
here the file name that i used was "genome1.fna"

#what it does:
-Sequence Loading — Reads a genomic FASTA file using readDNAStringSet()

-GC Content Calculation — Computes the percentage of Guanine & Cytosine bases in the sequence

-DNA → RNA Transcription — Converts DNA to RNA by replacing Thymine (T) with Uracil (U)

-Codon Extraction — Parses the RNA sequence into triplet codons

-Start & Stop Codon Detection — Counts occurrences of AUG (start) and UAA (stop) codons

-Codon Frequency Visualization — Generates a barplot of all codon frequencies across the sequence

#Tools Used are as follows:
-R programming

-Biostrings library

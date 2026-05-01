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

library(Biostrings)
sequence<-readDNAStringSet('genome1.fna')
sequence

dna_seq <- as.character(sequence[[1]])
cat("first DNA sequence:\n",dna_seq,"\n")
gc_count <- sum(strsplit(dna_seq, "")[[1]] %in% c("G", "C"))
gc_content<-(gc_count/nchar(dna_seq))*100
cat("GC_content:\n",round(gc_content,2))
rna_seq <- chartr("T","U",dna_seq)

get_codon<-function(seq){
  substring( seq, seq(1,nchar(seq)-2,3),seq(3,nchar(seq),3)
  )
}

codon<-get_codon(rna_seq)
start_codon = sum(codon == "AUG")
stop_codon = sum(codon == "UAA")
start_codon
stop_codon
codon_freq<-table(get_codon(rna_seq))
barplot(codon_freq,las = 2,main = "codon Frequency")


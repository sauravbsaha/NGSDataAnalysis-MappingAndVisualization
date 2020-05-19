# Next-generation sequencing help document
This document is being created as notes for  NGS data analysis.

1. Raw sequencing reads can be downloaded from NCBI SRA database.
2. Genome sequence in fasta format can be downloaded from NCBI Genome database.

## Indexing of reference genome before alignment
```bwa index reference.fasta```

## Aligning reference with raw reads
```bwa mem reference.fasta reads.fastq > reads.sam```

## Convering SAM to BAM file format
```samtools view -h -b -S reads.sam > reads.bam```

## Extracing the only reads mapped to the reference
```samtools view -b -F 4 reads.bam > reads.mapped.bam```

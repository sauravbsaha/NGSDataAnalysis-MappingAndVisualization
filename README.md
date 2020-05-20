# Next-generation sequencing help document
## Chapter 1- Mapping and Visualization of NGS reads 
This document is being created as notes for  NGS data analysis.

1. Raw sequencing reads can be downloaded from NCBI SRA database.
2. Genome sequence in fasta format can be downloaded from NCBI Genome database.

## Indexing of reference genome before alignment
```bwa index reference.fasta```

## Aligning reference with raw reads
```bwa mem reference.fasta reads.fastq > reads.sam```

## Convering SAM to BAM file format
```samtools view -h -b -S reads.sam > reads.bam```

## Extracting the only reads mapped to the reference
```samtools view -b -F 4 reads.bam > reads.mapped.bam```

## Sorting read according to read name
```samtools sort reads.mapped.bam -o reads.mapped.sorted```

## Indexing the BAM file
```samtools index reads.mapped.sorted reads.mapped.bai```

# Now you are ready to view the alignment on IGV Viewer! Enjoy :)

<img src="https://github.com/sauravbsaha/NGS_data_analysis/blob/master/igv_screenshot.png"
     alt="IGV Screenshot"
     style="float: center; margin-right: 10px;" />

* Note: IGV would require mapped reads sorted in bam format with bai index file in the same directory 

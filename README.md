# SWEEP_GOLD
An updated version of https://github.com/jclev-uga/SWEEP

How to run:

    SWEEP_GOLD -bam -vcf -o [-len] [-maf] [-dep]
-bam: a list of bam files
-vcf: a vcf input file
-o: output file
-len: sequence lengh
-maf: minor allele frequencey
-dep: depth

The program requires ~1-2 Gb for basic process and ~0.5-1  GB ber every bam file (varied based on the depth and the reference genome size).
In case of big number of bams and/or low memory capacity, the program can be run as following:

# SWEEP_GOLD
A vastly improved version of https://github.com/jclev-uga/SWEEP for refinement SNP calling of polypoids from NGS data

How to run:
## I. Full run:

    SWEEP_GOLD -bam -vcf -o [-len] [-maf] [-dep]
    
**-bam**: a list of bam files [Required]

**-vcf**: a vcf input file [Required]

**-o**: output file prefix [Required]

**-len**: lengh of sequence reads [Optional, default=300]

**-maf**: minor allele frequencey filter [Optional, default=5]

**-dep**: minimum depth to accept a haplotype [Optional, default=5]

### The program requires ~1-2 Gb RAM for basic process and ~0.5-1 GB RAM ber every bam file (varies based on the depth and the reference genome size).

![image](https://user-images.githubusercontent.com/21265433/44171352-01cd9400-a0a8-11e8-80c0-bea17c0d873e.png)

#######################################################################

## II. Split run:
#### In case of big number of bams and/or low memory capacity, the program can be run as follows:

#### 1. Bootstraping, one time:
        SWEEP_GOLD BOOTSTRAP -vcf [-len]
**-vcf**: input vcf file [Required] 

**-len**: sequence length [Optional, default=300]


#### 2. procssing bams, for every single bam:
        SWEEP_GOLD RAW -vcf -bam [-o]
**-vcf**: input vcf file [Required] 

**-bam**: an input bam file [Required]

**-o**: output .raw file [Optional, default=input bam file]


#### 3. filtration, one time otherwise if you want to test differnt maf and/or depth:
        SEEP_GOLD FILTER -vcf -bam -o [-maf] [-dep]
**-vcf**: input vcf file [Required] 

**-bam**: an input bam.raw file list, wildcards can be used inside the list [Required]

**-o**: output .raw file [Required]

**-maf**: minor allele frequencey [Optional, default=5]

**-dep**: depth [Optional, default=5]

![image](https://user-images.githubusercontent.com/21265433/44171420-2de91500-a0a8-11e8-802a-ebd79bfaf365.png)
#################################################################
# III. combined run: 
the outputs of the full run can be used into split run. **however, -len should be the same**.

![sweep3](https://user-images.githubusercontent.com/21265433/44222453-85dc5600-a152-11e8-9997-735f2c84b43d.jpg)
################################################################


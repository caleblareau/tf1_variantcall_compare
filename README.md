# TF1 Variant Calling Comparison
Comparison of tools for calling variants in TF1 scATAC-seq data

The `bams` folder contains the 855 HQ TF1 cells to be analyzed for subclonal variant structure. 

```
bcftools mpileup -b test_bams.txt -f rCRS.fasta --ignore-RG | bcftools call -mv -Ob -o TF1_bcftools_singlecell.bcf
```

The command used for calling variants with `freebayes` is shown here
```
freebayes -f rCRS.fasta for_fb/* > TF1_freebayes_singlecell.vcf
```

For both sets of output files, we used `bcftools view` to stream output into this `grep | awk` command

```
grep chrM | awk '{print $1"\t"$2"\t"$4"\t"$5"\t"$6}' 
```

To focus on columns needed to evluate the called variants. The plain-text tsv files are listed below for each tool


### Output files:
```
TF1_freebayes_calls.tsv
TF1_samtools_calls.tsv
```

These were imported for comparisons with the mgatk variant calling procedure.

<br><br>

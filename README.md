# TF1 Variant Calling Comparison
Comparison of tools for calling variants in TF1 scATAC-seq data

```
bcftools mpileup -b test_bams.txt -f rCRS.fasta --ignore-RG | bcftools call -mv -Ob -o TF1_bcftools_singlecell.bcf
```
```
freebayes -f rCRS.fasta for_fb/* > TF1_freebayes_singlecell.vcf
```


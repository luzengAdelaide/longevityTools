---
title: General Analytical Approach
keywords: 
last_updated: Mon Feb 15 14:59:07 2016
---

## Construction of MR eSNP risk score

File sood-2015-fileS1.xls reports the expression direction relative to age for each probe from the 150 probe set. See Top 150 worksheet. A gene marked as 'down' in column 'Ratio of Y:O muscle' means that the expression of the gene is lower in young vs old muscle. 

The goal is to generate an eSNP risk score constructed from eSNP alleles associated with increasing gene expression for genes that decrease with age and from eSNP alleles associated with decreasing gene expression for genes that increase with age. This eSNP risk score would represent an expression profile that more closely mimics the younger age profile rather than the older age profile.  

For the 150 probes that map to genes, identify cis-eSNPs using GTEx preanalyzed results from whole blood. Preanalyzed GTEx results correct for multiple testing of SNPs for each gene. To identify independent cis-eSNPs for each gene, prune cis-eSNPs in LD using 1000G EUR population group genotypes. Once independent cis-eSNPs are identified, create a file listing the SNPs to be included in a risk score and which allele is associated with decreasing expression for genes that increase with age (upregulated gene) and which allele is associated with increasing expression for genes that decrease with age (downregulated gene). Upregulated and downregulated genes based on column 'Ratio of Y:O muscle' from Sood et al supplemental file.

Individual level eSNP risk scores will be constructed as below. The eSNP risk score represents the MR instrumental variable.

$$ eSNP Risk Score_i = \sum_{j=1}^{N} eSNP_j^{AlleleDown} + \sum_{k=1}^{N} eSNP_k^{AlleleUp}  $$

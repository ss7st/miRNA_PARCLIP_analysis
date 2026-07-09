# miRNA_PARCLIP_analysis
R Markdown workflow for integrative analysis of PAR-CLIP, TCGA expression, and survival data to identify and rank candidate therapeutic microRNAs in glioblastoma
---
title: "Therapeutic delivery of microRNAs discovered to target deregulated glioblastoma pathways inhibits tumor growth in mice"
output: html_document
date: "2026-07-09"
---


```{r}
# Therapeutic delivery of microRNAs discovered to target deregulated glioblastoma pathways inhibits tumor growth in mice

## Table of Contents

1. Overview
2. Repository Contents
3. Software Requirements
4. Input Files Required
5. Running the Analysis
6. Analysis Parameters
7. Output Files
8. Reproducibility Information
9. Data Availability
10. Code Availability
11. Contact

---

## Overview

This repository contains the R Markdown analysis workflow used to identify candidate therapeutic microRNAs (miRNAs) targeting deregulated pathways in glioblastoma.
```


```{r}
# Software Requirements

## R version

Recommended:

R >= 4.2

RStudio is recommended for running the R Markdown notebook.

---

# Required R Packages

The following R packages are required:

tidyverse
readxl
writexl
knitr
rmarkdown
```

```{r}
---

# Input Files Required

All input files should be placed in the same working directory as:

miRNA_PARCLIP_analysis.Rmd

The following files are required to run the analysis.

---

## 1. PAR-CLIP Cluster Files

### AGO1 PAR-CLIP cluster file

File name:

ago1.clusters.csv

Description:

Contains AGO1 PAR-CLIP identified RNA-binding clusters used for identification of miRNA-mRNA interactions.

---

### AGO2 PAR-CLIP cluster file

File name:

ago2.clusters.csv

Description:

Contains AGO2 PAR-CLIP identified RNA-binding clusters used for identification of miRNA-mRNA interactions.

---

### AGO3 PAR-CLIP cluster file

File name:

ago3.clusters.csv

Description:

Contains AGO3 PAR-CLIP identified RNA-binding clusters used for identification of miRNA-mRNA interactions.

---

## 2. miRNA Seed Sequence Information

File name:

mirna-seeds.csv

Description:

Contains miRNA seed sequence information used to match PAR-CLIP binding sites with candidate miRNAs.

---

## 3. Intermediate PAR-CLIP Data (Optional)

File name:

intermediate-parclip-new.RData

Description:

Contains processed PAR-CLIP interaction data. This file can be used to avoid repeating PAR-CLIP preprocessing.

If this file is available:

useintermediate <- TRUE

Otherwise:

useintermediate <- FALSE

will regenerate PAR-CLIP processing.

---

## 4. TCGA Differential Expression Data

File name:

tcga-rnaseq-tvn.csv

Description:

Contains processed TCGA glioblastoma RNA-seq differential expression results.

Required information:

- Gene identifier
- log2 fold change
- p-value
- adjusted p-value

---

## 5. Glioblastoma Gene Expression Data

File name:

fpkm.csv

Description:

Contains glioblastoma gene expression data used for target gene expression analysis.

Required information:

- Gene identifier
- Expression value (FPKM/RPKM/TPM)

---

## 6. Survival Data

File name:

mrna-from-oncolnc.xlsx

Description:

Contains patient survival association data obtained from OncoLnc.

Required information:

- TCGA gene identifier
- Cox coefficient
- p-value
- adjusted p-value

---

## 7. Gene Annotation Data

File name:

annotated_genelist_onctsg.csv

Description:

Contains oncogene and tumor suppressor gene annotations.

Gene categories:

- ONC = Oncogene
- TSG = Tumor suppressor gene
```


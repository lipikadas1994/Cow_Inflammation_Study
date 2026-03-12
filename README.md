This repository contains R scripts and processed phyloseq objects associated with the manuscript “Postpartum Inflammation is Reflected in Early Distinct Fecal Microbiome Remodeling in Dairy Cows.” 
The repository includes several phyloseq objects (.rds files) used for downstream microbiome analyses. 
ps_updated.rds is a phyloseq object generated after removal of contaminant ASVs from the fecal microbiome dataset using the Decontam and SourceTracker packages. 
ps_both_elevated_updated.rds is a subset of ps_updated.rds containing samples where both fibrinogen and haptoglobin levels were elevated.
ps_both_normal_updated.rds contains samples where both biomarkers were within the normal range. 
ps_fibrinogen_elevated_updated.rds contains samples with elevated fibrinogen levels.
ps_fibrinogen_normal_updated.rds contains samples with normal fibrinogen levels. 
ps_haptoglobin_elevated_updated.rds contains samples with elevated haptoglobin levels 
ps_haptoglobin_normal_updated.rds contains samples with normal haptoglobin levels.
The repository also includes analysis notebooks and scripts. 
SpiecEasi-2.ipynb contains R scripts used for microbial network analysis.
DADA2_Diversity_Updated.ipynb contains R scripts for 16S rRNA data preprocessing using the DADA2 pipeline as well as alpha and beta diversity analyses. 
Deseq2 folder contains .Rmd and .html files with R scripts used for differential abundance analysis using DESeq2.

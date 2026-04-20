# Fecal Microbiota and Postpartum Inflammation in Dairy Cows

## Overview
The periparturient period in dairy cows is characterized by significant metabolic stress and immune modulation. While a controlled inflammatory response is essential for processes such as parturition and uterine involution, excessive or unresolved inflammation can negatively impact animal health and productivity.

This project investigates the relationship between fecal microbiota composition and systemic inflammation in early postpartum Holstein cows, using acute-phase proteins **fibrinogen** and **haptoglobin** as inflammation markers.

---

## Objectives
- Evaluate whether systemic inflammation is associated with changes in fecal microbiota
- Identify microbial taxa linked to elevated inflammatory status
- Assess microbial diversity patterns (alpha and beta diversity)
- Explore microbial interactions and potential keystone taxa
- Investigate microbiota as potential early indicators of inflammatory risk

---

## Study Design
- **Subjects:** 71 Holstein dairy cows
- **Sampling timepoints:** Day 1 and Day 3 in milk (DIM)
- **Sample type:** Fecal samples

### Inflammation Markers
- **Fibrinogen:** Measured on DIM 1, 3, and 7
- **Haptoglobin:** Measured on DIM 1 and 3

---

## Methods

### Microbiome Profiling
- 16S rRNA gene sequencing (targeting V3–V4)
- DADA2 pipeline (v1.34.0) for denoising and ASV inference
- Taxonomic assignment using SILVA databases (v138.2)

### Data Preprocessing
- Removal and identification of contaminants using:
  - decontam (v1.14.0)
  - SourceTracker (v1.0)
- Validation of sequencing performance using mock community analysis
- Assessment of overall data structure using NMDS (Non-metric Multidimensional Scaling)

### Diversity Analysis
- **Alpha diversity:** Observed, Shannon, Simpson, Evenness
  - Linear mixed-effects models adjusting for covariates:
    - parity
    - BCS
    - DIM
    - extraction date

- **Beta diversity:**
  - Bray–Curtis
  - Aitchison
  - Weighted & Unweighted UniFrac
  - PERMANOVA

### Differential Abundance
- DeSeq2 (v1.46.0) for identifying taxa associated with inflammation status (ASV-level analyses)
- Spearman correlation analysis between:
  - absolute abundance (normalized by 16S qPCR values)
  - serum inflammatory marker concentrations

### Network Analysis
- SPIEC-EASI (v1.1.2) for microbial interaction networks
- Identification of keystone taxa based on:
  - top 0.025 percentile for **degree** and **eigenvector centrality**
- Evaluation of relative distribution and correlation of keystone taxa across inflammation states

---

## Key Findings
- No significant association between inflammation and alpha diversity after multiple testing correction
- Significant shifts in microbial community composition (beta diversity) associated with inflammation, measured by:
  - fibrinogen
  - haptoglobin
  - combined fibrinogen and haptoglobin
- Differential abundance of specific taxa linked to fibrinogen and haptoglobin levels
- Distinct microbial interaction networks under different inflammatory states
- Identification of potential keystone taxa contributing to microbiome structure

---
Data Description

Processed Data (Primary Use)

Located in data/processed/

ps_updated.rds
→ Final curated phyloseq object after:

contaminant removal
mock exclusion
data curation
metadata_table.rds
→ Cleaned metadata used for all downstream analyses

otu_table.rds
→ final OTU table

taxa_table.rds
→ final taxonomy table

Stratified datasets:

ps_fibrinogen_normal_updated.rds
ps_fibrinogen_elevated_updated.rds
ps_haptoglobin_normal_updated.rds
ps_haptoglobin_elevated_updated.rds
ps_both_normal_updated.rds
ps_both_elevated_updated.rds
Intermediate Data

Located in data/intermediate/

Includes intermediate phyloseq objects and preprocessing outputs:

ps.decontam.rds
ps.contam.rds
ps.mock.rds
ps.true_sample_cleaned.rds
phyloseq.rds
ps.pa.rds, ps.pa.pos.rds, ps.pa.neg.rds
ps.sample_mock_cleaned.rds
These files are retained for reproducibility but are not required for standard downstream analysis.
Raw Data

Located in data/raw/

1083_Microbiome_Metadata.csv
Cow_FecalMicrobiome_Metadata_MERGED.csv
SourceTracker Inputs:

source_metadata.csv, sink_metadata.csv
source_otus.csv, sink_otus.csv
Archived Data

Located in archive/

Older metadata versions:

Cow_FecalMicrobiome_Metadata-2-2.csv
Deprecated notebooks:

Stored in archive/notebooks/
These are preserved for version history and reproducibility.
Analysis Workflows

Final Notebooks

Located in notebooks/

DADA2_Diversity_Updated.ipynb
→ Microbiome processing and diversity analysis

Network_SpiecEasi.ipynb
→ Network inference and keystone taxa identification

Differential Abundance Results

Located in results/differential_abundance/DESeq2/

Contains rendered outputs from DESeq2 analyses:

Fibrinogen-associated analysis
Haptoglobin-associated analysis
Combined inflammation analysis
Includes:

.Rmd files (analysis scripts)
.html files (rendered reports)
Recommended Starting Point

For most users:

data/processed/ps_updated.rds
data/processed/metadata_table.rds
These files contain the finalized dataset used for all major analyses.

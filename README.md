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

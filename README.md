Fecal Microbiota and Postpartum Inflammation in Dairy Cows
Overview
The periparturient period in dairy cows is characterized by significant metabolic stress and immune modulation. While a controlled inflammatory response is essential for processes such as parturition and uterine involution, excessive or unresolved inflammation can negatively impact animal health and productivity.
This project investigates the relationship between fecal microbiota composition and systemic inflammation in early postpartum Holstein cows, using acute-phase proteins fibrinogen and haptoglobin as inflammation markers.
 
Objectives
•	Evaluate whether systemic inflammation is associated with changes in fecal microbiota
•	Identify microbial taxa linked to elevated inflammatory status
•	Assess microbial diversity patterns (alpha and beta diversity)
•	Explore microbial interactions and potential keystone taxa
•	Investigate microbiota as potential early indicators of inflammatory risk
 
Study Design
•	Subjects: 71 Holstein dairy cows
•	Sampling timepoints: Day 1 and Day 3 in milk (DIM)
•	Sample type: Fecal samples
•	Inflammation markers:
o	Fibrinogen: measured on DIM 1, 3 and 7
o	Haptoglobin: Measured on DIM 1 and 3
 
Methods
1. Microbiome Profiling
•	16S rRNA gene sequencing (Targeting V3-V4)
•	DADA2 pipeline (v1.34.0) for denoising and ASV inference
•	Taxonomic assignment using Silva databases (v138.2)
2. Data Preprocessing
•	Removal and identification of source of contaminants using decontam (v1.14.0) and SourceTracker (v1.0) 
•	Validation of sequencing performance using mock community analysis
•	Assessment of overall data structure using NMDS (Non-metric Multidimensional Scaling)
3. Diversity Analysis
•	Alpha diversity: Observed, Shannon, Simpson, Evenness
o	Linear mixed-effects models adjusting for covariates (parity, BCS, DIM, extraction date)
•	Beta diversity:
o	Bray–Curtis, Aitchison, Weighted & Unweighted UniFrac
o	PERMANOVA 
4. Differential Abundance
•	DeSeq2 (v1.46.0) for identifying taxa associated with inflammation status (ASV-level analyses)
•	Spearman correlation analysis performed between absolute abundance (normalized by 16s qPCR value) and serum inflammatory marker concentration
5. Network Analysis
•	SPIEC-EASI (v1.1.2) for microbial interaction networks
•	Identification of keystone taxa based on network metrics top 0.025 percentile) for both degree and eigenvector centrality
•	Evaluation of relative distribution and correlation of keystone taxa across inflammation states 
Key Findings
•	No significant association between inflammation and alpha diversity after multiple testing correction
•	Significant shifts in microbial community composition (beta diversity) associated with inflammation measured by all the inflammation marker (Fibrinoigen, Haptoglobin and combined Fibrinogen and Haptoglobin)
•	Differential abundance of specific taxa linked to fibrinogen and haptoglobin levels
•	Distinct microbial interaction networks under different inflammatory states
•	Identification of potential keystone taxa contributing to microbiome structure

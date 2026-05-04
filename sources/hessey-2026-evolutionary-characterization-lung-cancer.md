---
title: "Evolutionary characterization of lung cancer metastasis"
authors: Sonya Hessey, Abigail Bunkum, Ariana Huebner, Kerstin Haase, Kristiana Grigoriadis, Cristina Naceur-Lombardelli, et al. (TRACERx Consortium, TRACERx EVO Consortium, PEACE Consortium), Simone Zaccaria, Nicholas McGranahan, Charles Swanton, Mariam Jamal-Hanjani
year: 2026
doi: 10.1038/s41586-026-10428-4
category: diagnostics
pdf_path: /home/user/llm_wiki/papers/hessey-2026-evolutionary-characterization-lung-cancer.pdf
pdf_filename: hessey-2026-evolutionary-characterization-lung-cancer.pdf
source_collection: external
---

## One-line Summary
Longitudinal whole-exome sequencing of 501 primary and metastatic NSCLC samples from 24 patients (TRACERx + PEACE autopsy) reveals that metastases diverge genomically from their primary tumour, frequently seed each other, and that chromosomal instability facilitates extrathoracic spread.

## 1. Document Information
- **Journal**: Nature (2026)
- **Received**: 29 June 2025; **Accepted**: 17 March 2026
- **Study**: TRACERx lung study + PEACE (Posthumous Evaluation of Advanced Cancer Environment) autopsy programme
- **ClinicalTrials.gov**: NCT01888601 (TRACERx), NCT03004755 (PEACE)

## 2. Key Contributions
- First comprehensive longitudinal genomic atlas of NSCLC metastasis from diagnosis to death, covering 70% of radiologically detected metastases
- Shows that in 62.5% of patients, multiple primary tumour subclones independently disseminated, each founding distinct metastases
- Demonstrates that >50% of sampled metastases were seeded by other metastases, not directly from the primary tumour
- Identifies chromosomal instability (somatic copy-number alterations) as enriched in subclones that disseminate extrathoracically
- Reveals that metastasis in-situ duration influences likelihood of further seeding

## 3. Methodology and Architecture
- **Cohort**: 24 patients with NSCLC (9 LUAD, 10 LUSC, 5 other), enrolled in both TRACERx and PEACE
- **Samples**: 501 total regions — 108 from 24 primary tumours, 41 pre-mortem metastases, 352 from 233 autopsy metastases
- **Sequencing**: High-depth whole-exome sequencing (WES; median depth 401.2x)
- **Analysis**: Subclonal architecture reconstruction; phylogenetic history per patient; somatic mutations + SCNAs + WGD events
- **Subclone classification**: truncal / primary-unique / metastasis-unique / shared subclonal
- **Heterogeneity metrics**: mutation diversity and SCNA diversity between/within metastases and vs. primary

## 4. Key Results and Benchmarks
- Metastases from the same patient are more similar to each other than to their paired primary (mutation diversity P=0.004, SCNA diversity P=6×10⁻⁵)
- Median 7 subclones per metastasis (range 3–37); 79% of metastases contained a subclone not detected in any other metastasis
- Metastasis-unique subclones per patient: median 28 (range 4–58) — 11-fold greater than prior TRACERx single-biopsy analysis (median 2.5)
- Most metastatic migrations stayed within the same anatomical cavity (thorax); extrathoracic spread was rare but genomically distinct
- Additional driver alterations and genome doubling events acquired after metastatic dissemination

## 5. Limitations and Future Work
- Single-region sampling per metastasis in 75% of cases limits full subclonal resolution
- 24 patients is a small cohort, though sampling depth (16 metastasis regions/patient on average) is unprecedented
- Autopsy-based sampling means the evolutionary history is reconstructed retrospectively
- Extrathoracic spread mechanism (CIN) is correlational; functional validation not provided

## 6. Related Work
- TRACERx multi-region primary NSCLC profiling (Jamal-Hanjani et al., prior TRACERx publications)
- Metastatic migration studies in ovarian, breast, and prostate cancer (cited as context for bidirectional migration patterns)
- Chromosomal instability and metastasis literature

## 7. Glossary
- **NSCLC**: Non-small cell lung cancer
- **TRACERx**: Tracking Non-small Cell Lung Cancer Evolution through Therapy (prospective multi-region study)
- **PEACE**: Posthumous Evaluation of Advanced Cancer Environment (research autopsy programme)
- **WES**: Whole-exome sequencing
- **SCNA**: Somatic copy-number alteration
- **WGD**: Whole-genome doubling
- **CIN**: Chromosomal instability
- **LUAD / LUSC**: Lung adenocarcinoma / lung squamous cell carcinoma
- **Truncal subclone**: Most recent common ancestor of all sequenced cancer cells
- **Metastasis seeding**: A metastasis founding a new secondary metastasis (as opposed to direct spread from primary)

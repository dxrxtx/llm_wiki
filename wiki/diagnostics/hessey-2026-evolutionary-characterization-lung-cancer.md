---
title: "Evolutionary characterization of lung cancer metastasis"
authors: Hessey, Bunkum, Huebner, Haase, Grigoriadis, Naceur-Lombardelli, et al. (TRACERx & PEACE Consortia); Zaccaria, McGranahan, Swanton, Jamal-Hanjani
year: 2026
doi: 10.1038/s41586-026-10428-4
source: hessey-2026-evolutionary-characterization-lung-cancer.md
category: diagnostics
pdf_path: /home/user/llm_wiki/papers/hessey-2026-evolutionary-characterization-lung-cancer.pdf
pdf_filename: hessey-2026-evolutionary-characterization-lung-cancer.pdf
source_collection: external
tags: [lung-cancer, metastasis, tumor-evolution, NSCLC, chromosomal-instability, TRACERx, PEACE, whole-exome-sequencing]
---

## Summary
Using 501 longitudinally collected tumour samples (WES, median depth 401x) from 24 NSCLC patients enrolled in both TRACERx and the PEACE autopsy programme, this study reconstructs the complete evolutionary history of each patient's disease from diagnosis to death. The key finding is that metastases are genomically divergent from primary tumours and, critically, from each other — and that more than half of metastases were seeded by *other metastases* rather than directly from the primary tumour.

## Key Contributions
- **Multi-seeding**: In 62.5% of patients, multiple independent primary-tumour subclones disseminated, each founding distinct metastases
- **Metastasis-to-metastasis seeding**: >50% of metastases were seeded by other metastases, not the primary tumour
- **Post-dissemination evolution**: Metastases acquire additional driver alterations and whole-genome doubling events *after* leaving the primary tumour
- **Extrathoracic spread**: The rare subclones that escaped the thoracic cavity were enriched for SCNAs, implicating chromosomal instability (CIN) as a facilitator of distant spread
- **Temporal factor**: Longer in-situ residence increased a metastasis's probability of seeding further metastases

## Methodology and Architecture
- **Cohort**: 24 NSCLC patients (9 LUAD, 10 LUSC, 5 other); median OS 29 months
- **Sampling**: 108 primary regions + 41 pre-mortem metastasis regions + 352 autopsy metastasis regions from 233 distinct metastatic sites
- **Coverage**: 70% of radiologically detected metastases had WES data
- **Subclone classification**: truncal → primary-unique → shared subclonal → metastasis-unique
- **Phylogenetic reconstruction**: per-patient evolutionary trees integrating somatic mutations, SCNAs, and WGD events

## Results
| Metric | Value |
|---|---|
| Patients with multi-subclone dissemination | 62.5% |
| Metastases seeded by other metastases | >50% |
| Metastasis-unique subclones per patient (median) | 28 (vs. 2.5 in prior single-biopsy TRACERx) |
| Intra-metastasis subclones (median) | 7 per metastasis |
| Metastases with unique subclone not in any other site | 79% |

## Related Papers
- [[overviews/]] — TRACERx primary NSCLC multi-region profiling studies (Jamal-Hanjani et al.)

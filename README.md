# Molecular resilience to smoking-induced lung cancer

Cancer Bioinformatics (Prof. Yosef Maruvka), Technion, Winter 2026/27 — final project.

## Research question

Is there a reproducible gene-expression signature of resilience to smoking: genes whose
response to smoking differs between smokers who stay cancer-free and smokers who develop
lung cancer, and does it hold across independent cohorts and tissues?

## Datasets

| Role | Dataset | Tissue | Owner |
|---|---|---|---|
| Discovery | GSE4115 (Spira) | Bronchial airway epithelium | Afik |
| Replication | GSE66499 (AEGIS) | Bronchial airway epithelium | Afik |
| Replication | Spira small set (cancer / no cancer / never smokers) | Bronchial airway epithelium | Afik |
| Smoking baseline | Crystal lab airway set (e.g. GSE4498) | Small airway epithelium | Ben |
| Cross-tissue | GTEx lung RNA-seq | Lung, cancer-free donors | Ben |
| Cross-tissue | TCGA LUAD/LUSC normal + tumor | Lung | Ben |

## Folder layout

```
data/raw/            downloaded data, never committed (see .gitignore)
data/processed/      normalized matrices + phenotype tables, never committed
scripts/airway/      GEO airway datasets: download, QC, differential expression
scripts/lung_tissue/ GTEx, TCGA, Crystal: download, QC, smoking-response DE
scripts/integration/ correlation, meta-analysis, signature, GSEA, cross-tissue
results/             result tables (gene, logFC, t, p, FDR, n per group)
figures/             plots for the presentations
docs/literature/     paper summaries and the novelty memo
presentations/       initial and final slides
```

## Conventions

- Every differential-expression script writes the standard results table:
  `gene, logFC, t, p, FDR, n_group1, n_group2`.
- Scripts are numbered in run order, e.g. `01_download_GSE4115.R`, `02_qc_GSE4115.R`.
- Both partners must be able to explain every script (individual code questioning).

## Task list

Live task tracker (source of truth): https://claude.ai/artifact/ShSM6iNhgY7f87aUZUKAuz
Snapshot in this repo: docs/task_list.md and docs/task_list.csv

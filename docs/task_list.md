# Project task list

Snapshot of the live task tracker (https://claude.ai/artifact/ShSM6iNhgY7f87aUZUKAuz), taken 2026-11-19.
Update statuses in the live sheet; this file is a copy for reference.

Owners: **Afik** = airway track (GEO airway datasets) · **Ben** = lung-tissue track (GTEx, TCGA, Crystal) · **Both** = shared work.


## 0 · Setup

| # | Task | Owner | Due | Status | Depends on | Done when / notes |
|---|---|---|---|---|---|---|
| 1 | Book the initial presentation slot (Fri Dec 4) in the course slots sheet | Both | 2026-11-21 | To do |  | Your names entered in a free slot. |
| 2 | Book the final presentation slot (Mar 17–18) | Both | 2026-11-21 | To do |  | Book early while slots are open. |
| 3 | Fix a weekly sync time (30 min) and a shared chat/notes channel | Both | 2026-11-21 | To do |  | Recurring meeting in both calendars. |
| 4 | Create a shared GitHub repo with folders: data/raw, data/processed, scripts, results, figures | Afik | 2026-11-22 | To do |  | Ben can clone and push. Add a README with the folder layout. Keep raw data out of git. |
| 5 | Set up a shared R environment (renv): GEOquery, limma, affy/oligo, edgeR, TCGAbiolinks, metafor, fgsea, msigdbr | Ben | 2026-11-22 | To do | 4 | renv.lock committed; both can restore it on their own laptop. |
| 6 | Shared reference library (Zotero group or a shared folder) | Ben | 2026-11-22 | To do |  | Every paper you read goes in here. |

## 1 · Literature

| # | Task | Owner | Due | Status | Depends on | Done when / notes |
|---|---|---|---|---|---|---|
| 7 | Read Spira 2007 (Nat Med, GSE4115) and Silvestri 2015 (NEJM, AEGIS): what they compared, which genes/pathways they found | Afik | 2026-11-25 | To do |  | Half-page summary in the repo: design, n, findings, what they did NOT test. |
| 8 | Read Huang 2022 (Nat Genet), Li 2024 (AJHG) and Beane 2007 (smoking reversibility in airway) | Ben | 2026-11-25 | To do |  | Half-page summary each, same format. |
| 9 | PubMed/Scholar novelty search: resilience/resistance of smokers, NRF2 + airway + lung cancer, meta-analysis of airway transcriptome | Both | 2026-11-26 | To do | 7, 8 | Split the queries. Log every query and the relevant hits in one table. |
| 10 | Write a one-paragraph novelty memo: what is already done, where the gap is | Both | 2026-11-27 | To do | 9 | This becomes the 'why is this new' slide. |
| 11 | Finalize the research question and 2–3 hypotheses (H1 cross-cohort concordance; H2 defense pathways weaker in smokers with cancer) | Both | 2026-11-28 | To do | 10 | Question written in one sentence that both of you agree on. |

## 2 · Data

| # | Task | Owner | Due | Status | Depends on | Done when / notes |
|---|---|---|---|---|---|---|
| 12 | Download GSE4115 (series matrix + CEL files); extract phenotypes: cancer status, smoking status, pack-years, age, sex | Afik | 2026-11-30 | To do | 5 | Clean phenotype table saved to data/processed. |
| 13 | Download GSE66499 (AEGIS) and extract the same phenotypes | Afik | 2026-12-02 | To do | 12 | Same phenotype table format as GSE4115. |
| 14 | Find the GEO accession of Spira's small set (20 cancer / 24 no cancer / 8 never smokers) and download it | Afik | 2026-12-02 | To do | 12 | Accession confirmed and data downloaded. |
| 15 | Check for patient overlap between the Spira/AEGIS datasets (IDs, ages, dates, sample names) | Afik | 2026-12-03 | To do | 13, 14 | Overlapping samples listed and removed from replication sets. |
| 16 | GTEx lung RNA-seq: download counts and public annotations; check whether smoking status is public or dbGaP-only | Ben | 2026-11-30 | To do | 5 | Answer to: do we have smoking labels for GTEx lung? |
| 17 | If GTEx smoking is controlled: email Prof. Maruvka about dbGaP access or an alternative | Ben | 2026-11-30 | To do | 16 | Decision recorded: use GTEx with labels, without labels, or drop it. |
| 18 | TCGA LUAD/LUSC: download RNA-seq counts (tumor + normal) and clinical data (tobacco history, pack-years) via TCGAbiolinks | Ben | 2026-12-02 | To do | 5 | Count matrix + clinical table; number of normal samples with smoking data noted. |
| 19 | Download a healthy-smoker airway dataset from the Crystal lab (e.g. GSE4498 or a larger one) as the smoking baseline | Ben | 2026-12-02 | To do | 5 | Smokers vs never smokers, no cancer. |
| 20 | Build the dataset inventory table: n per group, platform, tissue, covariates available | Both | 2026-12-03 | To do | 12–19 | One table; goes straight into the initial presentation. |

## 3 · Initial talk

| # | Task | Owner | Due | Status | Depends on | Done when / notes |
|---|---|---|---|---|---|---|
| 21 | Prepare initial presentation slides: question, novelty, datasets, analysis plan, expected results | Both | 2026-12-02 | To do | 11, 20 | About 8–10 slides for 15 minutes. |
| 22 | Rehearse the initial presentation once, timed | Both | 2026-12-03 | To do | 21 | Under 12 minutes, leaving time for questions. |
| 23 | Give the initial presentation (Zoom) | Both | 2026-12-04 | To do | 22 |  |
| 24 | Write down the feedback and update the plan and this task list | Both | 2026-12-08 | To do | 23 | Changes reflected in this sheet. |

## 2 · Data

| # | Task | Owner | Due | Status | Depends on | Done when / notes |
|---|---|---|---|---|---|---|
| 25 | QC + normalization of the airway datasets (RMA), PCA, outlier and batch check | Afik | 2026-12-10 | To do | 13, 15 | QC report with PCA plots; list of removed samples and why. |
| 26 | QC + normalization of GTEx/TCGA/Crystal (TMM + voom for RNA-seq, RMA for arrays), PCA, outliers | Ben | 2026-12-10 | To do | 16–19 | Same QC report format. |

## 4 · DE per dataset

| # | Task | Owner | Due | Status | Depends on | Done when / notes |
|---|---|---|---|---|---|---|
| 27 | Agree on a standard results-table format: gene, logFC, t, p, FDR, n per group | Both | 2026-12-15 | To do | 24 | Template file in the repo; every DE script writes this format. |
| 28 | Map probes to gene symbols for all array platforms; define the shared gene universe | Afik | 2026-12-15 | To do | 25, 26 | List of genes measured in all datasets. |
| 29 | limma DE in GSE4115: cancer vs no cancer, adjusted for age, sex, pack-years, current/former smoking | Afik | 2026-12-20 | To do | 27, 28 | Results table + volcano plot. |
| 30 | limma DE in GSE66499 with the same model | Afik | 2026-12-24 | To do | 29 | Results table + volcano plot. |
| 31 | Smoking-response DE (smokers vs never smokers) in the Crystal airway set and in GTEx lung | Ben | 2026-12-24 | To do | 26, 27 | Two results tables: the smoking response in people without cancer. |
| 32 | TCGA normal lung: smoking DE (by pack-years or heavy vs light) | Ben | 2026-12-28 | To do | 26, 27 | Results table; note the small n. |

## 5 · Cross-dataset

| # | Task | Owner | Due | Status | Depends on | Done when / notes |
|---|---|---|---|---|---|---|
| 33 | Spearman correlation of logFC between cohorts + scatter plots | Afik | 2027-01-07 | To do | 29–32 | Correlation matrix figure with p-values. |
| 34 | Direction concordance of top genes + overlap enrichment (hypergeometric test) | Ben | 2027-01-07 | To do | 29–32 | % concordant direction and overlap p-value for each dataset pair. |
| 35 | Build a gene signature in GSE4115 and test it in GSE66499 (AUC) | Afik | 2027-01-14 | To do | 30 | ROC curve and AUC in the held-out cohort. |
| 36 | Meta-analysis per gene (Stouffer, or random effects with metafor) + heterogeneity (I²) | Ben | 2027-01-14 | To do | 29–32 | Ranked meta-analysis table of consistent genes. |
| 37 | Sensitivity analyses: current vs former smokers, excluding COPD, with and without overlapping samples | Both | 2027-01-21 | To do | 33–36 | Do the main results hold? One summary table. |

## 6 · Resilience

| # | Task | Owner | Due | Status | Depends on | Done when / notes |
|---|---|---|---|---|---|---|
| 38 | Resilience model: smoking-response genes (vs never smokers) with a different response in smokers with vs without cancer (interaction term) | Afik | 2027-01-28 | To do | 31, 36 | List of candidate 'resilience' genes. |
| 39 | GSEA (fgsea) on Hallmark/Reactome; focus on NRF2, DNA repair, xenobiotic metabolism, immune pathways | Ben | 2027-01-28 | To do | 36, 38 | Pathway table + enrichment plots. |
| 40 | Interpret the top genes and pathways against the literature | Both | 2027-02-04 | To do | 38, 39 | One page of biological interpretation. |

## 7 · Cross-tissue

| # | Task | Owner | Due | Status | Depends on | Done when / notes |
|---|---|---|---|---|---|---|
| 41 | Score the signature in GTEx lung: does it differ between smokers and never smokers without cancer? | Ben | 2027-02-11 | To do | 17, 38 | Boxplots + test. Skip if GTEx smoking labels are unavailable. |
| 42 | Score the signature in TCGA normal lung vs GTEx lung | Afik | 2027-02-11 | To do | 38 | Boxplots + test; mention batch/platform caveats. |
| 43 | Summarize what replicates and what does not across cohorts and tissues | Both | 2027-02-15 | To do | 37, 41, 42 | One summary figure for the final talk. |

## 8 · Code review

| # | Task | Owner | Due | Status | Depends on | Done when / notes |
|---|---|---|---|---|---|---|
| 44 | Afik walks Ben through the airway pipeline (tasks 12–15, 25, 28–30, 33, 35, 38, 42) | Both | 2027-02-18 | To do | 43 | Ben can explain every script. |
| 45 | Ben walks Afik through the lung-tissue pipeline (tasks 16–19, 26, 31–32, 34, 36, 39, 41) | Both | 2027-02-18 | To do | 43 | Afik can explain every script. |
| 46 | Each of you re-runs the other's scripts from scratch on your own laptop | Both | 2027-02-25 | To do | 44, 45 | Same results reproduced; fix anything that breaks. |

## 9 · Final talk

| # | Task | Owner | Due | Status | Depends on | Done when / notes |
|---|---|---|---|---|---|---|
| 47 | Finalize all figures in one consistent style | Afik | 2027-03-01 | To do | 43 | Figures folder ready for the slides. |
| 48 | Draft the final slide deck (25 minutes) | Ben | 2027-03-05 | To do | 47 | Full draft deck. |
| 49 | Write the limitations slide: 1-year follow-up, platform differences, confounders, sample overlap | Both | 2027-03-05 | To do | 48 |  |

## 8 · Code review

| # | Task | Owner | Due | Status | Depends on | Done when / notes |
|---|---|---|---|---|---|---|
| 50 | Mock Q&A: each of you questions the other on any script (as in the 5-minute individual questioning) | Both | 2027-03-10 | To do | 46 | Both can answer 'what does this line do and why' for all code. |

## 9 · Final talk

| # | Task | Owner | Due | Status | Depends on | Done when / notes |
|---|---|---|---|---|---|---|
| 51 | Two full timed rehearsals | Both | 2027-03-14 | To do | 48, 49 | Under 22 minutes, leaving time for questions. |
| 52 | Final presentation (in person) | Both | 2027-03-17 | To do | 51 | Date depends on the slot booked in task 2. |

## Chapter 1: AI/ML Lifecycle Foundations and Data Pipeline Controls — Flashcards

| # | Front (Question) | Back (Answer) |
|---|-----------------|---------------|
| 1 | What are the 4 stages of the AI/ML lifecycle tested on AAIA? | Data → Train → Deploy → Monitor. Exam tip: each stage maps to distinct controls — data=quality/lineage, train=split integrity, deploy=access control, monitor=drift detection. |
| 2 | Data lineage vs data provenance — difference? | Lineage = full transformation/flow history of data through a pipeline. Provenance = record of origin/source and ownership. Exam tests both terms separately — don't conflate them. |
| 3 | Common train/validation/test split ratio for moderate-size datasets | 70/15/15 (80/10/10 for very large datasets). Exam tip: as dataset size grows, val/test percentage can shrink while absolute record counts stay large enough for reliable evaluation. |
| 4 | Cohen's kappa interpretation scale for annotator agreement | <0.20 poor, 0.21–0.40 fair, 0.41–0.60 moderate, 0.61–0.80 substantial, 0.81–1.0 almost perfect. Exam tip: kappa below ~0.4 signals a labeling guideline/training failure requiring remediation before use. |
| 5 | Three data quality dimensions heavily tested | Completeness (required fields present), Accuracy (values correct), Timeliness (data current). Exam tip: match the scenario keyword ('missing field', 'wrong value', 'stale data') to the correct dimension. |
| 6 | Primary cause of data leakage between train/test splits | Duplicate/overlapping records across splits, temporal overlap, or features derived from target/future information. Exam tip: red flag = validation accuracy far exceeds production accuracy. |
| 7 | Best control to keep PII out of training data | An automated PII detection/redaction gate enforced BEFORE data enters the training set — a preventive control, not manual post-hoc review. Exam tip: 'automated preventive gate' beats 'manual detective review' answers. |
| 8 | Command to version a dataset with DVC | `dvc add data/train.csv` then commit the generated .dvc file with git. Exam tip: DVC ties a dataset version to a git commit hash, giving traceable lineage. |
| 9 | Correct control for sampling bias in demographic-sensitive training data | Stratified sampling across relevant subgroups. Exam tip: 'just collect more data from the same source' is the wrong-answer trap — it doesn't fix underrepresentation. |
| 10 | Access control principle for training data stores | Least privilege + role-based access + audit logging of who accessed/exported training datasets. Exam tip: exam favors layered controls (RBAC + logging) over a single isolated control. |
| 11 | ETL vs ELT in an AI data pipeline | ETL = transform before load (cleanse/label pre-storage). ELT = load raw data first, transform on demand. Exam tip: ELT requires stronger transform-logic versioning since raw data is stored unmodified. |
| 12 | Artifact an auditor expects as proof of data provenance | A dataset datasheet/lineage record documenting source, collection method, consent basis, version, and transformations applied. Exam tip: its absence is a commonly tested audit finding. |

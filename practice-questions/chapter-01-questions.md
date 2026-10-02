## Chapter 1: AI/ML Lifecycle Foundations and Data Pipeline Controls — Practice Questions

**Q1.** An audit of a credit-risk model finds that 40% of records in the test set are duplicates (same customer, same time window) of records in the training set. Model accuracy on test is 97%, but production accuracy is 71%. What control failure BEST explains this gap?

A) Data leakage caused by improper train/test split integrity
B) Insufficient model complexity
C) Incorrect labeling annotation guidelines
D) Missing PII redaction in the training pipeline

<details>
<summary>Answer</summary>

**Correct: A**

Duplicate records across train and test sets is a textbook data leakage scenario; the model memorizes samples it later sees again, producing inflated test metrics that collapse in production.

**Why the others are wrong:**
- Model complexity doesn't explain the specific test/production score divergence caused by overlapping records
- Labeling guideline issues affect label correctness, not record duplication across splits
- PII redaction is unrelated to duplicate-record contamination between splits

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q2.** A vendor-annotated sentiment-labeling project reports a Cohen's kappa of 0.35 between two annotators. Which action should the AI operations team take before using these labels for training?

A) Retrain annotators and revise the labeling guidelines, then re-measure agreement
B) Accept the labels since kappa above 0 indicates agreement
C) Discard human labels entirely and use rule-based heuristics instead
D) Add more annotators without changing the guidelines

<details>
<summary>Answer</summary>

**Correct: A**

Kappa of 0.35 falls in the 'fair' range, indicating unreliable guidelines or annotator understanding; the correct remediation is guideline revision and retraining before re-measuring agreement.

**Why the others are wrong:**
- Kappa above 0 is not a sufficient threshold; 0.35 is well below acceptable agreement levels for training data
- Abandoning human labels is an overcorrection, not a targeted quality-control fix
- Adding annotators without fixing guidelines does not address the root cause of disagreement

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q3.** During a model audit, the reviewer cannot determine which version of a source dataset was used to train the currently deployed production model. Which control is missing?

A) Data lineage and provenance documentation
B) Model monitoring and drift detection
C) Data access control policy
D) Hyperparameter tuning logs

<details>
<summary>Answer</summary>

**Correct: A**

The inability to trace which dataset version fed a specific model is the defining symptom of missing data lineage/provenance documentation.

**Why the others are wrong:**
- Drift detection concerns post-deployment performance changes, not dataset traceability
- Access control governs who can view/modify data, not which version was used
- Hyperparameter logs relate to model training configuration, not data versioning

</details>

---

**Q4.** Which control BEST prevents personally identifiable information (PII) from entering a model's training dataset?

A) Manual quarterly review of a sample of training records
B) Encrypting the training dataset at rest
C) Automated PII detection and redaction enforced as a gate in the data pipeline before the training set is assembled
D) Logging all reads and writes to the training data store

<details>
<summary>Answer</summary>

**Correct: C**

A preventive, automated gate that scans and redacts PII before data reaches the training set stops the problem at the source, rather than detecting it after the fact.

**Why the others are wrong:**
- Manual sampling is a detective control that misses most records and occurs too infrequently
- Encryption at rest protects data confidentiality but does not remove PII from the training set
- Access logging is detective, not preventive, and does not stop PII from being ingested

</details>

---

**Q5.** A team building a facial recognition model collected training images almost entirely from one geographic region and age group. What is the BEST control to address this?

A) Increase total dataset size by scraping more images from the same sources
B) Apply data augmentation (rotation, cropping) to existing images
C) Apply stratified sampling to ensure balanced representation across demographic subgroups
D) Reduce the dataset size to speed up training

<details>
<summary>Answer</summary>

**Correct: C**

Stratified sampling directly targets underrepresented subgroups, correcting the collection bias rather than amplifying the existing skew.

**Why the others are wrong:**
- Scraping more data from the same biased sources reinforces the existing imbalance rather than fixing it
- Augmentation transforms existing images but does not add missing demographic diversity
- Reducing dataset size does not address representation imbalance at all

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q6.** For a moderately sized labeled dataset, which split configuration reflects standard practice for training, validation, and test sets respectively?

A) 70% / 15% / 15%
B) 33% / 33% / 33%
C) 100% / 0% / 0%
D) 50% / 50% / 0%

<details>
<summary>Answer</summary>

**Correct: A**

70/15/15 is the widely used convention for moderate dataset sizes, leaving enough data for training while reserving adequate held-out sets for tuning and final evaluation.

**Why the others are wrong:**
- Equal thirds leaves too little data for training and is not standard practice
- Using 100% for training leaves no held-out data to validate or test generalization
- A 50/50 split with no test set removes the ability to perform an unbiased final evaluation

</details>

---

**Q7.** A monthly audit finds that 22% of customer records used for training are missing the 'income' field entirely. Which data quality dimension is being violated?

A) Timeliness
B) Accuracy
C) Completeness
D) Consistency

<details>
<summary>Answer</summary>

**Correct: C**

Completeness measures whether required fields are present for each record; missing values in a required field is a direct completeness violation.

**Why the others are wrong:**
- Timeliness concerns whether data is current/up to date, not whether fields are missing
- Accuracy concerns whether present values are correct, not whether values exist
- Consistency concerns whether data agrees across sources/formats, not field presence

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q8.** Which statement BEST describes data lineage in the context of the AI/ML lifecycle?

A) A record of who is authorized to access a dataset
B) The documented history of a dataset's origin, transformations, and movement through a pipeline
C) A performance metric measuring model drift over time
D) The encryption method applied to data at rest and in transit

<details>
<summary>Answer</summary>

**Correct: B**

Data lineage is defined as the traceable history of data as it originates and moves/transforms through pipeline stages.

**Why the others are wrong:**
- Authorization records describe access control, a related but distinct control
- Drift measurement is a monitoring concept, not a lineage concept
- Encryption method is a security control unrelated to tracing data history

</details>

---


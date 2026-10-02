## Chapter 2: Model Development, Training, and Evaluation Audit Evidence — Practice Questions

**Q1.** An auditor reviewing a fraud detection model finds the dataset is 99% legitimate transactions and 1% fraud. The development team reports 99% accuracy as the primary evaluation metric with no other metrics logged. What should the auditor flag as the PRIMARY documentation gap?

A) Accuracy was not computed on the training set
B) The model was not retrained on a balanced dataset
C) The confusion matrix was not converted to a ROC curve
D) No precision, recall, or F1 score was recorded, so model performance on the minority (fraud) class cannot be verified

<details>
<summary>Answer</summary>

**Correct: D**

On a 99/1 imbalanced dataset, a model predicting 'legitimate' every time achieves 99% accuracy while catching zero fraud. Precision/recall/F1 on the minority class is the missing audit evidence needed to assess real performance.

**Why the others are wrong:**
- Training accuracy isn't the audit concern here — accuracy itself is the wrong metric regardless of split
- Rebalancing is a possible remediation, not the documentation gap being audited
- ROC/AUC could help but converting the matrix isn't the core missing evidence — the metrics were never computed at all

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q2.** A model card submitted for audit lists model architecture, intended use, and performance metrics, but omits information on the demographic groups used in training/testing data and known performance disparities across those groups. Per standard model card practice (Mitchell et al.), which section is missing?

A) Quantitative Analyses / Ethical Considerations and disaggregated performance by subgroup
B) Model Details
C) Intended Use
D) Training Data source URL

<details>
<summary>Answer</summary>

**Correct: A**

The Model Cards framework requires disaggregated evaluation results across factors (e.g., demographic groups) and an ethical considerations/limitations section — this is what's missing.

**Why the others are wrong:**
- Model Details (architecture, version, type) was already provided per the scenario
- Intended use was already provided
- A source URL is part of the datasheet, not the disaggregated performance requirement being tested

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q3.** A data science team needs to log hyperparameters, metrics, and model artifacts across hundreds of training runs so an auditor can trace which configuration produced the deployed model. Which capability BEST satisfies this audit requirement?

A) A shared spreadsheet updated manually after each run
B) An experiment tracking tool (e.g., MLflow, Weights & Biases) that automatically logs parameters, metrics, and artifact lineage per run
C) Storing final model weights only, in a single folder named 'final_model'
D) Code comments describing what hyperparameters were tried

<details>
<summary>Answer</summary>

**Correct: B**

Experiment tracking platforms automatically capture run-level parameters, metrics, and artifact lineage, giving auditors a reproducible, tamper-resistant trail — manual methods are error-prone and unverifiable.

**Why the others are wrong:**
- Manual spreadsheets are error-prone, not tamper-evident, and easily fall out of sync
- Storing only final weights loses the record of which configuration and run produced them
- Code comments are not systematic, versioned, or queryable evidence

</details>

---

**Q4.** During an audit, you find a team used 3-fold cross-validation on a dataset of only 300 samples with 50 features, then reported a single held-out test score with no variance reported across folds. What is the MOST significant audit concern?

A) With a small sample size and high feature count, low fold count and missing variance reporting increase risk of undetected overfitting and unstable performance estimates
B) 3-fold cross-validation is never acceptable regardless of dataset size
C) Cross-validation should only be used for deep learning models
D) The test set should have been discarded entirely

<details>
<summary>Answer</summary>

**Correct: A**

Small n with high dimensionality is a classic overfitting risk; low fold counts and lack of variance reporting hide instability across folds, which is exactly what audit evidence for cross-validation should surface.

**Why the others are wrong:**
- 3-fold CV is contextually acceptable for larger datasets — it's not universally wrong
- Cross-validation applies to all model types, not just deep learning
- A held-out test set is still good practice; the issue is missing variance reporting, not the test set's existence

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q5.** Which metric is BEST suited to summarize a binary classifier's ranking ability across all possible classification thresholds?

A) F1 score at threshold 0.5
B) Raw accuracy
C) Mean squared error
D) AUC-ROC (Area Under the ROC Curve)

<details>
<summary>Answer</summary>

**Correct: D**

AUC-ROC evaluates ranking/discrimination performance across all thresholds (0 = worst, 0.5 = random, 1.0 = perfect), independent of any single decision threshold.

**Why the others are wrong:**
- F1 at 0.5 only evaluates one fixed threshold, not overall ranking capability
- Accuracy is threshold- and class-balance-dependent, not a ranking metric
- MSE is a regression metric, not applicable to binary classification

</details>

---

**Q6.** An auditor cannot reproduce a model's reported test accuracy because the training script references a dataset file that was later modified, and no version tag exists for the code, data, or environment used. Which control failure does this represent?

A) Lack of model versioning and reproducibility controls (data, code, and environment lineage)
B) Insufficient feature engineering documentation
C) Incorrect hyperparameter tuning method
D) Missing datasheet for the dataset

<details>
<summary>Answer</summary>

**Correct: A**

The core failure is that data, code, and environment were not version-controlled together, so the exact conditions producing the reported result cannot be reconstructed — a reproducibility control gap.

**Why the others are wrong:**
- Feature engineering documentation is a related but narrower issue, not the core failure described
- Hyperparameter tuning method isn't implicated here — the issue is lineage tracking
- A datasheet describes dataset composition/provenance but wouldn't by itself fix version drift

</details>

---

**Q7.** A team engineered 40 new features by combining raw fields (e.g., ratio of income to debt) but kept no record of the transformation logic or rationale. Why is this a material audit gap?

A) Feature engineering never needs documentation once the model is trained
B) Without a feature engineering audit trail, auditors cannot verify data lineage, detect leakage, or assess whether engineered features introduce bias or invalid proxies
C) Only hyperparameters require audit trails, not features
D) Feature engineering only matters for image models

<details>
<summary>Answer</summary>

**Correct: B**

Undocumented derived features can hide data leakage (e.g., using post-outcome information) or proxy variables for protected attributes, both of which are key audit risks the trail is meant to surface.

**Why the others are wrong:**
- Documentation is required precisely because trained models can't reveal transformation logic after the fact
- Hyperparameters and features are both part of required audit evidence, not one exclusively
- Feature engineering audit trails apply across model types, not just image models

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q8.** Per the 'Datasheets for Datasets' framework, which question is a dataset creator expected to answer that a model card does NOT typically cover?

A) How was the data collected, and were consent and licensing considerations addressed?
B) What is the model's F1 score on the test set?
C) What hyperparameters were used during training?
D) What is the model's intended use case?

<details>
<summary>Answer</summary>

**Correct: A**

Datasheets focus on dataset provenance — collection process, consent, licensing, composition, and known limitations — distinct from model cards, which focus on model performance and intended use.

**Why the others are wrong:**
- F1 score is model card territory (performance evaluation)
- Hyperparameters are experiment tracking/model documentation, not dataset documentation
- Intended use is a model card section, not a datasheet section

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---


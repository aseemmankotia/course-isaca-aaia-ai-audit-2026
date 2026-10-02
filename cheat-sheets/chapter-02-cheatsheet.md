# Chapter 2 Cheat Sheet: Model Dev, Training & Evaluation Audit Evidence

## Exam Domain: AI Operations (46% weight)

### Evaluation Metrics — Formulas
| Metric | Formula | Use When |
|---|---|---|
| Precision | TP/(TP+FP) | False positives costly (e.g., spam) |
| Recall | TP/(TP+FN) | False negatives costly (e.g., fraud, cancer screening) |
| F1 | 2×(P×R)/(P+R) | Need balance, imbalanced classes |
| AUC-ROC | Area under TPR vs FPR curve | Threshold-independent ranking quality; 0.5=random, 1.0=perfect |
| Accuracy | (TP+TN)/All | Only valid on balanced classes — audit trap on imbalanced data |

**Exam trap:** High accuracy + imbalanced dataset + no precision/recall/F1 logged = red flag. A 99%-accuracy model can still catch 0% of the minority class.

### Cross-Validation Controls
- Common folds: **k=5** or **k=10** (standard defaults)
- Small dataset + high dimensionality + low k = overfitting risk
- Audit evidence must include: fold-by-fold scores + variance, not just mean
- Learning curves (train vs. val over epochs/iterations) reveal overfitting gaps

### Documentation Frameworks
| Framework | Documents | Key Sections |
|---|---|---|
| Model Card (Mitchell et al., 2019) | The MODEL | Details, Intended Use, Factors, Metrics, Evaluation/Training Data, Quantitative Analyses, Ethical Considerations, Caveats |
| Datasheet (Gebru et al., 2018) | The DATASET | Motivation, Composition, Collection Process, Preprocessing, Uses, Distribution, Maintenance |

**Exam trap:** Confusing model card content (performance) with datasheet content (provenance/consent/licensing) — they are complementary, not interchangeable.

### Experiment Tracking & Reproducibility
- Tools: **MLflow** (Tracking + Model Registry with stage transitions), **Weights & Biases**, **DVC** (data/model version control), **Neptune.ai**, **TensorBoard**
- MLflow logging: `mlflow.log_param()`, `mlflow.log_metric()`, `mlflow.log_artifact()`
- Reproducibility requires linked versions of: **code (Git) + data (DVC) + environment (Docker/conda lock)**
- Audit red flag: dataset file modified after training with no version tag → result cannot be reproduced

### Hyperparameter Tuning Methods
| Method | Characteristic |
|---|---|
| Grid Search | Exhaustive, expensive, guarantees coverage of defined grid |
| Random Search | Efficient at scale, samples randomly from space |
| Bayesian Optimization | Sample-efficient, models search space based on prior results |

Audit evidence must show: search method, search space/bounds, and selection rationale — not just the final hyperparameter values.

### Feature Engineering Audit Trail
- Document transformation logic and rationale for every derived feature
- Absence of trail → risk of undetected **data leakage** (post-outcome info) or **proxy variables** for protected attributes

### Regulatory Anchors (2026)
- **EU AI Act Article 11**: technical documentation for high-risk AI systems
- **NIST AI RMF 1.0**: Govern/Map/Measure/Manage functions
- **ISO/IEC 42001:2023**: AI management system requirements

**Common mistake:** Treating model versioning, experiment tracking, and documentation (model card/datasheet) as one artifact — they serve distinct, complementary audit purposes.

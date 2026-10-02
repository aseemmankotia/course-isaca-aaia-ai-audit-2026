## Chapter 1 Cheat Sheet — AI/ML Lifecycle & Data Pipeline Controls

### Lifecycle Stages → Primary Control Focus
| Stage | Control Focus |
|---|---|
| Data | Quality, lineage, provenance, PII handling |
| Train | Split integrity, leakage prevention, labeling QA |
| Deploy | Access control, versioning, approval gates |
| Monitor | Drift detection, performance/quality alerting |

### Data Quality Dimensions
| Dimension | Definition | Violation Symptom |
|---|---|---|
| Completeness | Required fields present | Missing values in required fields |
| Accuracy | Values reflect reality | Wrong/incorrect values recorded |
| Timeliness | Data is current | Stale data used for decisions |
| Consistency | Agreement across sources/formats | Conflicting values across systems |

### Cohen's Kappa Scale (Labeling Agreement)
| Kappa Range | Interpretation |
|---|---|
| < 0.20 | Poor |
| 0.21–0.40 | Fair (needs remediation) |
| 0.41–0.60 | Moderate |
| 0.61–0.80 | Substantial |
| 0.81–1.00 | Almost perfect |

### Standard Split Conventions
| Dataset Size | Train/Val/Test |
|---|---|
| Small–moderate | 70/15/15 |
| Large | 80/10/10 |

### Lineage vs Provenance
| Term | Meaning |
|---|---|
| Lineage | Full transformation/flow history through pipeline |
| Provenance | Origin, source, ownership record |

### Data Leakage Red Flags
- Duplicate records across train/test splits
- Temporal overlap (future data leaking into training)
- Features derived from the target variable
- Symptom: test/validation metrics far exceed production metrics

### PII Handling Control Hierarchy (Preventive > Detective)
1. Automated PII detection/redaction gate pre-ingestion (preventive — best)
2. Access control + audit logging (detective/limiting)
3. Manual periodic review (detective — weakest)

### Sampling Bias Fix
- Wrong answer trap: "collect more data from the same source"
- Correct approach: stratified sampling across demographic/relevant subgroups

### ETL vs ELT
| | Transform Timing | Lineage Implication |
|---|---|---|
| ETL | Before load | Cleansed/labeled data stored |
| ELT | After load (on demand) | Must version transform logic separately from raw data |

### Key Exam Callouts
- Missing dataset-version traceability to a model = lineage/provenance control gap, not a monitoring gap.
- Kappa below ~0.4 on labeling = guideline/training failure, not an acceptable-quality label set.
- "Automated pipeline gate" answers outrank "manual review" answers for PII and quality questions.

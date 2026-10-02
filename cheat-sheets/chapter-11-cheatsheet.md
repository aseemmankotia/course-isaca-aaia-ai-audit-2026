## Chapter 11 Cheat Sheet: Bias, Fairness, Explainability & Vendor Assurance

### Fairness Metrics
| Metric | Definition | Conditions on Outcome? |
|---|---|---|
| Demographic parity | Equal selection/approval rate across groups | No |
| Disparate impact ratio | (lower group rate)/(higher group rate); four-fifths rule = fails if < 0.8 | No |
| Equal opportunity | Equal TPR across groups | Yes (positives only) |
| Equalized odds | Equal TPR AND FPR across groups | Yes (both) |

**Exam trap:** Demographic parity and disparate impact ratio ignore ground truth qualification — a model can satisfy them while still being 'unfair' in the equalized-odds sense, and vice versa.

### Explainability Techniques
| Technique | Scope | Basis | Best For |
|---|---|---|---|
| SHAP | Local + Global | Shapley values (game theory) | Consistent attribution, audit-defensible |
| LIME | Local only | Linear surrogate on perturbed samples | Fast single-prediction explanation |
| Feature importance (e.g., tree-based) | Global | Model-internal (e.g., Gini/split gain) | Overall model behavior, not individual decisions |
| Counterfactual explanation | Local | Minimal input change to flip outcome | Explaining adverse decisions, actionability |

### Model Provenance Checklist
- Training data source(s) and collection method
- Data licensing terms (commercial use rights, restrictions)
- Foundation model lineage (base model, fine-tuning steps, version)
- Known limitations/exclusions disclosed by provider

### Third-Party Vendor Assurance
| Evidence Type | What It Confirms |
|---|---|
| SOC 2 Type I | Control design at a point in time |
| SOC 2 Type II | Control design + operating effectiveness over a period |
| Vendor questionnaire | Self-reported practices (data handling, bias testing, security) |
| Contractual AI clauses | Audit rights, bias testing obligations, data usage limits, liability |

**Rule:** Vendor self-attestation (including vendor fairness reports) = supporting evidence only. Independent bias testing on representative data is required for audit sign-off.

### Reporting Findings
- Severity: Critical / High / Medium / Low (based on impact + likelihood)
- Every finding needs: root cause, remediation owner, target date, retest plan
- For black-box/foundation models: document input/output test logs, explanation samples (SHAP/LIME), fairness metric results, and stated testing limitations — since internal logic may be inaccessible.

### Key Formula
Disparate Impact Ratio = Selection Rate (protected group) ÷ Selection Rate (reference group)
Threshold: **< 0.8 → potential adverse impact (four-fifths rule)**

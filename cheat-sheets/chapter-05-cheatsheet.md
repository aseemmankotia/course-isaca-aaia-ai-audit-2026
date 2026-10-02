# AI Monitoring, Drift Detection & Model Performance Assurance

## Drift Detection Methods
| Method | Feature Type | What It Measures |
|---|---|---|
| PSI | Numerical (binned) | Population distribution shift; standard operational metric |
| KS Test | Numerical (continuous) | CDF difference between baseline & current samples |
| Chi-squared | Categorical | Frequency distribution shift |
| KL Divergence | Numerical/categorical | Asymmetric distribution difference, sensitive to tail changes |

## PSI Threshold Guide
| PSI Value | Interpretation | Action |
|---|---|---|
| < 0.1 | No significant shift | No action |
| 0.1–0.25 | Moderate shift | Investigate, monitor closely |
| > 0.25 | Significant shift | Trigger retraining review |

## Data Drift vs Concept Drift
| | Data Drift | Concept Drift |
|---|---|---|
| What changes | Input distribution P(X) | Relationship P(Y\|X) |
| Accuracy impact | May remain stable | Typically degrades |
| Detection method | PSI, KS test, Chi-squared | Performance metric tracking over time |

## Retraining Triggers
- **Scheduled** — fixed calendar cadence regardless of performance
- **Performance-triggered** — accuracy/precision/recall drops below threshold
- **Drift-triggered** — PSI/KS/Chi-squared exceeds threshold

## Continuous Monitoring vs Periodic Validation
| | Continuous Monitoring | Periodic Validation |
|---|---|---|
| Frequency | Real-time/ongoing | Scheduled (e.g., quarterly) |
| Depth | Lightweight metrics, alerting | Deep-dive vs full holdout dataset |
| Cost | Higher ongoing infra cost | Lower cost, detection lag |
| Use case | High-risk/regulated production | Supplementary governance check |

## Logging & Audit Trail — Required Fields
- Model version/ID
- Input data (or reference)
- Output/prediction + confidence score
- Timestamp
- Human override/review decision (if any)
- Alert/incident reference (if triggered)

## Human-in-the-Loop (HITL) Controls
- Routes low-confidence or high-risk outputs to a human reviewer
- Reviewer decision must be logged as part of the audit trail
- Distinct from monitoring: HITL is an *active override*, not passive observation

## Incident Management Steps (Order Matters)
1. Log & triage — assess severity/scope
2. Contain — restrict/flag affected outputs
3. Root cause analysis (drift? bug? adversarial input?)
4. Remediate (retrain, rollback, patch)
5. Post-incident review & documentation

## Common Exam Traps
- Confusing data drift (stable accuracy) with concept drift (degrading accuracy)
- Choosing "retrain immediately" when PSI is only in the moderate (0.1–0.25) band
- Picking continuous monitoring when the question specifically describes scheduled deep validation
- Forgetting human override decisions must be logged for audit purposes

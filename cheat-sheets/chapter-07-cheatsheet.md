## Chapter 7 Cheat Sheet: AI Risk Identification & Enterprise Risk Assessment

### AI Risk Taxonomy (6 core categories)
| Category | Example Risk |
|---|---|
| Bias/Fairness | Disparate impact in hiring/credit decisions |
| Robustness | Model fails on edge cases/adversarial input |
| Security | Prompt injection, model theft, adversarial attacks |
| Privacy | Training data memorization, re-identification |
| Explainability | Black-box decisions lacking rationale for regulators |
| Third-Party | Vendor model lacks bias testing/data provenance |

### NIST AI RMF 1.0 — Four Functions
| Function | Focus |
|---|---|
| Govern | Culture, policy, accountability (cross-cutting) |
| Map | Context, use case, risk identification |
| Measure | Quantify/qualify risks, test, track metrics |
| Manage | Respond, prioritize, allocate resources |

### EU AI Act Risk Tiers
| Tier | Examples | Obligation |
|---|---|---|
| Unacceptable | Social scoring, real-time public biometric ID | Prohibited |
| High-risk | Credit scoring, hiring, biometric categorization, critical infrastructure | Conformity assessment, docs, human oversight |
| Limited | Chatbots, deepfakes | Transparency/disclosure |
| Minimal | Spam filters, AI in video games | No mandatory obligation |

### Risk Scoring: Inherent vs Residual
- **Inherent Risk** = Likelihood × Impact BEFORE controls
- **Residual Risk** = Likelihood × Impact AFTER controls applied
- Controls reduce likelihood (e.g., human review) and/or impact (e.g., faster detection)
- Re-score residual risk after each control change — never treat as static

### Model Risk Management (MRM) for AI/ML — adapted from SR 11-7
| Traditional MRM Pillar | AI/ML Adaptation |
|---|---|
| Conceptual soundness review | + Training data quality & bias testing |
| Independent validation | + Explainability assessment (opaque models) |
| Ongoing monitoring | + Drift detection, retraining triggers |

### Emerging Generative AI Risks
| Risk | Description | Primary Mitigation |
|---|---|---|
| Hallucination | Plausible but false output | RAG + output validation/guardrails |
| Prompt Injection | Malicious instructions in input/content override system prompt | Input sanitization, sandboxing, instruction hierarchy enforcement |
| Data Poisoning | Corrupted training data skews behavior | Data provenance checks, anomaly detection in training pipeline |

### AI Risk Register — Required Fields (beyond standard ERM)
- Model/Use-Case ID
- AI Taxonomy Category (bias, robustness, security, privacy, explainability, third-party)
- Lifecycle Stage (dev, validation, deployment, monitoring)
- Human Oversight Control Reference
- Risk Tier (aligned to risk appetite statement)

### Risk Appetite Statement
- Executive/board-approved threshold for acceptable AI risk
- Example: "No fully autonomous high-stakes decision without human-in-the-loop review"
- Used to benchmark residual risk scores during tiering

### Exam Traps
1. Confusing inherent vs residual risk scoring (residual reflects controls, not a static score)
2. Misclassifying EU AI Act tiers — credit/hiring/biometric = high-risk, NOT limited
3. Treating disclaimers as a 'mitigation' for hallucination — it's risk acceptance, not control
4. Assuming vendor AI model risk is fully transferred — accountability for harm remains with the deploying org

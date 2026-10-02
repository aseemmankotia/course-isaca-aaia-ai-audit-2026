## Chapter 3 Cheat Sheet: MLOps/LLMOps Pipelines

### Pipeline Stages (order matters on exam)
| Stage | Purpose | Key Control |
|---|---|---|
| Build | Compile artifact, train/package model | Reproducible build via IaC + pinned dependencies |
| Test | Validate correctness, quality, fairness | Unit, integration, and bias/fairness gates — **must block promotion on failure** |
| Release | Approve version for production | Registry approval workflow, segregation of duties |
| Deploy | Ship to production | Champion/challenger or canary rollout, rollback plan ready |

### Testing Gate Types
| Gate | Checks | Fails Block? |
|---|---|---|
| Unit | Code logic correctness | Yes |
| Integration | Data/pipeline flow, upstream/downstream compatibility | Yes |
| Bias/Fairness | Protected-class outcome disparity vs. threshold | Yes — mandatory in Test stage |

### LLMOps-Specific Additions (beyond classic MLOps)
- **Prompt versioning**: prompts change behavior without retraining → version + approve + rollback independently.
- **Guardrails**: input/output moderation, PII redaction, jailbreak detection — version and test like code.
- **RAG controls**: version and access-control the retrieval/vector index separately; stale/poisoned index = distinct risk class from model drift.
- **Reproducible bundle** = model weights + tokenizer + prompt template + guardrail config, all tagged together.

### Deployment Strategies
| Strategy | Description | When to Use |
|---|---|---|
| Champion/Challenger | New version gets a small traffic slice; compare vs. current champion | Testing new model or prompt safely in prod |
| Canary | Gradual traffic ramp-up to new version | Lower-risk, incremental rollout |
| Blue/Green | Full parallel environments, instant switch | Need instant full cutover + instant rollback |
| Rollback | Revert to last approved registry version | Incident response — faster than retraining |

### Governance Controls
- **Model registry**: tracks version, lineage, approver identity, timestamp, test results — enables audit + rollback.
- **Segregation of duties**: builder (data scientist) ≠ sole approver (deployment/MLOps team) for production promotion.
- **IaC**: environment defined in version control, tagged to same release as model — no manual console setup.

### Common Exam Traps
- Placing bias/fairness testing in Deploy stage instead of Test stage (too late).
- Treating 'code review' as equivalent to segregation of duties (it is not — roles must differ).
- Assuming model rollback fixes a prompt-only incident (wrong artifact reverted).
- Confusing retraining (slow, days) with rollback (fast, registry-based) for incident response.
- Forgetting RAG's knowledge base/index needs its own versioning, separate from model version.

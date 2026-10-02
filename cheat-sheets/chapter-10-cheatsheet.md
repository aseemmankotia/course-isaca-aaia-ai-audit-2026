## Chapter 10 Cheat Sheet: Scoping & Control Testing Strategy

### Control Testing Techniques (Weakest → Strongest Evidence)
| Technique | What It Is | Evidence Strength | Use When |
|---|---|---|---|
| Inquiry | Asking process owner how control works | Weakest | Supplement only; never sole evidence for key controls |
| Observation | Watching control performed live | Low-Moderate | Point-in-time confirmation; misses history |
| Inspection | Examining existing documents/logs | Moderate-High | Confirms control operated over a period |
| Reperformance | Independently redoing the control | Strongest | High-risk/key quantitative controls (e.g., drift calc) |

**Exam rule:** high-risk/key controls require inspection + reperformance (or observation + inspection); inquiry alone is a trap answer.

### Risk-Based Scoping Logic
1. Build **AI audit universe** — inventory all models.
2. Tier by **inherent risk** (impact, likelihood, regulatory exposure — e.g., EU AI Act high-risk categories).
3. Allocate audit depth proportional to tier: High → full-scope testing; Medium → targeted testing; Low → light-touch/inquiry-based review.
4. Ownership by second-line/MRM does **not** remove a system from IA scope.

### Selecting Audit Criteria
| Source | Appropriate? | Why |
|---|---|---|
| NIST AI RMF / ISO/IEC 42001 | Yes | Recognized, tailorable framework |
| Internal AI policy | Yes, if tied to external regulation | Organization-specific baseline |
| Vendor self-attestation | No (sole source) | Not independent |
| Auditor's personal opinion | No | Not objective/defensible |

### Sampling Approaches
- **Stratified sampling** → use for subgroup/bias/representativeness testing (protects small subgroups from underrepresentation).
- **Simple random sampling** → use for homogeneous populations (e.g., general log review).
- **Judgmental sampling** → use for targeting known high-risk items (e.g., largest exceptions), not for statistical conclusions.

### Walkthroughs
- Purpose: build process understanding, trace data through pipeline, identify key controls/risks.
- NOT sufficient alone to conclude on operating effectiveness.

### Reliance on Second-Line/MRM Work
Before relying: assess **competence + objectivity + quality**, then **corroborate with independent testing**. Never accept blindly; never fully disregard without evaluation.

### Test Plan Documentation — Required Elements
1. Control objective
2. Testing technique(s) used
3. Sample size & selection method
4. Pass/fail criteria

**Exam gotcha:** Missing pass/fail criteria = incomplete test step, a frequently tested documentation defect.

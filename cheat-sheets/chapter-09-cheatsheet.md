# Ch.9 Cheat Sheet: Mapping AI Governance to Auditable Controls

## Policy → Control Translation
A policy statement is NOT a control until it defines: **Owner, Frequency, Trigger, Evidence Type, Pass/Fail Criterion**. Missing any element = gap.

## Control Type Comparison
| Type | Timing | Example | Evidence |
|---|---|---|---|
| Preventive | Before risk occurs | CI/CD bias gate blocks deploy | Blocked-build logs |
| Detective | After risk occurs | Drift monitoring alert | Alert + investigation log |
| Corrective | After detection | Auto-rollback of biased model | Remediation ticket |
| Compensating | Substitutes for missing primary control | Manual review when automated gate absent | Sign-off record |

## Control Frequency Mapping
| Requirement Language | Frequency Type |
|---|---|
| 'annually' / 'each fiscal year' | Periodic (annual) |
| 'after any material change/drift' | Event-driven/triggered |
| 'ongoing' / 'throughout lifecycle' | Continuous |
| 'each release' | Per-event |

## KRI vs KPI
| | KRI | KPI |
|---|---|---|
| Purpose | Leading risk signal | Performance/objective tracking |
| Structure | Threshold + escalation trigger | Target + achievement rate |
| Action on breach | Escalate per procedure | Review process improvement |

## Evidence Hierarchy (weakest → strongest)
1. Verbal/self-attestation
2. Design document only
3. Point-in-time screenshot
4. Timestamped logs across full period + investigation/closure trail

## Gap Analysis Prioritization
Rank by **risk exposure/severity**, not scope or deadline alone. Missing incident-response capability > partial documentation gaps > overdue-but-scheduled activities.

## Key Standards Referenced
- **NIST AI RMF 1.0**: Govern, Map, Measure, Manage
- **ISO/IEC 42001**: AIMS — context, leadership, risk-based planning, support, operation, performance evaluation (internal audit + mgmt review), improvement
- **EU AI Act Art. 72**: Continuous, lifecycle-long post-market monitoring plan (proportionate to risk); separate from serious-incident reporting obligations

## Three Lines of Defense
1st line = ML/model teams (operate) → 2nd line = AI governance/risk (design/monitor/challenge) → 3rd line = internal audit (independent assurance). Trap: 2nd line performing 3rd-line testing breaks independence.

## Control Ownership Documentation Must Include
Owner role, backup owner, escalation path, accountable governance body — not just a name.

# Chapter 6 Cheat Sheet: AI Governance Structures, Roles & Accountability
**Domain: AI Governance and Risk (33%)**

## Three Lines of Defense Applied to AI
| Line | Function | Key AI Roles | Responsibility |
|---|---|---|---|
| 1st | Operational/Business | Model owners, AI developers, data stewards | Build/operate models, implement controls, own daily risk |
| 2nd | Risk Oversight | Model risk management, AI ethics board, CAIO (policy) | Set policy, independent monitoring/challenge, approve high-risk use cases |
| 3rd | Independent Assurance | Internal Audit | Periodically test AI governance framework effectiveness; report to Audit Committee/Board |

Exam trap: 2nd line = ongoing, embedded oversight/challenge. 3rd line = periodic, independent audit. Don't swap these.

## Key Roles Quick Reference
| Role | Line | Primary Accountability |
|---|---|---|
| Chief AI Officer (CAIO) | Strategic/2nd | Enterprise-wide AI strategy, policy, governance alignment |
| Model Risk Owner | 1st | Risk of a specific model/use case; usually 'Accountable' in RACI |
| Data Steward | 1st | Data quality, lineage, access controls |
| AI Ethics Board | 2nd | Cross-functional ethical review, high-risk approval; usually 'Consulted' in RACI |
| Internal Audit | 3rd | Independent assurance on governance effectiveness |
| Board of Directors | Governance | Risk appetite, policy approval, receives AI risk reporting |

## RACI Mapping Rule
- Only ONE 'Accountable' per risk item (usually Model Risk Owner)
- Responsible = does the work (e.g., data scientist)
- Consulted = provides input before the decision (e.g., ethics board, legal)
- Informed = notified after the decision (e.g., senior mgmt for low-risk items)
Exam trap: assigning multiple 'Accountable' parties is a common wrong-answer pattern.

## Escalation Path (Severity-Based)
- Low risk: Model owner handles; informs 2nd line periodically
- Medium risk: Model owner → Model risk management (2nd line) review
- High risk: Model owner → AI ethics board/governance committee → Senior management
- Critical/Material: → Board of Directors + possible regulator notification

## Policy Lifecycle
Draft → Review → Approve (Governance Committee/Board) → Publish → Monitor → Periodic Review/Retire
- Every policy needs a designated owner and defined review cadence
- Material AI capability/regulatory changes should trigger an OUT-OF-CYCLE review, not wait for the next scheduled cycle

## ERM Alignment Principle
AI risk categories should be integrated into the existing Enterprise Risk Management (ERM) taxonomy and risk register — not managed as a fully separate framework. This ensures consistent risk appetite application and aggregated board-level reporting.

## Common Exam Traps
1. Assuming Internal Audit (3rd line) performs day-to-day model monitoring — wrong, that's 1st/2nd line.
2. Believing the AI Ethics Board has final decision authority — usually 'Consulted,' not 'Accountable.'
3. Treating AI governance as fully separate from ERM — should be integrated.
4. Assuming policies have no review cycle — all AI policies need periodic or trigger-based review.

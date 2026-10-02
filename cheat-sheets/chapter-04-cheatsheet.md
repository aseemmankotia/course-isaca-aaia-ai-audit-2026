## Chapter 4 Cheat Sheet — Deployment Architectures & Production Controls

### Deployment Patterns
| Pattern | Traffic Impact | Use Case | Rollback Speed |
|---|---|---|---|
| Batch | None (offline) | High-volume, latency-tolerant scoring | N/A — rerun job |
| Real-time API | Full, synchronous | Low-latency per-request decisions | Depends on gateway config |
| Edge | Full, local | No/unreliable connectivity, low latency | Redeploy to device |
| Embedded | Full, on-device | Extreme resource constraints, no network | Firmware/app update |
| Shadow | Zero (mirrored, logged only) | Safe validation of new model on live traffic | N/A — never live |
| Canary | Partial, incremental % | Gradual validation with real users | Fast — shrink % to zero |
| Blue-Green | Full, instant cutover | Zero-downtime full release | Fast — switch back to old env |

### API Gateway Controls
- **AuthN methods**: API keys, OAuth2/OIDC, mTLS (strongest mutual assurance)
- **Rate limiting algorithms**: Token bucket (burst-tolerant), Leaky bucket (constant outflow), Fixed/Sliding window counters
- **Standard responses**: 401 = unauthenticated, 403 = unauthorized, 429 = rate-limited
- Enforce least-privilege scopes per model endpoint; log all access for audit trail

### Change Management Workflow (Production Model Update)
1. Change request submitted with model version + validation evidence (performance, bias/fairness, drift tests)
2. Independent review/sign-off (risk, compliance, model risk owner) — segregation of duties from dev team
3. Rollback criteria defined BEFORE release (error rate, latency, drift thresholds)
4. Controlled rollout (shadow → canary → full) with monitoring at each stage
5. Post-deployment documentation updated (model card, changelog)

### Rollback & Incident Response Triggers
- Error rate spike above baseline
- Latency/SLA breach
- Data/prediction drift beyond threshold
- Business KPI degradation
- **Action order**: detect → contain (reduce/stop traffic to new version) → route to last known-good → root cause → post-incident review

### Capacity Planning for AI Workloads
- Do NOT rely on CPU utilization alone — inference workloads bottleneck on queue depth, batching, GPU/accelerator saturation
- Autoscale on: request queue depth, p95/p99 latency, GPU utilization
- Plan for burst traffic (e.g., seasonal/promotional spikes) separately from steady-state baseline

### Third-Party/Vendor-Hosted Model Risk Checklist
- Right-to-audit clause (not just NDA)
- Access to vendor change logs / incident reports
- Data residency & processing location clarity
- Model versioning/change notification commitments
- Exit strategy / data portability clause

### Common Exam Traps
- Confusing shadow (zero impact) with canary (partial live impact)
- Assuming CPU-based autoscaling is sufficient for inference services
- Treating an NDA as a sufficient vendor risk control
- Forgetting rollback criteria must be pre-defined, not decided during an incident

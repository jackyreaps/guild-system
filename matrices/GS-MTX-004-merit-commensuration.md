---
doc: GS-MTX-004
title: Merit Commensuration Matrix
status: draft
category: matrix
depends_on: [GS-CHR-002]
review_cycle: annual
---

# GS-MTX-004 — Merit Commensuration Matrix

| Contribution Type | Verification Method | Commensuration Primitive | Cross-Domain Portability | Gaming Risk |
|---|---|---|---|---|
| Formal proof | Proof checker / proof assistant | Independent verification | High | Low |
| Formalization | Proof assistant compilation | Independent verification | High | Low |
| Training loop | Execution with reproducible output | Independent execution | Medium | Medium (overstated gains) |
| Benchmark | Independent replication | Independent replication | High | Medium (overfitting) |
| Red-team report | Reproduction of vulnerability | Independent reproduction | High | Low (reproduction required) |
| Reproducibility audit | Independent rerun | Independent rerun | High | Low |
| Dataset | Independent validation | Independent validation | Medium | Medium (quality gaming) |
| Tooling | Independent use in another project | Independent use | High | Low |
| Teaching | Verified learner outcome | Verified outcome | Medium (context dependent) | Medium (grade inflation) |
| Mentorship | Longitudinal peer attestation | Longitudinal observation | Low (slow to verify) | Medium (reciprocal rings) |
| Command contribution | Two-member peer attestation | Peer attestation | Low | Medium (claim inflation) |

## Cross-References

| Document | Relationship |
|---|---|
| GS-CHR-002 §3 | Universal primitive |
| GS-CHR-002 §4 | Six dimensions |
| RS-INF-003 | Claim labels |

---
doc: GS-MTX-003
title: Merit Anti-Gaming Matrix
status: draft
category: matrix
depends_on: [GS-CHR-002]
review_cycle: annual
---

# GS-MTX-003 — Merit Anti-Gaming Matrix

| Attack Vector | Mechanism | Detection | Mitigation | Legal Boundary |
|---|---|---|---|---|
| Sybil farming | Multiple monikers by same person | Anonymity-set attestation; cross-guild diversity; contribution patterns | Anonymity-set attestation; cross-guild diversity for high-weight awards; periodic re-verification | No fraud |
| Collusive rings | Small groups attesting to each other | Attestation graph analysis; independence requirements | Attestors must be from guilds other than the attestee's for high-weight awards | No fraud |
| Plagiarism | Re-attesting copied work | Content-addressed hash matching | Hash uniqueness required; original attribution preserved | Copyright law applies |
| Merit laundering through forks | Copying merit to a new guild | Fork protocol: merit is not transferable | Non-transferability enforced by schema (RS-INF-002 §7.2) | No fraud |
| Bought merit | Payment for attestation | Financial disclosure requirements; pattern analysis | Attestation independence; reporting of financial ties | Bribery law applies |
| Sockpuppet review | Fake peer validation | Identity diversity checks; attestation independence | Independence requirements | No fraud |
| Command contribution inflation | Claiming command credit for routine work | Verification by two members of the affected circle | Peer attestation requirement | No fraud |
| Domain weight inflation | A guild inflating its own weights | Cross-branch peer attestation at renewal | No central authority; peer attestation (GS-CHR-002 §6) | No fraud |

## Cross-References

| Document | Relationship |
|---|---|
| GS-CHR-002 | Merit Protocol |
| GS-CHR-009 | Cross-guild recognition |
| RS-INF-002 §7.2 | API prohibits conversion and transfer |

---
doc: GS-CHR-002
title: Merit Protocol & Commensuration Rules
status: draft
category: charter
depends_on: [GS-FND-002]
runtime_impl: RS-INF-002, RS-INF-003
review_cycle: annual
---

# GS-CHR-002 — Merit Protocol & Commensuration Rules

## 1. Purpose

Merit is not a scoreboard. It is a codifying mechanism — the unit that lets a formalist's proof and a builder's training loop be placed on the same plane. This document specifies what counts as contribution, how contributions are weighted across domains, how Merit is recorded, and how it is protected from gaming.

Implements the Merit Ledger defined in GS-FND-002 §3 and `RS-INF-002` §3.2. Does not implement the Credits Ledger — that is GS-CHR-003.

## 2. The Commensuration Problem

A proof and a training loop are not naturally comparable. Institutional title fails as a comparator. Citation count fails. What does not fail is a single property both share: **the claim can be independently verified by a third party who does not trust the contributor.**

## 3. The Universal Primitive: Independent Verifiability

| Contribution Type | Verification Method |
|---|---|
| Formal proof | Proof checker / proof assistant |
| Formalization | Proof assistant compilation |
| Training loop | Execution with reproducible output |
| Benchmark | Independent replication |
| Red-team report | Reproduction of the vulnerability |
| Reproducibility audit | Independent rerun |
| Dataset | Independent validation |
| Tooling | Independent use in another project |
| Teaching | Verified learner outcome |
| Mentorship | Longitudinal peer attestation |

Merit is awarded on verification, not on claim.

## 4. Merit Dimensions

Every contribution is scored across six dimensions:

1. **Verification strength** — how independently confirmable
2. **Novelty** — new result vs. replication
3. **Difficulty** — domain-calibrated
4. **Downstream use** — did others build on it
5. **Robustness** — did it survive adversarial review
6. **Teaching value** — did it raise others' capability

Each dimension is scored on a published scale (0–5). The total is the base Merit weight. Domain-specific weighting may adjust within a factor of two.

## 5. Command Contribution

Leading under threat — maintaining parallel transport under stress — is a recognized contribution. Examples:

- Coordinating an emergency response during a member's detention
- Making the call that saves a guild from a legal attack
- Sustaining a Fork Circle through a split
- Holding a defense position in a hostile jurisdiction

Command contribution is verified by peer attestation from at least two members of the affected circle. Recorded in the Merit Ledger with a `command_contribution` event.

## 6. Per-Guild Calibration

Calibration is per-guild, subject to cross-branch peer attestation at the annual charter renewal cycle.

Each guild publishes its calibration rules in its Local Charter (GS-CHR-010). No central body sets weights. No cross-guild body may unilaterally inflate its own weight.

## 7. Attestation Format

Merit attestations are signed, portable, content-addressed. They reference the artifact, not the person. They include:

- Artifact content hash
- Verification evidence (proof checker output, test results, reproduction log)
- Six-dimension scoring
- Attestor signature
- Timestamp

Stored in the ledger event log (`RS-INF-002` §3.4) as `merit_award` events.

## 8. Cross-Guild Recognition

Cross-guild merit recognition is Phase C of `RS-INF-001`. It reads the published attestation format (GS-CHR-009) rather than the raw ledger. Until GS-CHR-009 is ratified, cross-guild recognition is manual and per-agreement between guilds.

## 9. Anti-Gaming

Merit is a target. Attack vectors (full analysis in GS-MTX-003):

- Sybil farming
- Collusive attestation rings
- Plagiarism
- Merit laundering through forks
- Bought Merit
- Sockpuppet review

Mitigations:

- Anonymity-set attestation
- Cross-guild diversity requirement for high-weight attestations
- Content-addressed artifact tracking
- Merit non-transferability
- Periodic re-verification of high-merit contributions

## 10. Appeals, Corrections, Decay

**Appeals:** Any member may appeal a Merit award within 30 days. Appeals are heard by peer attestors not involved in the original award.

**Corrections:** If an artifact is found to be incorrect or fraudulent, the original Merit may be rescinded and a `merit_rescind` event recorded. Merit is non-decreasing by default; rescission is the sole exception and requires two-thirds of the guild's attesting peers.

**Decay:** Merit does not decay. It is a permanent record. Downstream use continues to inform weighting.

## 11. Privacy

Merit is recorded against the moniker, never against a legal identity. Attribution of Merit to a legal person is the member's choice (via GS-CHR-011) and never required by the Guild System.

## 12. Cross-References

| Document | Relationship |
|---|---|
| GS-FND-002 §3, §4 Art. II, §7.7 | Merit definition, non-conversion, command contribution |
| GS-CHR-003 Currency Annex | Credits system, separate from Merit |
| GS-CHR-005 Branch Guardrails | Drift detection includes Merit gaming |
| GS-CHR-010 Local Charter | Per-guild calibration rules |
| GS-CHR-011 Identity and Alias | Merit-to-legal-identity binding (opt-in) |
| GS-MTX-003 Merit Anti-Gaming | Full attack vector analysis |
| GS-MTX-004 Merit Commensuration | Cross-domain comparison matrix |
| RS-INF-002 Ledger Schema | Storage format |
| RS-INF-003 Frame Profile | Claim labeling for merit attestations |

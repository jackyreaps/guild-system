---
doc: GS-Audit-001
title: Audit Resolution Directives
status: active
category: audit
authority: Assembly of Charters
depends_on: [GS-FND-002]
resolves: Coherence and Cohesion Audit findings
---

# GS-Audit-001 — Audit Resolution Directives

**Formal acceptance of the Coherence and Cohesion Audit findings and the architectural decisions that resolve them.**

---

## 1. Purpose

The Coherence and Cohesion Audit identified structural problems: a bottom-heavy document structure, a dependency loop where operational protocols referenced non-existent foundational authorities, overlapping concentration rules across three documents, terminology collisions between internal and external remedy systems, and an unresolved ambiguity between Merit and Credits.

This directive accepts those findings and establishes the architectural rules that resolve them. Every rule here is authoritative and binds the drafting of GS-FND-002 and all subsequent documents.

---

## 2. Structural Fixes and Boundary Declarations

### 2.1 The Foundational Disambiguation

Two distinct sets of "four inversions" were in circulation. They are now strictly separated:

**Operating Articles (I–IV)** — Economic and data mechanics:
1. Public/Authorized Data Separation
2. Non-Convertible System Credits
3. The Tax-Integrity Floor
4. Civic Substitution over Capital Accumulation

**Structural Principles (I–IV)** — Spatial and political architecture:
1. Exemption through Provision
2. Velocity of Flow over Hoarding
3. Polycentricity over Patronage
4. Verifiability over Secrecy

Both sets bind. They are never referred to jointly as "the four inversions." The collective term, when needed, is **the Eight Foundational Rules**.

### 2.2 Concentration Rule Boundaries

Three-layer division eliminates triple-enforcement overlap:

- **Process Layer (GS-CHR-005 Guardrails):** Detects drift, tracks operational metrics, manages the enforcement timeline. Does not define compliance thresholds.
- **Architecture Layer (GS-OPS-005 Insulation):** Defines structural requirements for legal entities — jurisdictional distribution, corporate form boundaries, disclosure rules.
- **Reserve Layer (GS-OPS-006 Resilience):** Defines quantitative distribution thresholds — the one-third institutional cap, currency spreads, 90-day runway assets.

**Operational correction:** GS-CHR-005 is amended to strip out independent structural definitions. It points to GS-OPS-005 for entity compliance and GS-OPS-006 for capital allocation compliance.

### 2.3 Lexical Collision Clean-up

- **The seven-step process in GS-CHR-005 §6** is renamed **The Drift Remedy Ladder**. Applies exclusively to internal guild governance.
- **The five-step posture framework in GS-CHR-006 §8** is renamed **The Demand Determination Scale**. Applies exclusively to external jurisdictional mandates.
- Both sections carry the note: "This framework applies exclusively to [Internal Guild Governance / External Jurisdictional Mandates] and cannot be substituted or cross-applied."

---

## 3. Conceptual Clarifications

### 3.1 Ledger Decoupling: Merit vs. Credits

Two separate ledgers. No conversion. Direct implementation in `RS-INF-002` §2.

**Merit Ledger** — Permanent, non-transferable, non-purchasable, non-burnable. Increases only. Serves as the exclusive metric for governance authority, calibration rights, and peer attestation weighting.

**Credits Ledger** — Variable, burn-on-use, spendable only on internal goods. Increases on grant, decreases on burn.

**Boundary:** No API endpoint, no internal function, and no write operation takes a Merit balance and returns Credits, or vice versa. The decoupling is enforced at the operation layer (`RS-INF-002` §7.2).

### 3.2 Calibration and Recognition Power

**Domain Councils (Removed):** The term is deleted from GS-CHR-002 §6. Replaced by: "Per-guild calibration subject to cross-branch peer attestation at the annual charter renewal cycle."

**Public-Good Functions:** Recognition is per-guild, declared in the local charter, validated by peer attestation. The Compact sets the non-negotiable floor (Education, Health, Infrastructure, Emergency Response, Legal Aid, Science Literacy, Care Work). Guilds may expand; may not subtract.

### 3.3 Housekeeping

**GS-OPS-006 §7** is amended to reference GS-OPS-005 §6 rather than restate the disclosure boundary.

**GS-OPS-006 §12** (Asymmetric Clearing) is revised from high-risk protocol references to a **Compliant Multi-Rail Redundancy** mandate: multiple regulated banking rails, multiple correspondent relationships, multiple payment providers, multiple currencies, all disclosed to lawful authorities.

### 3.4 Runtime Integration

The frame profile (`RS-INF-003`) records each guild's founding orientation and shear detection method in the ledger's `meta.frame_profile`. This operationalizes:
- Compact §6 Minimum Standard 5 (fork readiness)
- GS-CHR-005 (drift detection indicators)
- GS-CHR-010 (founding orientation declaration)

The frame profile is a declaration, not an attestation. Verification remains the peer guild's act.

---

## 4. Systematic Inventory Realignment

The full system map is updated to the GS-[CATEGORY]-[NNN] naming convention. See `INDEX.md` for the current inventory.

---

## 5. Cross-References

| Document | Relationship |
|---|---|
| GS-FND-002 Compact | Implements the Eight Foundational Rules defined here |
| GS-CHR-005 Branch Guardrails | Boundary amended per §2.2 |
| GS-OPS-005 Structural Insulation | Boundary clarified per §2.2 |
| GS-OPS-006 Financial Resilience | §7 and §12 amended per §3.3 |
| GS-CHR-002 Merit Protocol | Domain Councils removed per §3.2 |
| RS-INF-002 Ledger Schema | Implements §3.1 directly |
| RS-INF-003 Frame Profile | Implements §3.4 |

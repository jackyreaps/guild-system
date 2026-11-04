---
doc: GS-FND-002
title: The Compact of the Guild System
status: draft
category: foundation
binds: true
supersedes: all prior Compact drafts
review_cycle: biennial
---

# GS-FND-002 — The Compact of the Guild System

## 1. Purpose

This Compact establishes the minimum standards every chartered guild must meet, the eight foundational rules that govern the system's operation and structure, the authority under which the system acts, and the relationship between this document and every other document in the Guild System inventory.

Every other GS-* document derives its authority from this Compact. Where a contradiction exists, this Compact governs and the contradicting document is amended.

## 2. What the Guild System Is

A polycentric network of autonomous guilds — each with its own culture, currency, and internal governance — interoperating through a shared protocol for merit recognition, contribution verification, and idea protection.

No headquarters. No central board. No legal personality at the system level. A meta-structure: a minimal shared layer over many sovereign local guilds.

Its purpose is to provide a lawful, merit-based alternative to institutional narrative control — a place where formalists and builders can work together on problems that matter, with their contributions recognized by peers and protected by structure.

**Runtime:** Resileos-QAI (`RS-INF-001`, `RS-INF-002`, `RS-INF-003`). Framework: QD-TER-Human-Medium. Policy: this repository.

## 3. Core Definitions

- **The Compact.** This document. Holds no assets, signs no contracts, employs no one, has no legal personality, cannot be served.
- **Chartered Guild.** An autonomous legal entity that has adopted this Compact, filed a Local Guild Charter (GS-CHR-010), and been attested by peer guilds.
- **Circle.** A working group within a guild — formalist, empirical, forge, or distribution.
- **Forge Circle.** A temporary, mission-specific circle formed when formalist and empirical members overlap.
- **Member.** An individual participating in a chartered guild under a moniker. Membership does not require disclosure of legal identity at the system level.
- **Moniker.** A persistent pseudonymous identity bound to a cryptographic keypair.
- **Merit.** A permanent, non-transferable, non-purchasable record of verified contribution. The exclusive metric for governance authority, calibration rights, and peer attestation weighting. Stored in the Merit Ledger (`RS-INF-002` §3.2).
- **Credits.** A variable internal accounting unit used to access shared compute, tools, material resources, and educational services. Burn-on-use. Cannot be converted to Merit. Stored in the Credits Ledger (`RS-INF-002` §3.2).
- **Reserve.** Any asset held by a guild for operational continuity.
- **Guild Work.** Public or authorized contribution produced under a guild charter.
- **Hostile State.** A state actor using unlawful, predatory, or extrajudicial means to suppress lawful public-interest work. See GS-CHR-001 §3.2 for the expanded definition covering law-as-weapon.
- **Legitimate Legal Demand.** A request satisfying the Legitimacy Test (GS-CHR-006 §6): lawful basis, due process, proportionality, jurisdiction, human-rights compliance, targeting of lawful work, absence of pretext. A demand can be lawful under local statute and still fail the test if the law itself is predatory.
- **Predatory Request.** A demand failing any criterion of the Legitimacy Test.

## 4. The Four Operating Articles

### Article I — Public or Authorized Data Separation

The Guild System works only with public or explicitly authorized data. No guild, circle, or member may use covert data acquisition, unauthorized access, proprietary telemetry without consent, or trade secrets as the basis of any Guild artifact.

Public data, open weights, voluntarily disclosed whistleblower material through lawful channels, and authorized audit telemetry are permitted. Everything else is prohibited.

**Runtime:** Resileos enforces this at the namespace layer (`RS-INF-001` §3).

### Article II — Non-Convertible System Credits

Guild Credits are internal accounting units. They cannot be exchanged for fiat, cryptocurrency, or any external store of value. Earned by contribution, burned on consumption of internal goods.

The convertibility cap avoids tax and regulatory exposure, ensures credits can only build capability, and prevents credits from becoming speculative or capturable.

Any guild wishing to operate a semi-closed or convertible instrument must file a compliance annex (GS-CHR-003) and obtain local counsel sign-off. The default is closed-loop.

**Runtime:** `RS-INF-002` §7.2 prohibits `/convert`, `/redeem`, and `/transfer` endpoints. Their absence is structural.

### Article III — The Tax-Integrity Floor

Every member and every guild meets lawful tax obligations in their jurisdictions of residence, operation, and holding. No Guild structure conceals income, mischaracterizes compensation, defeats a lawful tax obligation, or moves value to defeat a lawful obligation.

Guild Credits route *surplus contribution* toward public-good functions (Article IV). They never route *around* a legal duty. Every guild files a local civic-provision annex reviewed by counsel (GS-CHR-004). If a structure cannot pass lawful inquiry, it is not a Guild structure.

### Article IV — Civic Substitution over Capital Accumulation

The Guild System exists to provide where provision is absent. Where public goods are unfunded, corrupted, or denied, voluntary mutual institutions may provide them in parallel.

The floor every guild must recognize:
- Education and literacy
- Health and mental health support
- Local infrastructure and logistics
- Emergency response
- Legal aid and rights education
- Science and civic literacy
- Care work

Guilds may expand this list. They may not subtract.

## 5. The Four Structural Principles

### Principle I — Exemption through Provision

No guild may seek exemption from lawful local obligations. Civic provision is the substitute for privilege, never a claim to it.

### Principle II — Velocity of Flow over Hoarding

No guild may accumulate convertible assets beyond what its mission and contingency pool require. Reserves circulate. Credits are spent. Concentration rules apply: no guild may hold more than one-third of reserves in a single institution, and no single counterparty may represent more than a defined share of income.

**Cross-reference:** `GS-OPS-005` §8, `GS-OPS-006` §4.

### Principle III — Polycentricity over Patronage

No guild may depend on a single funder, university, lab, state, legal form, or jurisdiction. Distribution requirements apply: assets in two or more jurisdictions, records in two or more, legal personality in a rule-of-law jurisdiction, membership distributed.

**Cross-reference:** `GS-OPS-005` §7, `GS-OPS-006` §4.

### Principle IV — Verifiability over Secrecy

No guild may be operationally opaque. Members may be pseudonymous; the guild's methods, artifacts, financial summaries, and operation must be verifiable by peers.

**Runtime:** `RS-INF-001` §3.2 names this as the reason for the namespaced subject scheme. `RS-INF-003` operationalizes it via the frame profile's claim labels.

## 6. Minimum Standards

Every chartered guild must meet all of the following:

1. **Adopt the Compact.** File a signed declaration of adoption.
2. **File a Local Guild Charter** (GS-CHR-010) declaring legal form, jurisdictions, funding sources, jurisdiction spread, fork readiness, founding orientation, and shear detection method.
3. **Operate lawfully.** Comply with tax, sanctions, AML/KYC, money transmission, employment, and consumer protection law.
4. **Publish artifacts.** Every Guild artifact is signed, reproducible, and publicly available.
5. **Maintain fork readiness.** Every guild has a Fork and Secession Protocol on file (GS-CHR-008) and can be forked by its members on defined conditions.
6. **Maintain the Defense Fund contribution.** Every guild contributes to the Defense Fund under GS-CHR-006 §5.4.
7. **Submit to peer attestation.** Every guild attests to peer guilds annually, and is attested by them.
8. **Comply with the disclosure boundary.** If a lawful authority asks who ultimately benefits from any structure, the answer is available (GS-OPS-005 §6).

**Runtime:** Resileos will not host a guild without a filed GS-CHR-010 (`RS-INF-001` §2.1).

## 7. The Authority Article

### 7.1 No Central Authority

No executive, legislative, or judicial power is granted to any body at the system level.

### 7.2 Authority Is Granted, Not Assumed

Where authority exists, it is granted by a specific document to a specific body for a specific purpose.

### 7.3 Authority Is Bounded

Every grant specifies: purpose, time period, scope of decisions, disclosure requirements, appeal mechanism.

### 7.4 Authority Is Sunset

No grant is permanent. Emergency authority expires faster than routine authority.

### 7.5 Authority Is Revocable

Every grant is revocable by the Assembly of Charters under its own procedures.

### 7.6 Authority Is Accountable

Every body exercising granted authority is subject to after-action review by peer attestation. The review is published.

### 7.7 Command Contribution

Leading under threat — maintaining parallel transport under stress — is a recognized contribution under GS-CHR-002 §5. Members who exercise granted authority well are recorded in the Merit Ledger. Members who abuse it are subject to the Drift Remedy Ladder (GS-CHR-005 §4).

## 8. Document Relationship

- **FND (Foundation) binds.** The Compact is the sole binding document in this category.
- **CHR (Charters) derives.** Charters take authority from the Compact.
- **OPS (Operations) implements.** Operations implement Charter rules.
- **MTX (Matrices) illustrates.** Matrices inform; they do not bind.
- **REF (Reference) informs.** Reference documents provide context.

Where documents conflict: FND > CHR > OPS > MTX > REF.

## 9. Peer Attestation

Every chartered guild is attested annually by at least two peer guilds not under its own charter. Attestation confirms:

- Compliance with the Compact and the guild's own charter
- Compliance with the eight foundational rules
- Fork readiness
- Publication and disclosure status
- Concentration and distribution status

Attestation is signed, public, and subject to appeal. Failure to obtain attestation triggers the Drift Remedy Ladder (GS-CHR-005 §4).

**Runtime:** Resileos stores attestations but does not perform them (`RS-INF-001` §5).

## 10. Fork and Exit

No guild may prevent its members from forking (GS-CHR-008). No guild may prevent its members from exiting. Orientation can always leave.

## 11. Amendment

1. Proposal by any chartered guild.
2. Public comment period of at least 60 days.
3. Ratification by two-thirds of chartered guilds in good standing.
4. Publication of amended text with revision history.

Emergency amendments (new legal threat category) may be ratified by two-thirds of the Assembly with 14-day comment, subject to confirmation within 90 days.

## 12. Cross-References

| Document | Relationship |
|---|---|
| GS-FND-001 Founding Signal | Cultural statement |
| GS-FND-003 Core Blueprint | Architectural narrative |
| GS-CHR-001 Hostile-State Resilience | Adversarial legality doctrine |
| GS-CHR-002 Merit Protocol | Implements the Merit/Credits decoupling |
| GS-CHR-003 Currency Annex | Implements Article II |
| GS-CHR-004 Civic Substitution | Implements Articles III and IV |
| GS-CHR-005 Branch Guardrails | Implements the Drift Remedy Ladder |
| GS-CHR-006 Juridical Chamber | Implements Authority §7 |
| GS-CHR-008 Fork and Secession | Implements §10 |
| GS-CHR-010 Local Charter Template | Implements §6 |
| GS-OPS-001 First 24 Hours | Implements emergency authority §7.4 |
| GS-OPS-005 Structural Insulation | Implements Principles II, III, IV |
| GS-OPS-006 Financial Resilience | Implements Principles II, III |
| GS-OPS-007 Modular Proxy | Corporate tiering for Principles II, III |
| GS-MTX-001 Adversarial Legality | Threat mapping |
| GS-REF-001 Historical Overlay | Historical foundation |
| RS-INF-001 Guild Infra | Runtime implementation |
| RS-INF-002 Ledger Schema | Data contract for Merit/Credits |
| RS-INF-003 Frame Profile | Founding orientation and shear detection |

## 13. Effective Date

Upon ratification by two-thirds of chartered guilds in good standing. Biennial review. Emergency review on material change.

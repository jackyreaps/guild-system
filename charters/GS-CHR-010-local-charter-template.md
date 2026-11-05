---
doc: GS-CHR-010
title: Local Guild Charter Template
status: draft
category: charter
depends_on: [GS-FND-002, GS-OPS-005, GS-OPS-006]
runtime_refs: [RS-INF-002, RS-INF-003, RS-INF-004]
review_cycle: annual
---

# GS-CHR-010 — Local Guild Charter Template

Every chartered guild files a Local Guild Charter. This Template specifies the minimum content required. A guild may add sections; it may not omit any of the required sections.

Sections 2.17 through 2.19 are optional. A guild that has not yet defined a rank ladder, a title catalog, or a valor policy omits them and states that they are deferred. Absence is valid. A guild that publishes a ladder must publish it here so pilots can be attested against it.

Resileos will not host a guild without a filed Local Guild Charter (RS-INF-001 §2.1).

## 1. Purpose

The Local Guild Charter is the guild's own constitutional document. It states what the guild is, where it operates, how it is governed, and what it commits to. It is reviewed by counsel, published as a public artifact, and attested by peer guilds. It is the local expression of the Compact's Minimum Standards (GS-FND-002 §6).

## 2. Required Sections

### 2.1 Guild Identity

- Guild name.
- Guild ID — lowercase slug, letters, digits, and hyphens only. Stable for the guild's lifetime.
- Founding date.
- Founding members, listed by moniker. Legal identity is optional.

### 2.2 Jurisdictions

- Legal jurisdictions of operation.
- Jurisdictions of asset holding.
- Jurisdictions of member residence, aggregated, not individual.

### 2.3 Legal Form

- The legal entity type — cooperative, non-profit, LLC, foundation, unincorporated association, or other.
- Registration jurisdiction.
- Registered agent, if applicable.

### 2.4 Membership and Alias Rules

- How members join.
- Whether membership is open, invitation-only, or application.
- Alias policies — whether a moniker can be changed, whether cross-guild linkage is required, and under what circumstances.

### 2.5 Internal Governance

- Decision-making process — rough consensus, rotating roles, elected stewards, or other.
- Term limits for any role.
- Amendment process for this charter.

### 2.6 Currency and Exchange

- The guild's currency system. Default is closed-loop Credits per GS-CHR-003.
- If an alternative: the compliance annex and local counsel sign-off reference.
- If the guild operates hub credits, the consolidation rate to guild credits (GS-OPS-010 §4.1).

### 2.7 Merit Recognition

- The guild's calibration rules, per GS-CHR-002 §6.
- The guild's public-good function additions beyond the Compact floor, per GS-FND-002 §4 Article IV.

### 2.8 Contribution Verification

- The guild's verification methods for each contribution type it recognizes.
- Any custom contribution types, with the primitive used to verify them.

### 2.9 Founding Orientation

Required per GS-CHR-008 §6. The fields are stored at `meta.frame_profile` in the ledger, specified in RS-INF-002.

- **Statement.** One paragraph. What the guild commits to preserve.
- **Field coupled to.** The problem domain, community, or public good.
- **Invariants.** Three to seven things the guild will not be sheared away from.

### 2.10 Shear Detection Method

Required per RS-INF-002 (`meta.frame_profile`).

- **Method.** Peer attestation, metric watch, or hybrid.
- **Indicators.** At least three from the published set in RS-INF-002, or custom indicators labeled as declared.
- **Threshold.** The condition under which shear is declared.
- **Review cadence.** Monthly, quarterly, or annual.

### 2.11 Fork Conditions

Required per GS-CHR-008 §6.

- The specific conditions under which members may fork to preserve the founding orientation.
- Examples include: orientation materially changed without amendment; funding concentration exceeds threshold; governance opaque; prohibited entanglement entered.
- If the guild operates under GS-CHR-012 Sovereignty, state explicitly whether fork is available (it is not, under §7.5) and what the exit path is instead.

### 2.12 Guardrail Declaration

Required per GS-CHR-005 §2.

- A statement that the guild complies with each of the seven drift patterns' prohibitions.
- Any exceptions, with justification, subject to peer attestation.

### 2.13 Conflict-of-Interest Rules

- Disclosure requirements for members in governance roles.
- Recusal procedures.

### 2.14 Legal Compliance Statement

- A statement that the guild complies with the Tax-Integrity Floor, per GS-FND-002 §4 Article III.
- A statement that the guild complies with the disclosure boundary, per GS-OPS-005 §6.

### 2.15 Counsel Contact

- The guild's local counsel contact information.
- The guild's legal annex reference, per §2.16.

### 2.16 Legal Annex

- Filed separately, referenced here.
- Covers tax registration, beneficial ownership disclosure, sanctions compliance, AML/KYC where applicable, and data protection.

### 2.17 Structural Model

Required if the guild sits in a network that has adopted a structural model under GS-CHR-012.

- The model the guild participates in: Convocation, Imperium, Sovereignty, or none.
- If Convocation: whether the guild sits or opts out (§4.1, §4.2).
- If Imperium: whether the guild is a Senate member or periphery (§5.1, §5.3).
- If Sovereignty: the guild's relationship to the sovereign's charge and the Council of Valor (§6.3).

A guild that participates in no model is external. It states that here.

## 3. Optional Sections

### 3.1 Rank Table (Optional)

A guild that defines a local rank ladder publishes it here. The rank ladder is local. It is not a network office, and a rank name does not carry the meaning of a network office (GS-CHR-012 §12.2).

Each rank entry names:

- **Rank name.** Local to the guild.
- **Merit threshold.** The aggregate merit required, per the guild's calibration (GS-CHR-002 §6).
- **Additional conditions.** Attestation count, verified contribution types, tenure, or other criteria the guild sets.
- **Recorded in.** Confirm the ladder is recorded in RS-INF-003.

A guild that has not defined a ladder states: "No rank ladder defined at filing." The section remains present and may be filled by amendment.

### 3.2 Title Catalog (Optional)

A guild that awards titles publishes the catalog here.

Each title entry names:

- **Title.** Local to the guild.
- **Criteria.** What earns it.
- **Evidence.** What artifact or verification supports it.
- **Revocable.** Yes or no, and on what conditions.
- **Recorded in.** Confirm titles are recorded in RS-INF-004.

Titles are earned, not purchased. Credits never buy a title (GS-CHR-012 §12.2).

A guild that awards no titles states: "No title catalog defined at filing."

### 3.3 Valor Policy (Optional)

A guild that records valor publishes its policy here.

The policy names:

- **What counts as valor.** The guild's definition. It must involve demonstrated cost borne, not assertion.
- **Pending vs. accomplished.** How a valor record moves from pending (claimed) to accomplished (verified). What evidence is required for each transition.
- **Who verifies.** The guild body or process that confirms accomplishment.
- **Recorded in.** Confirm valor records are stored in RS-INF-004.

Accomplished valor is evidence. It does not auto-appoint anyone to a network seat or class (GS-CHR-012 §12.3). Under Sovereignty, accomplished valor records are inputs to the Valor Audit (GS-CHR-012 §6.4); valor is demonstrated in public contest, not granted by API.

A guild that records no valor states: "No valor policy defined at filing."

## 4. Filing Process

1. The guild drafts its charter.
2. The charter is reviewed by local counsel — via the Counsel Network if the guild is new.
3. The charter is published in `world:` or equivalent public artifact store.
4. The charter hash is recorded in the guild's first ledger entry, per RS-INF-002.
5. The guild requests attestation from at least one peer guild not under its own charter, per GS-FND-002 §9.

## 5. Amendment

Amendments to the Local Guild Charter follow the guild's own amendment process, defined in §2.5. Amendments to sections 2.9, 2.10, 2.11, or 2.17 — founding orientation, shear detection, fork conditions, structural model — require three additional steps:

1. The guild's internal amendment process.
2. A 30-day comment period for peer guilds.
3. Re-attestation by at least one peer guild.

Adding, changing, or removing a rank table, title catalog, or valor policy (§3.1–3.3) requires the guild's internal amendment process and re-attestation. These are not quiet changes.

These sections are the member's protection against quiet capture. They cannot be amended without the additional process.

## 6. Cross-References

| Document | Relationship |
|---|---|
| GS-FND-002 §6 | Minimum Standards — charter is Standard 2 |
| GS-CHR-002 §6 | Merit calibration |
| GS-CHR-003 | Currency system |
| GS-CHR-005 §2 | Guardrail declaration |
| GS-CHR-008 §6 | Fork conditions |
| GS-CHR-012 §12 | Portfolio bridge — how rank, title, and valor feed representation |
| GS-OPS-005 §6 | Disclosure boundary |
| GS-OPS-006 §4 | Reserve distribution — referenced, not restated |
| GS-OPS-010 §4.1 | Hub consolidation rate, if hub credits are used |
| RS-INF-001 §2.1 | Runtime requires filed charter |
| RS-INF-002 | Ledger schema, including `meta.frame_profile` |
| RS-INF-003 | Ranks and work board |
| RS-INF-004 | Titles and valor portfolio |

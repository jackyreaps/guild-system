---
doc: GS-OPS-006
title: Financial Resilience and Distribution Protocol
status: draft
category: operations
depends_on: [GS-FND-002, GS-OPS-005]
review_cycle: annual
---

# GS-OPS-006 — Financial Resilience and Distribution Protocol

## Boundary Statement

This document defines reserve distribution thresholds. For drift detection, see **GS-CHR-005**. For entity structure, see **GS-OPS-005**.

## 1. Purpose

To ensure that no single financial institution, jurisdiction, currency, legal form, or counterparty can disable the Guild System by freezing, seizing, failing, or capturing the system's means of operation. Every structure here is designed to pass lawful inquiry, not to defeat it.

## 2. The Foundational Distinction

- **Resilience** — many independent, lawful, disclosed holdings, so that any one failure is survivable.
- **Concealment** — one hidden holding, so that no one can find it.

The first is the goal. The second is prohibited under GS-OPS-005 §6.

## 3. Definitions

- **Reserve.** Any asset held for operational continuity.
- **Concentration.** Share of reserves in a single institution, jurisdiction, currency, or legal form.
- **Contingency Pool.** A reserve for emergency response, accessible within 24 hours.
- **Distribution Requirement.** Minimum spread across institutions, jurisdictions, currencies, forms.

## 4. The Five Distribution Requirements

### 4.1 Institutional

No single financial institution holds more than one-third of a guild's reserves. Threshold is set per guild and reviewed by counsel.

### 4.2 Jurisdictional

Reserves in at least two jurisdictions with independent legal systems and banking regulators.

### 4.3 Currency

Reserves in at least two currencies, preferably with independent monetary policies.

### 4.4 Legal Form

Reserves across at least two legal forms: bank deposit, custody arrangement, cooperative membership, physical asset, IP.

### 4.5 Counterparty

No single counterparty represents more than a defined share of income or reserves. Cross-references GS-OPS-005 §8.

## 5. The Contingency Pool

Each guild maintains a contingency pool equivalent to at least 90 days of operational runway, accessible within 24 hours without depending on a single institution.

**Permitted forms:**
- Cash or near-cash at more than one institution.
- Short-term government securities in more than one jurisdiction.
- Physical precious metal with a licensed custodian.
- Prepaid compute credits with more than one provider.

**Prohibited forms:**
- Assets that cannot be liquidated within 24 hours.
- Assets held by a single institution.
- Assets whose ownership is not disclosed on lawful request.
- Assets held in any structure failing GS-OPS-005 §6.

## 6. The Distribution Matrix

| Reserve Type | Min. Institutions | Min. Jurisdictions | Min. Currencies | Min. Legal Forms | Access |
|---|---|---|---|---|---|
| Operating funds | 2 | 2 | 1 | 1 | 24 hours |
| Contingency pool | 2 | 2 | 2 | 2 | 24 hours |
| Long-term reserves | 3 | 2 | 2 | 3 | 90 days |
| Compute credits | 2 providers | 2 | N/A | 1 | 24 hours |
| Intellectual property | 1 entity/work | 2 | N/A | 2 | N/A |

## 7. Legal Compliance

All asset structures must satisfy the definitive disclosure boundaries established in GS-OPS-005 §6. That includes: tax compliance, beneficial ownership disclosure, regulatory reporting, sanctions compliance, AML/KYC.

If a structure cannot satisfy all five, it is a concealment structure.

## 8. The Failure Test

> If any single institution, jurisdiction, currency, legal form, or counterparty fails, is captured, or becomes hostile, the guild continues operating for at least 90 days using reserves held elsewhere.

If the answer is no, the structure fails.

## 9. Prohibited Structures

- Purpose of defeating a lawful obligation.
- Cannot pass lawful inquiry.
- Designed to make reserves untraceable.
- Dependent on a single institution, jurisdiction, currency, or form.
- Fails to disclose beneficial ownership on lawful request.

## 10. Compliant Multi-Rail Redundancy

Cross-border or high-value trade settlements must not rely on a single, centralized clearing network without an active, parallel alternative.

- **Multi-rail settlement.** At least two independent regulated payment rails are available for any given settlement corridor.
- **Bilateral clearing.** For critical operational dependencies, guilds may establish direct bilateral clearing via local credit-barter or isolated collateral arrangements under contract.
- **Regulated instruments.** All rails comply with local money-transmission, AML/KYC, and sanctions law. Any digital asset used for cross-guild settlement is held via a regulated custody intermediary and subject to the same disclosure requirements as any other reserve.

The purpose is survivability of a single rail failure, not evasion of lawful freezing or sanctions. A structure designed to defeat lawful enforcement fails §7.

## 11. Cross-References

| Document | Relationship |
|---|---|
| GS-FND-002 §5 Principles II, III | Flow over hoarding, polycentricity |
| GS-CHR-005 §4 | Drift Remedy Ladder |
| GS-OPS-005 §6, §7, §8 | Disclosure boundary, jurisdictional distribution, anti-concentration |
| GS-OPS-004 | Compliance layer |
| GS-MTX-005 | Credit exposure |
| GS-MTX-010 | Counterparty insulation |

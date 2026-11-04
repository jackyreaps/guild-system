---
doc: GS-OPS-004
title: Compute and Treasury Compliance Annex
status: draft
category: operations
depends_on: [GS-FND-002, GS-CHR-003, GS-OPS-006]
review_cycle: annual
---

# GS-OPS-004 — Compute and Treasury Compliance Annex

## 1. Purpose

Compute and treasury flows touch every jurisdiction where a guild operates. This Annex specifies the compliance requirements for both.

## 2. Compute

### 2.1 Sources

Compute may be acquired from:

- Commercial cloud providers (AWS, GCP, Azure, others).
- Decentralized compute marketplaces.
- Member-contributed compute.
- Cooperative compute arrangements.
- Guild-owned hardware.

### 2.2 Compliance Requirements

For each compute source:

- **Sanctions screening.** The provider is not sanctioned, and the funds do not benefit a sanctioned entity.
- **Export control.** The use of the compute does not violate export-control regimes applicable to the jurisdiction.
- **Data residency.** Compute is not used for data that would violate the data's jurisdiction of origin's residency requirements.
- **Provider agreement.** The provider's terms are accepted and complied with.

### 2.3 Compute Credits

Compute may be purchased with Credits (internal) or with external value (via intermediary). If purchased with Credits:

- Credits are burned on purchase (per `RS-INF-002` §4 `credits_burn`).
- The compute provider is paid in external value by the guild, not by Credits.
- The Credits do not touch the provider. They remain internal.

If purchased with external value via intermediary:

- The intermediary complies with the same sanctions, export-control, and data-residency requirements.
- The intermediary does not receive Merit.

## 3. Treasury

### 3.1 Sources

Treasury inflows may come from:

- Member contributions (donations, membership fees, bounty payments).
- Grants from foundations, universities, or non-profit organizations.
- Compute revenue (if a guild provides compute to others).
- Bounty completions paid by external parties.

### 3.2 Compliance Requirements

For each inflow:

- **Source documentation.** The source is identified and documented.
- **Sanctions screening.** The source is not sanctioned.
- **AML/KYC.** Where required by the receiving institution, AML/KYC is completed.
- **Tax.** The inflow is recorded for tax purposes.
- **Gift/contribution treatment.** Non-taxable contributions are distinguished from taxable income.

### 3.3 Outflows

For each outflow:

- **Tax.** Outflows are recorded; withholding applies where required.
- **Sanctions screening.** The recipient is not sanctioned.
- **AML/KYC.** Where required.
- **Disclosure.** The outflow is recorded in the guild's annual transparency report, aggregated.

### 3.4 Reserves

Reserves follow GS-OPS-006 §4 (distribution requirements). This Annex specifies the compliance layer; GS-OPS-006 specifies the distribution layer.

## 4. Intermediaries

Every non-trivial treasury or compute flow goes through an intermediary (GS-OPS-005 §5). The intermediary:

- Holds the legal relationship with the counterparty.
- Complies with the compliance requirements above.
- Discloses to the guild the information needed for the guild's own compliance.

The guild is not the direct counterparty to the state, sovereign fund, or large institution (GS-OPS-005 §4).

## 5. Per-Jurisdiction Review

Every guild files a per-jurisdiction compliance annex covering:

- Tax registration in each jurisdiction.
- Banking relationships in each jurisdiction.
- Sanctions regimes applicable.
- Export-control regimes applicable.
- Data-residency requirements applicable.

Local counsel reviews.

## 6. Cross-References

| Document | Relationship |
|---|---|
| GS-FND-002 Art. II, Art. III | Non-convertibility, tax integrity |
| GS-CHR-003 | Credits system |
| GS-OPS-005 §4, §5 | Counterparty and intermediary rules |
| GS-OPS-006 §4 | Reserve distribution |
| GS-MTX-002 | Per-jurisdiction matrix |

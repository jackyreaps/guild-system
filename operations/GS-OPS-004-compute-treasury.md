---
doc: GS-OPS-004
title: Compute and Treasury Compliance Annex
status: draft
category: operations
depends_on: [GS-FND-002, GS-CHR-003, GS-OPS-008, GS-OPS-009]
review_cycle: annual
---

# GS-OPS-004 — Compute and Treasury Compliance Annex

Specifies how a guild acquires compute, allocates it to members, meters usage, and integrates with any external compute provider — including Resileos — without converting Guild Credits to external value or allowing fiat to become Guild Credits.

## 1. Purpose

Compute and treasury flows touch every jurisdiction where a guild operates. This Annex specifies the compliance requirements for both, and — critically — specifies the integration model between the guild's internal credits economy and any external compute provider.

The distinction this document preserves: **Guild Credits are internal. Fiat is external. They meet at the guild's treasury, and they never cross.** A member spends Guild Credits to access compute the guild has already paid for in fiat. The fiat never becomes a credit. The credit never becomes fiat.

## 2. Compute

### 2.1 Sources

Compute may be acquired from:

- Commercial cloud providers (AWS, GCP, Azure, others).
- Decentralized compute marketplaces.
- Member-contributed compute.
- Cooperative compute arrangements.
- Guild-owned hardware.
- Resileos-QAI, when operating as a compute provider.
- Any other provider satisfying §2.2.

### 2.2 Compliance Requirements

For each compute source:

- **Sanctions screening.** The provider is not sanctioned, and the funds do not benefit a sanctioned entity.
- **Export control.** The use of the compute does not violate export-control regimes applicable to the jurisdiction.
- **Data residency.** Compute is not used for data that would violate the data's jurisdiction of origin's residency requirements.
- **Provider agreement.** The provider's terms are accepted and complied with.

### 2.3 Compute Acquisition

The guild acquires compute in one of two ways:

**Fiat purchase.** The guild's treasury pays the provider in fiat, at the provider's commercial rate. This is an ordinary treasury outflow under GS-OPS-008 §4 (Exchange Event) and GS-OPS-004 §3.3. The guild now holds compute capacity as a reserve or operating asset.

**Barter or contribution.** A member contributes compute directly, or the guild trades non-monetary value for compute under a documented contract. Both are permitted, subject to the same compliance requirements as fiat purchase, and both are documented for tax purposes.

**Guild Credits are never used to pay an external provider.** See §2.4.

### 2.4 Compute Metering and Credit Burn

Once the guild holds compute capacity — whether purchased with fiat, bartered, or contributed — the guild allocates that capacity to members. Members access the allocated capacity by burning Guild Credits.

**The burn-on-use model:**

1. The guild allocates a compute pool: "X hours of GPU time per month, or Y API tokens per month, available to members."
2. A member requests compute from the pool.
3. The member's Guild Credits are burned at the guild's published rate: `credits_burn` event with `resource: compute:<type>` and `amount: <credits>`.
4. The guild provides the compute from its allocation.
5. The member receives the compute access.

**The credits are consumed. They do not flow to the provider.** The provider was paid in fiat by the guild's treasury. The credits are an internal accounting of how the guild's compute allocation is distributed among members.

When compute is allocated through the mutual pool or the advance mechanism (GS-OPS-009 §5), the allocation is recorded as a `compute_pool_draw` or `compute_advance_issued` event rather than a `credits_burn`. The three paths are distinct:

| Path | Event | Effect |
|---|---|---|
| Burn on use | `credits_burn` | Credits consumed; no further obligation |
| Pool draw | `compute_pool_draw` | Obligation to future contribution; repaid via `compute_pool_repay` |
| Advance | `compute_advance_issued` | Obligation to specified contribution; settled via `compute_advance_settled` |

The burn path consumes credits immediately. The pool and advance paths create contribution obligations that are settled later. A member chooses the path based on whether they have credits to burn or want to commit future contribution.

### 2.5 What the Burn Is and Is Not

**The burn is:**
- An internal accounting event: "this member consumed this much of the guild's allocated compute."
- Recorded in the guild ledger as `credits_burn` (RS-INF-002 §4).
- A use of credits that were earned by contribution.
- The only way a member consumes guild-allocated compute without creating a future obligation.

**The burn is not:**
- A conversion of credits to fiat. The credits cease to exist; they are not exchanged for value.
- A purchase of credits. The member did not pay fiat to receive the credits; they earned them by contribution.
- A payment to the provider. The provider is paid separately, in fiat, by the guild's treasury.
- A redemption. Redemption implies external value; burn is internal consumption.

### 2.6 The One-Way Rule

**Fiat never becomes Guild Credits. Guild Credits never become fiat.**

There are exactly three ways a member acquires Guild Credits:

1. **Contribution.** Verified work that the guild awards credits for, per GS-CHR-002.
2. **Mutual credit facility.** The member borrows credits from the pool against future contribution, per GS-OPS-009 §2.
3. **Advance against contribution.** The guild advances credits against future work, per GS-OPS-009 §3.

There is no fourth way. A member cannot purchase Guild Credits with fiat. A member cannot convert fiat into credits through any mechanism. A member cannot receive credits as a gift from the guild in exchange for fiat or external value.

There is exactly one way a member uses Guild Credits: **burn on internal goods.** Compute, tools, courses, and internal services are consumed by burning credits. The credits are extinguished. No external value flows to the member in exchange.

Compute can also be accessed through the pool or advance mechanisms, which create contribution obligations rather than consuming credits. Both paths are internal: no fiat, no conversion, no external value.

### 2.7 What About External Providers Selling Credits?

If an external provider — including Resileos-QAI in its commercial capacity — sells credits or access tokens to the public for fiat, those are that provider's own commercial instruments. They are not Guild Credits.

A member may hold Resileos commercial credits alongside their Guild Credits. Those are two different instruments with two different ledgers:

- **Guild Credits** live in the guild's `guild_ledger.json` (RS-INF-002). Earned by contribution. Burned on internal goods. Never purchased with fiat.
- **Resileos commercial credits** live in Resileos's own commercial accounting. Purchased with fiat. Redeemable for Resileos's services. Not Guild Credits.

The guild may integrate with Resileos in one direction: **the guild buys compute from Resileos at commercial rates, then allocates that compute to members who burn Guild Credits for it, or draw from the pool, or take an advance.** This is the model in §2.4. The Resileos commercial credits the guild purchases are held in the guild's treasury, not passed to members.

What is prohibited:

- The guild accepting Resileos commercial credits as payment for Guild Credits.
- The guild allowing members to convert Guild Credits to Resileos commercial credits.
- Any mechanism that makes Resileos commercial credits equivalent to, exchangeable for, or a path to Guild Credits.

## 3. Treasury

### 3.1 Sources

Treasury inflows may come from:

- Member contributions (donations, membership fees, bounty payments).
- Grants from foundations, universities, or non-profit organizations.
- Compute revenue (if a guild provides compute to others).
- Bounty completions paid by external parties.
- Borrowing, per GS-OPS-008 §5.2.
- Capital instruments, per GS-OPS-008 §5.3.

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

Reserves follow GS-OPS-006 §4 (distribution requirements) and GS-OPS-008 §3 (allocation policy). This Annex specifies the compliance layer; GS-OPS-006 specifies the distribution layer; GS-OPS-008 specifies the allocation layer.

## 4. Intermediaries

Every non-trivial treasury or compute flow goes through an intermediary (GS-OPS-005 §5). The intermediary:

- Holds the legal relationship with the counterparty.
- Complies with the compliance requirements above.
- Discloses to the guild the information needed for the guild's own compliance.

The guild is not the direct counterparty to the state, sovereign fund, or large institution (GS-OPS-005 §4).

## 5. The Resileos Integration Model

Resileos-QAI is one compute provider among others. When a guild uses Resileos compute, the integration follows §2.4, §2.6, and §2.7 exactly.

### 5.1 The Flow

1. **Guild treasury pays Resileos in fiat** for a compute allocation, at Resileos's commercial rate. This is an outflow under §3.3.
2. **Resileos provides the allocation to the guild.** The guild holds it as a compute asset.
3. **Guild allocates the compute pool to members**, per the guild's internal governance.
4. **Members access the allocation** via one of three paths: burn Guild Credits (`credits_burn`), draw from the compute pool (`compute_pool_draw`), or take an advance (`compute_advance_issued`).
5. **The member receives compute access.** The credits are consumed or the obligation is recorded. The fiat was already spent by the treasury.

The credits never leave the guild ledger. The fiat never enters it as credits. The two flows are separate and stay separate.

### 5.2 What Resileos May and May Not Do in This Flow

**Resileos may:**
- Accept fiat from the guild's treasury at commercial rates.
- Provide compute allocation to the guild as a service.
- Maintain its own commercial accounting of the guild's purchase.

**Resileos may not:**
- Accept Guild Credits as payment. Guild Credits are not external value; they cannot be paid to an external provider.
- Issue Resileos credits that are exchangeable for Guild Credits.
- Operate any mechanism that allows a member to convert between Guild Credits and Resileos commercial credits.
- Act as a registry, custodian, or clearinghouse for Guild Credits. Those live only in the guild's `guild_ledger.json`.
- Act as a clearinghouse for the compute pool or advance obligations. Those are recorded in the guild's own ledger, not in Resileos's commercial accounting.

### 5.3 What About Resileos Selling AI Access to the Public?

If Resileos sells AI access, credits, or tokens to the general public for fiat, that is Resileos's own commercial product. It is not connected to any guild's Guild Credits.

A person may be both:
- A Guild member, with Guild Credits earned by contribution.
- A Resileos customer, with Resileos commercial credits purchased with fiat.

The two are separate. The guild may not intermediate between them. A member may not use their guild relationship to convert Resileos commercial credits to Guild Credits, or vice versa.

### 5.4 The Guiding Principle

The integration is **one-way by construction.**

- **Into the guild:** compute allocation purchased with fiat, or contributed by members.
- **Out of the guild:** fiat for providers, signed artifacts, public research.
- **Inside the guild:** Guild Credits earned by contribution, burned on internal goods; compute allocation through burn, pool draw, or advance.

The credits never cross the boundary. That is what makes the model compliant with Article II and safe for the guild.

## 6. Per-Jurisdiction Review

Every guild files a per-jurisdiction compliance annex covering:

- Tax registration in each jurisdiction.
- Banking relationships in each jurisdiction.
- Sanctions regimes applicable.
- Export-control regimes applicable.
- Data-residency requirements applicable.
- Compute provider relationships and their jurisdictional exposure.

Local counsel reviews.

## 7. Cross-References

| Document | Relationship |
|---|---|
| GS-FND-002 Art. II, Art. III | Non-convertibility, tax integrity |
| GS-CHR-003 §6 | Permitted and prohibited structures |
| GS-OPS-005 §4, §5, §6 | Counterparty, intermediary, disclosure rules |
| GS-OPS-006 §4 | Reserve distribution |
| GS-OPS-008 §4, §5 | Exchange events and capital acquisition |
| GS-OPS-009 §2 | Mutual credit facility |
| GS-OPS-009 §3 | Advance against contribution |
| GS-OPS-009 §5 | Compute allocation — burn, pool draw, advance |
| GS-MTX-002 | Per-jurisdiction matrix |
| RS-INF-001 §3 | `world:` namespace for registered artifacts |
| RS-INF-002 §4 | `credits_burn`, `compute_pool_draw`, `compute_advance_issued` events |

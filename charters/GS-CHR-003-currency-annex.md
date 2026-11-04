---
doc: GS-CHR-003
title: Currency and Exchange Annex
status: full
category: charter
authority: Assembly of Charters
depends_on: [GS-FND-002, GS-Audit-001]
runtime_impl: RS-INF-002
review_cycle: annual
---

# GS-CHR-003 — Currency and Exchange Annex

**Convertibility boundaries and the lawful limits of internal currency.**

---

## 1. Purpose

Guild Credits are internal accounting units. This Annex specifies their convertibility boundaries, the compliance surfaces they touch, and the prohibited structures that would turn them into a compliance liability. It implements Operating Article II of the Compact.

---

## 2. The Convertibility Boundary

| Level | Description | Legal Exposure |
|---|---|---|
| **Closed-loop** | Internal only, non-redeemable, non-transferable outside | Lowest |
| **Mutual credit** | Members extend and receive credit among themselves | Moderate |
| **Semi-closed** | Redeemable for external compute/services via intermediary | Counsel required |
| **Convertible** | Exchangeable for fiat/crypto | Full regulatory regime |

**The Compact defaults to closed-loop.** Any guild wishing to operate semi-closed or convertible must file a compliance annex and obtain local counsel sign-off.

---

## 3. The Alignment Principle

The less convertible a unit, the lower its tax and regulatory exposure, and the more it must be spent on learning, tools, compute, and local contribution. Therefore the Compact deliberately caps convertibility. This is a feature, not a limitation. The tax shield and the learning incentive are the same mechanism.

---

## 4. Tax Efficiency and Lawful Planning

**What the Guild does:**
- Structure internal units to avoid accidental realization
- Use treaty mechanisms, foreign tax credits, non-profit/educational/cooperative status where available
- Time contributions to avoid double taxation
- Support members in understanding local obligations

**What the Guild does not do:**
- Conceal income
- Mischaracterize compensation
- Move value to defeat a lawful obligation
- Advise on evasion
- Maintain opaque value transfer

**Mandatory:** Every guild files a local tax annex reviewed by counsel (GS-CHR-004 §4). No exceptions.

---

## 5. Guild Credit Exposure

| Use Case | Convertibility | Regime Triggered | Lawful Mitigation | Prohibited Version |
|---|---|---|---|---|
| Internal compute purchase | Closed-loop | None | Non-transferable unit | — |
| Learning bounty in credits | Closed-loop | Low | Non-redeemable | Cash payout disguised as credits |
| Mutual credit for review | Mutual | Low–moderate | Time-bank precedent | Off-book wage substitution |
| Stipend for living costs | Semi-closed | Income tax likely | Disclose, withhold if required | Concealed compensation |
| Inter-guild settlement | Mutual | Varies | Counsel per jurisdiction | Unlicensed transmission |
| External redemption | Convertible | Full regime | Licensed rails, AML/KYC | Anonymous cash-out |
| Compute barter | Barter | Often taxable | Contract, report | Unreported barter |

---

## 6. Permitted and Prohibited Structures

**Permitted:**
- Internal accounting units
- Bounty escrow with counsel oversight
- Compute barter under contract
- Mutual-aid pools within legal limits

**Prohibited:**
- Unlicensed money transmission
- Sanctions evasion
- Unregistered securities offering
- Wage substitution designed to avoid employment law
- Anonymous large-value settlement
- Convertible units without a compliance annex

**Runtime:** `RS-INF-002` §7.2 prohibits `/convert`, `/redeem`, `/transfer`, `/purchase`, `/withdraw` endpoints. Their absence is structural.

---

## 7. Per-Guild Compliance Annex Requirement

Every guild operating any non-closed-loop instrument files a Compliance Annex reviewed by local counsel. The annex names: instrument type, jurisdiction(s), legal regime, mitigation applied, counsel contact.

---

## 8. Cross-References

| Document | Relationship |
|---|---|
| GS-FND-002 Art. II, Art. III | Non-convertibility, tax integrity |
| GS-Audit-001 §3.1 | Ledger decoupling |
| GS-CHR-004 Civic Substitution | Tax annex and civic provision |
| GS-CHR-002 Merit Protocol | Merit system, separate from Credits |
| GS-OPS-005 Structural Insulation | Entity structure hosting Credits |
| GS-OPS-006 Financial Resilience | Reserve distribution |
| GS-MTX-005 Credit Exposure Matrix | Full exposure matrix |
| RS-INF-002 Ledger Schema | Storage and API boundary |

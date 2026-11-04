---
doc: GS-CHR-003
title: Currency and Exchange Annex
status: draft
category: charter
depends_on: [GS-FND-002, GS-OPS-008, GS-OPS-009]
runtime_impl: RS-INF-002
review_cycle: annual
---

# GS-CHR-003 — Currency and Exchange Annex

## 1. Purpose

Guild Credits are internal accounting units. This Annex specifies their convertibility boundaries, the compliance surfaces they touch, and the prohibited structures that would turn them into a compliance liability. It implements Operating Article II of the Compact.

## 2. The Convertibility Boundary

| Level | Description | Legal Exposure |
|---|---|---|
| **Closed-loop** | Internal only, non-redeemable, non-transferable outside | Lowest |
| **Mutual credit** | Members extend and receive credit among themselves | Moderate |
| **Semi-closed** | Redeemable for external compute/services via intermediary | Counsel required |
| **Convertible** | Exchangeable for fiat/crypto | Full regulatory regime |

**The Compact defaults to closed-loop.** Any guild wishing to operate semi-closed or convertible must file a compliance annex and obtain local counsel sign-off.

## 3. The Alignment Principle

The less convertible a unit, the lower its tax and regulatory exposure, and the more it must be spent on learning, tools, compute, and local contribution. Therefore the Compact deliberately caps convertibility. The tax shield and the learning incentive are the same mechanism.

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

## 6. Permitted and Prohibited Structures

**Permitted:**
- Internal accounting units
- Bounty escrow with counsel oversight
- Compute barter under contract
- Mutual-aid pools within legal limits
- Mutual credit facilities, per GS-OPS-009 §2
- Advances against future contribution, per GS-OPS-009 §3
- Regulated pass-through fiat facilities at market rate, per GS-OPS-009 §4

**Prohibited:**
- Unlicensed money transmission
- Sanctions evasion
- Unregistered securities offering
- Wage substitution designed to avoid employment law
- Anonymous large-value settlement
- Convertible units without a compliance annex
- Zero-interest or below-market fiat lending from the guild to a member (GS-OPS-009 §5)
- Fiat lending from the mutual credit pool (GS-OPS-009 §5)

**Runtime:** `RS-INF-002` §7.2 prohibits `/convert`, `/redeem`, `/transfer`, `/purchase`, `/withdraw` endpoints. Their absence is structural. Mutual credit and advance events are recorded in the ledger as `advance_issued` and `advance_settled`; they are not conversion events.

## 7. Private Arrangements Between Members

This Annex governs the guild's structures and the credits instrument. It does not govern arrangements members make between themselves outside those structures.

If members arrange credit, exchange, or support privately, the guild does not review, endorse, or condemn those arrangements. Members are responsible for their own conduct and their own legal compliance in their own jurisdictions. The guild's protection extends to guild work under guild structures, not to private arrangements outside them.

The full statement of this position is in GS-OPS-009 §6.

## 8. Per-Guild Compliance Annex Requirement

Every guild operating any non-closed-loop instrument files a Compliance Annex reviewed by local counsel. The annex names: instrument type, jurisdiction(s), legal regime, mitigation applied, counsel contact.

## 9. Cross-References

| Document | Relationship |
|---|---|
| GS-FND-002 Art. II, Art. III | Non-convertibility, tax integrity |
| GS-CHR-004 Civic Substitution | Tax annex and civic provision |
| GS-CHR-002 Merit Protocol | Merit system, separate from Credits |
| GS-OPS-005 Structural Insulation | Entity structure hosting Credits |
| GS-OPS-006 Financial Resilience | Reserve distribution |
| GS-OPS-008 | Treasury allocation, exchange between reserve assets |
| GS-OPS-009 | Emergency liquidity and mutual credit mechanisms |
| GS-MTX-005 Credit Exposure Matrix | Full exposure matrix |
| RS-INF-002 Ledger Schema | Storage and API boundary |

---
doc: GS-OPS-008
title: Treasury and Asset Allocation Protocol
status: draft
category: operations
depends_on: [GS-FND-002, GS-OPS-004, GS-OPS-005, GS-OPS-006, GS-OPS-009]
review_cycle: annual
---

# GS-OPS-008 — Treasury and Asset Allocation Protocol

Specifies how a guild manages its reserves: how it apportions them across asset classes, how it exchanges between them lawfully, and how it acquires new capital. It is the fund-management layer that sits on top of the structural rules in GS-OPS-005 and the distribution thresholds in GS-OPS-006.

This document does not permit credits to become convertible. Article II of the Compact stands. The distinction is between *the guild's treasury holding and exchanging assets* (permitted, this document) and *the credits instrument being exchangeable for external value* (prohibited, Article II).

## 1. Purpose

A guild holds reserves. Those reserves must be allocated across asset classes (cash, sovereigns, metals, crypto, compute, IP), rebalanced when conditions change, and exchanged when the guild needs a different asset to meet an obligation. The guild also acquires new capital over time — through grants, revenue, membership, and possibly lawful instruments.

GS-OPS-006 specifies how much of a reserve can sit in one institution, jurisdiction, currency, or legal form. It does not specify what *mix* of assets the reserve is composed of, or how the guild moves between them, or how it acquires more.

This document fills those three gaps. It does not weaken GS-OPS-005 or GS-OPS-006.

## 2. Definitions

- **Reserve asset class.** A category of holding with distinct risk, liquidity, and compliance properties. The classes recognized by this document are: operating cash, short-term sovereign securities, physical precious metals, digital assets held in regulated custody, compute credits, and intellectual property.
- **Allocation policy.** A guild's written statement of target percentages across reserve asset classes, with permitted bands, rebalancing rules, and concentration limits.
- **Exchange event.** A transaction in which a guild converts one reserve asset into another — for example, selling sovereigns to purchase compute, or converting EUR to SGD to meet a vendor obligation. An exchange event is between the guild's own reserve assets. It is not a conversion of credits to external value.
- **Capital acquisition.** The acquisition of new reserves from outside the guild. Includes grants, donations, revenue from bounty work or compute provision, membership fees, and — where lawful and disclosed — borrowing or issuance of instruments.
- **Capital instrument.** A financial instrument issued by a guild to an outside party in exchange for capital, with an expectation of return. Includes debt instruments, equity-like instruments, and any tokenized equivalent.

## 3. Asset Allocation Policy

Every guild with reserves above a threshold set in its Local Guild Charter (GS-CHR-010) maintains a written Allocation Policy. The policy declares:

### 3.1 Target Allocation

Target percentages across the reserve asset classes the guild holds. Example structure (not prescriptive; the guild sets its own):

| Asset class | Target band | Liquidity | Custody |
|---|---|---|---|
| Operating cash | 20–30% | 24 hours | Multi-institution (GS-OPS-006 §4.1) |
| Short-term sovereigns | 30–40% | 24–72 hours | Multi-jurisdiction (§4.2) |
| Physical metals | 5–15% | 72 hours | Licensed custodian |
| Digital assets (regulated custody) | 0–10% | 24 hours | Licensed custodian only |
| Compute credits | 10–20% | 24 hours | Multi-provider |
| IP and long-term | remainder | 90 days | Direct ownership |

The policy names the rationale for each band. "Diversification" is not a rationale. The rationale states what risk the band hedges.

### 3.2 Rebalancing

The policy states when and how the guild rebalances. Minimum: annual review, plus rebalancing when any asset class breaches its band by more than a declared threshold (e.g., 5 percentage points).

### 3.3 Concentration Limits

In addition to GS-OPS-006 §4 (institutional, jurisdictional, currency, legal form, counterparty), the policy declares per-asset-class limits. Example: no more than 15% of reserves in any single digital asset.

### 3.4 Review

The Allocation Policy is reviewed annually and whenever a material event occurs (a currency crisis in a holding jurisdiction, a counterparty failure, a change in the guild's mission). Reviews are recorded in the guild's transparency report.

## 4. Lawful Exchange Between Reserve Assets

When the guild needs to exchange one reserve asset for another — to pay a vendor in a different currency, to liquidate sovereigns for compute, to rebalance — the exchange is an Exchange Event. Every Exchange Event satisfies:

1. **Between the guild's own reserve assets.** Not between credits and external value. Not between a member's credits and fiat. Between two assets the guild already holds.
2. **Regulated counterparty.** Exchanges go through a regulated broker, exchange, or custodian, not a peer-to-peer counterparty without KYC.
3. **Sanctions and AML screening.** The counterparty and the destination are screened under the same standards as any other treasury flow (GS-OPS-004 §3.3).
4. **Tax documentation.** The exchange is documented for tax purposes in every jurisdiction where the guild is registered or holds the asset.
5. **Records.** Each Exchange Event is recorded: date, assets exchanged, amounts, counterparty, purpose, compliance confirmations.
6. **Aggregated disclosure.** The guild's annual transparency report includes aggregate exchange activity by asset class. No individual trade disclosure required.

**What is not permitted:** exchanges designed to defeat a lawful obligation, exchanges with sanctioned parties, exchanges structured to hide beneficial ownership, exchanges that create an undisclosed concentrated position. GS-OPS-005 §6 and §9 apply in full.

## 5. Capital Acquisition

### 5.1 Ordinary Acquisition

Grants, donations, bounty revenue, compute provision revenue, and membership fees are ordinary capital acquisition. They satisfy:

- Source identification and documentation (GS-OPS-004 §3.2)
- Sanctions and AML screening
- Tax recording
- Gift/contribution vs. taxable income distinction

No additional approval required beyond the guild's own internal governance.

### 5.2 Borrowing

A guild may borrow. Borrowing is subject to:

- GS-OPS-005 §4 (no direct sovereign counterparty)
- GS-OPS-005 §8 (concentration — no single lender above one-third of reserves)
- GS-CHR-005 §2.6 (Entanglement Drift — a guild must not become the concentrated creditor of a sovereign, and must not become so indebted to one lender that the lender's hostility could end the guild)
- Documentation of terms, rates, and covenants in the transparency report (aggregate)

Borrowing that would trigger Entanglement Drift is prohibited. Borrowing that is diversified, documented, and lawful is permitted.

**Borrowing is distinct from lending.** This section covers the guild as borrower. The guild as lender to members is governed by GS-OPS-009, which specifies three mechanisms — mutual credit, advance against contribution, and regulated pass-through — and prohibits zero-interest fiat lending from the guild to a member.

The guild does not lend fiat at below-market rates. A member needing fiat goes through the regulated pass-through in GS-OPS-009 §4. A member needing internal credits goes through the mutual credit facility in GS-OPS-009 §2 or the advance mechanism in GS-OPS-009 §3.

### 5.3 Capital Instruments

A guild may issue a capital instrument (debt or equity-like) to outside parties only if all of the following hold:

1. **Per-jurisdiction compliance annex.** The guild files a compliance annex covering securities law, disclosure obligations, and investor protection law in every jurisdiction where the instrument is offered.
2. **Counsel sign-off.** Local counsel in every offering jurisdiction signs off that the issuance complies.
3. **No credit conversion.** The instrument does not entitle the holder to convert Guild Credits to external value, or to any conversion that would violate Article II.
4. **No governance capture.** The instrument does not confer voting rights, board seats, or decision rights in the guild's internal governance. If a guild wants to offer governance-linked instruments, that is a change to the Compact and is not permitted under this document.
5. **Disclosure.** The issuance is disclosed in the guild's transparency report: amount, instrument type, jurisdiction of offering, aggregate holder count. Individual holders are not disclosed unless required by law.

A capital instrument that does not satisfy all five conditions is prohibited. It is prohibited not because capital acquisition is wrong, but because a non-compliant instrument is a securities-law liability and a governance-capture risk in one wrapper.

### 5.4 What Capital Acquisition Does Not Authorize

- It does not authorize making Guild Credits convertible. Article II stands.
- It does not authorize granting decision rights to outside capital. Compact §7 (Authority Article) stands.
- It does not authorize concentration above the thresholds in GS-OPS-005 §8 and GS-OPS-006 §4.5.
- It does not authorize any structure that fails GS-OPS-005 §6 (disclosure boundary).

Capital acquisition is legitimate. Taking on outside money is not the same as taking on outside authority.

## 6. Digital Assets as a Reserve Asset Class

A guild may hold digital assets as a reserve asset if and only if all of the following hold:

1. **Regulated custody.** The assets are held through a licensed custodian in a jurisdiction with a functioning regulatory regime for digital-asset custody. Self-custody of reserve assets is prohibited (it defeats the distribution requirement and creates a single-key failure point).
2. **Disclosed on lawful request.** The holding is disclosed to lawful authorities on request under GS-OPS-005 §6.
3. **Sanctions screening.** The assets were not acquired from a sanctioned party and are not held on behalf of one.
4. **Tax documented.** The holding is documented for tax in every jurisdiction where it is held or where the guild is registered.
5. **No conversion to credits.** The digital asset is a reserve the guild holds. Members do not receive digital assets in exchange for credits. Credits remain internal under Article II.

**What is prohibited:**

- A digital asset held in self-custody, or held through an unregulated intermediary, or held in a way that fails lawful inquiry.
- A digital asset issued or promoted by the guild as a member benefit, a reward, or a currency.
- Any structure in which the digital asset functions as an internal currency, a credits substitute, or a means of converting credits to external value.
- Any use of digital assets to defeat a lawful obligation.

The line is: **the guild may hold digital assets as it may hold gold.** The guild does not issue digital assets, does not make them exchangeable for credits, and does not use them as a payment system for members.

## 7. Private Arrangements

The treasury rules in this document govern the guild's own reserves and the guild's own transactions. They do not govern arrangements members make between themselves outside the guild's structures.

If members arrange credit, exchange, or support between themselves privately — along the lines of the mechanisms in GS-OPS-009 or otherwise — the guild does not review, endorse, or condemn those arrangements. Members are responsible for their own conduct and their own legal compliance in their own jurisdictions. The guild's protection (Defense Fund, Chamber, Counsel Network) extends to guild work under guild structures, not to private arrangements outside them.

This is the same position stated in GS-OPS-009 §6.

## 8. Prohibited Activities

None of the following are permitted, regardless of how they are characterized:

- Conversion of Guild Credits to fiat, crypto, or any external store of value (Compact Article II).
- Any endpoint, function, or workflow that converts credits to external value (RS-INF-002 §7.2).
- Any capital instrument that grants governance rights or conversion rights (this document §5.3).
- Any digital asset holding that fails §6 conditions.
- Any exchange event designed to defeat a lawful obligation or evade sanctions.
- Any structure that fails GS-OPS-005 §6 (disclosure boundary).
- Any concentration above GS-OPS-005 §8 or GS-OPS-006 §4 thresholds, including through capital instruments.
- Zero-interest fiat lending from the guild to a member (GS-OPS-009 §5).

## 9. Compliance Surfaces

Every treasury operation touches, at minimum:

- **Tax** in each holding jurisdiction.
- **AML/KYC** where required by the institution, custodian, or broker.
- **Sanctions** in each jurisdiction where any counterparty operates.
- **Securities law** for any capital instrument offering.
- **Money transmission** for any exchange involving a third party.
- **Data protection** for records containing counterparty information.
- **Disclosure boundary** (GS-OPS-005 §6) for all reserve holdings.

Per-jurisdiction review is documented in the guild's Legal Annex (GS-CHR-010 §2.16).

## 10. Transparency

Each guild publishes in its annual transparency report:

- The target allocation bands (not the actual amounts, which are sensitive).
- Aggregate reserve composition by asset class (ranges, not precise figures).
- Aggregate exchange activity (by asset class, no individual trades).
- Any capital instrument issued, with amount, type, and jurisdiction.
- Any borrowing above the guild's declared threshold.
- Any digital-asset holding, by class and custodian jurisdiction.

Individual counterparties, amounts, and account details are not published. They are available to lawful authorities on request under GS-OPS-005 §6.

## 11. Cross-References

| Document | Relationship |
|---|---|
| GS-FND-002 Art. II | Credits non-convertibility — unchanged by this document |
| GS-FND-002 Art. III | Tax-Integrity Floor |
| GS-FND-002 §5 Principle II | Flow over hoarding — allocation serves mission, not accumulation |
| GS-CHR-005 §2.2, §2.6 | Accumulation and Entanglement Drift |
| GS-OPS-004 | Compute and treasury compliance — the compliance layer this document sits on |
| GS-OPS-005 §4, §6, §8 | Counterparty rules, disclosure boundary, anti-concentration |
| GS-OPS-006 §4, §5 | Distribution requirements and contingency pool |
| GS-OPS-009 | Emergency liquidity — the guild as lender to members |
| GS-MTX-005 | Credit exposure — confirms credits remain internal |
| RS-INF-002 §7.2 | API prohibition of conversion endpoints |

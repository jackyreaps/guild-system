---
doc: GS-OPS-010
title: Tiered Closed-Loop Unit Hierarchy
status: draft
category: operations
depends_on: [GS-FND-002, GS-CHR-003, GS-OPS-004, GS-OPS-008, GS-OPS-009]
review_cycle: annual
---

# GS-OPS-010 — Tiered Closed-Loop Unit Hierarchy

Defines the tiered relationship between the guild's internal units — hub credits, guild credits, and merit — and specifies the flow rules between tiers. It exists to make the upward-consolidation path explicit while prohibiting the downward and external paths that would collapse the closed-loop structure.

The core rule: **units flow up, never down. What crosses the boundary is merit, artifacts, and the member — not the credit instrument.**

## 1. Purpose

A guild operates across multiple contexts: hubs (Titanos, game environments, VR environments), the guild-wide ledger, and the wider world. Each context may have its own internal unit. This document defines how those units relate, which direction value may flow between them, and what may legitimately cross the boundary between the guild's internal economy and the outside world.

It does not create new units. It specifies the rules that govern units that already exist (hub credits, guild credits) and the one permanent record that survives every boundary (merit).

## 2. Definitions

- **Hub.** A bounded operational context in which members participate — a Titanos deployment, a game environment, a VR environment, or any similar context. A guild may operate one or more hubs.
- **Hub credit.** An internal unit earned and spent within a single hub. Non-convertible, non-transferable outside the hub's defined context, unless consolidated upward per §4.
- **Guild credit.** The guild-wide internal unit (GS-CHR-003). Earned by contribution, spent on guild goods across all hubs. Non-convertible to external value (Compact Article II).
- **Merit.** The permanent, non-transferable, non-purchasable record of verified contribution (GS-CHR-002). It is not a unit; it is a record. It travels with the member.
- **Context boundary.** The line between one tier and another: hub → guild, guild → outside, hub → outside.
- **Consolidation.** The upward movement of hub credits into guild credits, within the guild's own ledger, at a published rate.
- **External value.** Fiat, cryptocurrency, or any external store of value.

## 3. The Three Tiers

### 3.1 Tier 3 — Hub Credits (Local)

Hub credits are earned and spent within a single hub. They are local: a hub credit earned in hub A is not directly spendable in hub B unless both hubs publish a consolidation path to guild credits and the member consolidates.

Hub credits are closed-loop within their hub by default. They are not convertible to external value. They are not transferable to members who have not earned them.

### 3.2 Tier 2 — Guild Credits (Guild-Wide)

Guild credits are the guild-wide unit (GS-CHR-003). They are earned by verified contribution to the guild, and spent on guild goods: compute, courses, tools, internal services, and other guild-provided resources.

Guild credits are closed-loop to the guild. They are not convertible to external value. They are not transferable outside the guild's ledger.

### 3.3 Tier 1 — Merit (Permanent)

Merit is not a unit. It is the permanent record of verified contribution, and it governs authority, calibration rights, and peer attestation weighting (GS-CHR-002).

Merit does not flow between tiers because it is not a flow. It is a record that survives every transition. A member who leaves a hub keeps their merit. A member who leaves a guild keeps their merit. A member who forks a guild keeps their merit.

Merit is the only thing in the hierarchy that crosses the context boundary. It travels as reputation, never as value.

## 4. The Flow Rules

### 4.1 Upward Consolidation — Permitted

Hub credits may be consolidated upward into guild credits. This is the only flow between tiers.

**Conditions for consolidation:**

1. **Published rate.** The hub publishes the consolidation rate in its charter or operating documentation.
2. **Within the guild's ledger.** Consolidation is recorded in the guild's ledger. It is not an external transaction.
3. **One direction.** Once consolidated, hub credits are extinguished and guild credits are issued. The reverse is not permitted.
4. **Non-premium.** The consolidation rate does not include a fee, a rent, or a premium. It is an administrative exchange at the published rate.
5. **Tax-documented.** The consolidation is recorded for tax purposes. If consolidation results in a taxable event in any jurisdiction, it is documented.

**Event:** `hub_consolidate` in the guild ledger, with `from_hub`, `from_amount`, `to_amount`, and `rate`.

### 4.2 Downward Flow — Prohibited

Guild credits may not be converted into hub credits. The reverse of consolidation does not exist.

**Why:** A downward flow creates a bridge between two closed-loop systems. A member who could convert guild credits to hub credits would have a two-hop path from guild credits to whatever the hub credits can reach. If the hub credits could ever touch external value, the guild credits would be transitively convertible. The one-way rule at the boundary is what preserves the closed-loop structure.

### 4.3 External Flow — Prohibited

No tier converts to external value. Not hub credits, not guild credits.

**Why:** Compact Article II. This is the foundation of the entire compliance posture. Removing it removes the armor.

### 4.4 Cross-Hub Flow — Via Guild Credits Only

Hub credits from hub A cannot be directly converted to hub credits from hub B. The only path between hubs is through guild credits: hub A credits → guild credits → hub B credits is not permitted (that would require downward flow). Hub A credits → guild credits is permitted, and the member now holds guild credits, which they may spend across all hubs.

The distinction: a member consolidates hub A credits up to guild credits, and then spends guild credits on hub B goods. The hub B goods are paid for with guild credits, not with hub B credits. Hub B credits are earned separately, within hub B.

## 5. What Crosses the Boundary

The context boundary — between the guild's internal economy and the outside world — is crossed by four things, none of which is a credit instrument:

### 5.1 Merit

Merit travels with the member. It is the portable record of verified contribution. A member who leaves a guild, joins another, or operates outside any guild carries their merit record with them. It is not converted, not transferred, not spent. It is a record.

### 5.2 Artifacts

Signed, published work. Artifacts are public property once published. They carry the member's attribution and the guild's provenance. They cross the boundary freely because they were never internal to it.

### 5.3 The Member

A member may leave the guild at any time (Compact §10). They take their skills, their track record, their relationships, and their merit. They do not take credits.

### 5.4 The Value of What Was Learned

A member who burns credits for a course or a compute allocation leaves with the knowledge, the skills, and any artifacts produced. The credits are consumed; the capability remains. This is the actual return on the member's contribution.

## 6. The Loose Taking Outside

What the guild does not do: it does not police private exchanges between members outside the guild's structures (GS-OPS-009 §7, GS-OPS-008 §8). If a member privately arranges to exchange their guild credits with another party for something of value, the guild does not review, endorse, or condemn the arrangement. The member acts alone, bears their own legal responsibility in their own jurisdiction, and the guild's protection does not extend to private arrangements outside its structures.

What the guild does not do: it does not provide any structural path for credits to exit. The guild does not offer redemption, conversion, cash-out, or any mechanism by which credits become external value. The structure is closed-loop by design.

The distinction is important:

- **Private arrangements** are outside the guild's authority and outside the guild's protection.
- **Structural paths** are inside the guild's authority and do not exist for external conversion.

The "loose" part is real: the guild does not police what members do privately. The "taken outside" part is not: the structure itself provides no path.

## 7. Application to Hub Environments

A hub may be a Titanos deployment, a game environment, a VR environment, or any other bounded context. The hierarchy rules apply uniformly.

### 7.1 A Game or VR Hub

A game or VR hub may issue hub credits earned by play or participation. Those hub credits:

- Are earned within the hub.
- Are spent within the hub.
- May be consolidated upward into guild credits at a published rate, if the hub is guild-operated and the consolidation path exists.
- Are not convertible to external value.
- Are not bridgeable to any other closed-loop unit outside the consolidation path.

### 7.2 Jurisdiction

A hub environment is not jurisdiction-free. The server is in a country. The operator is a legal entity in a country. The members are physically in countries. The payment rails touch banks in countries. Every tier of the hierarchy is subject to the law of every jurisdiction it touches.

The safety of the hierarchy comes from its closed-loop structure, not from any jurisdictional gap. A closed-loop unit is safe because no conversion exists for the law to reach, not because the environment is somehow outside jurisdiction.

### 7.3 The One-Way Rule Applies to Every Hub

Each hub's credits are a separate instrument. They consolidate upward to guild credits. They do not consolidate downward. They do not bridge to other hubs directly. They do not convert to external value.

The same one-way rule that governs Resileos commercial credits (GS-OPS-004 §2.6) governs every hub credit.

## 8. What the Hierarchy Is Not

- **It is not a bridge between external systems.** A unit that could reach external value through any path in the hierarchy would make every tier above it convertible.
- **It is not a two-way system.** Downward flow is prohibited because a two-way path creates a convertible instrument at every tier.
- **It is not a jurisdictional shield.** VR, game environments, and metaverses are subject to the law of every jurisdiction they touch. The closed-loop structure is the safety; the environment is not.
- **It is not a private exchange mechanism.** Members may arrange private exchanges outside the guild's structures, but those arrangements are not guild paths and the guild does not intermediate them.

## 9. Prohibited Flows

None of the following are permitted, regardless of how they are characterized:

- Downward flow from guild credits to hub credits.
- Direct flow between hub credits of different hubs.
- Any conversion of any tier to external value.
- Any bridge that would allow a hub credit to reach external value through a chain of conversions.
- Any mechanism that treats hub credits as equivalent to guild credits except through the published consolidation path.
- Any consolidation rate that includes a fee, rent, or premium.
- Any structure that fails GS-OPS-005 §6 (disclosure boundary).

## 10. Transparency

Each guild publishes in its annual transparency report:

- The hubs it operates, by name and context type.
- The consolidation rate for each hub that has a consolidation path.
- Aggregate consolidation activity (by hub, no individual member details).
- Any changes to the consolidation rate.

Individual member balances and consolidation activity are not published. They are visible to the member and to the guild's internal governance.

## 11. Cross-References

| Document | Relationship |
|---|---|
| GS-FND-002 Art. II | Credits non-convertibility — the foundation this document preserves |
| GS-CHR-002 | Merit as the permanent record that travels with the member |
| GS-CHR-003 §6 | Permitted and prohibited structures |
| GS-OPS-004 §2.6 | The one-way rule — fiat never becomes credits, credits never become fiat |
| GS-OPS-008 §5 | Allocation of reserves to members |
| GS-OPS-009 §5 | Compute allocation — burn, pool draw, advance |
| GS-OPS-009 §7 | Private arrangements — the "loose" position stated |
| RS-INF-002 §4 | Ledger records `hub_consolidate` events |

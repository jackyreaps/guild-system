---
doc: GS-CHR-008
title: Fork and Secession Protocol
status: draft
category: charter
depends_on: [GS-FND-002]
review_cycle: annual
---

# GS-CHR-008 — Fork and Secession Protocol

## 1. Purpose

The Templars had no fork mechanism. When the Order drifted, the only options were obedience or destruction. The Fork and Secession Protocol guarantees that orientation can always leave — that members who believe a guild has sheared from its founding orientation can preserve that orientation in a new guild without destroying the old one.

This is the structural answer to 1307.

## 2. Principles

1. **Fork is a right, not a privilege.** Any member of a chartered guild may propose a fork.
2. **Forks are non-aggressive.** Neither fork nor parent guild may attack the other.
3. **Assets, merit, and artifacts follow published rules.** No fork requires renegotiation.
4. **Aliases and keys are portable.** A member's moniker, keypair, and merit history move with the member.
5. **The Compact survives forks.** A fork does not exit the Guild System; it re-enters under a new charter.

## 3. What Constitutes a Fork

A fork occurs when:

- Two or more members of a chartered guild declare a new guild.
- The new guild files its own Local Guild Charter (GS-CHR-010).
- The new guild adopts the Compact.
- The new guild is attested by at least one peer guild not under its own charter.

Until attestation, the fork is a *provisional guild*. It cannot participate in merit recognition or interoperability.

## 4. The Fork Process

### 4.1 Proposal

Any member publishes a fork proposal to the parent guild. The proposal names:

- The new guild's founding orientation.
- The reason for the fork (usually: the parent has sheared from the original orientation).
- The members who intend to join.
- The artifacts, merit, and obligations intended to move.

The proposal is public within the parent guild.

### 4.2 Response Period

The parent guild has 30 days to respond. The response may be an acknowledgment, a counter-proposal, or a rejection. Rejection does not prevent the fork.

### 4.3 Declaration

After 30 days, if the fork proceeds, the declaring members file the new guild's Local Charter and adopt the Compact. The new guild is now independent.

### 4.4 Asset and Obligation Division

- **Artifacts.** Public artifacts remain public. Attribution is preserved (authored by X while in guild Y). Both guilds may claim citation rights.
- **Merit.** Members carry their own merit history. The parent guild's merit ledger retains a record of contributions made while in the parent. The new guild's merit ledger starts fresh from the point of fork.
- **Obligations.** Legal obligations made by the parent guild do not transfer unless explicitly named in the fork proposal and accepted by the new guild.
- **Reserves.** Reserves held by the parent guild remain the parent's. The new guild starts with its own.

### 4.5 Key Continuity

- Member monikers and keypairs move with the member.
- The new guild issues new guild-level keys.
- Attestations signed before the fork remain valid and traceable to their issuer.

## 5. Non-Aggression

- Neither guild may publish defamatory material about the other.
- Neither guild may interfere with the other's attempts to attract members.
- Neither guild may claim the other's artifacts as its own without attribution.
- Disputes between fork and parent go through GS-CHR-007.

## 6. Fork Conditions in the Local Charter

Every guild's Local Guild Charter declares the specific conditions under which its members may fork to preserve the founding orientation. Examples:

- The guild's founding orientation has materially changed without amendment.
- The guild's funding concentration exceeds a declared threshold.
- The guild's governance has become opaque.
- The guild has entered an entanglement the charter prohibits.

The declared conditions are the member's protection. A guild that removes the fork conditions has sheared.

## 7. The Frame Profile

Each guild's `meta.frame_profile` (`RS-INF-003`) records fork conditions in the ledger. When a member invokes a fork condition, the record is the evidence.

## 8. Cross-References

| Document | Relationship |
|---|---|
| GS-FND-002 §10 | Fork and exit |
| GS-FND-002 §9 | Peer attestation |
| GS-CHR-005 §4 | Drift Remedy Ladder Step 6 |
| GS-CHR-007 | Dispute resolution during and after fork |
| GS-CHR-010 | Local Guild Charter Template (fork conditions required) |
| RS-INF-003 | Frame profile records fork conditions |

---
doc: GS-OPS-003
title: Distribution and Mirroring Protocol
status: draft
category: operations
depends_on: [GS-FND-002]
review_cycle: annual
---

# GS-OPS-003 — Distribution and Mirroring Protocol

## 1. Purpose

A published artifact that exists in one place can be deleted. A published artifact that exists in many places is durable. This Protocol specifies how the Guild System ensures that artifacts survive takedowns, deplatforming, and infrastructure failure.

## 2. Principles

1. **Content-addressed.** Every artifact is identified by its hash, not its URL.
2. **Redundant.** Every artifact exists in at least three independent mirrors.
3. **Jurisdictionally distributed.** Mirrors are in at least two jurisdictions.
4. **Lawful.** Mirrors comply with lawful takedowns — but a lawful takedown of one mirror does not remove the artifact from the network.
5. **Transparent.** Every takedown is logged and reported.

## 3. Mirror Types

- **Content-addressed storage** (IPFS, Arweave, or equivalent).
- **Open-source repository hosts** (GitHub, GitLab, Codeberg).
- **Independent mirrors** operated by member guilds.
- **Archival services** (Internet Archive, Software Heritage, or equivalent).

At least three of the above, across at least two of the categories above.

## 4. Takedown Handling

If a mirror receives a lawful takedown request:

1. The mirror operator complies with the lawful order (the Guild System does not resist valid court orders).
2. The takedown is logged.
3. The artifact remains available on other mirrors.
4. The takedown is published in the transparency report, subject to legal advice.

If the takedown is predatory (fails the Legitimacy Test, GS-CHR-006 §6):

1. The mirror operator may challenge the order (with counsel).
2. The Chamber coordinates the challenge (GS-CHR-006 §8.3 or §8.4).
3. The artifact remains available on other mirrors while the challenge proceeds.

## 5. Transparency Reporting

Each guild publishes an annual report listing:

- Mirrors maintained.
- Takedowns received and their handling.
- Artifacts added, removed, or migrated.

Aggregated; no member identity disclosed.

## 6. Cross-References

| Document | Relationship |
|---|---|
| GS-FND-002 §4 Art. I | Public or authorized data only |
| GS-CHR-001 §3 | Armor of transparency |
| GS-CHR-006 §8 | Demand Determination Scale |
| RS-INF-001 §3 | `world:` namespace for registered artifacts |

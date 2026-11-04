# The Guild System

A polycentric, merit-based architecture for collective intellectual work.

The Guild System is a set of structural, legal, and operational documents that define how autonomous guilds interoperate through a shared protocol: merit recognition, contribution verification, idea protection, and lawful civic provision. It is not a single organization. It has no headquarters and no central authority. It is a meta-structure — a minimal shared layer over many sovereign local guilds.

## What this repository is

This repository contains the **policy layer** of the Guild System: the Compact, the Charters, the Operations protocols, the Matrices, and the Reference documents. It does not contain runtime code, hosted infrastructure, or framework claims.

## The three-project boundary

The Guild System operates alongside two other projects. They meet at defined interfaces and do not merge.

| Project | Repository | Owns | Does not own |
|---|---|---|---|
| **Guild System** | this repo | Compact, charters, merit policy, legal and ops | Runtime store, API host |
| **QD-TER / Human Medium** | [jackyreaps/QD-TER-Human-Medium](https://github.com/jackyreaps/QD-TER-Human-Medium) | Framework claims, measurements, `/Guild/README.md` pointer | Guild policy, hosted console |
| **Resileos-QAI** | [jackyreaps/Resileos-QAI](https://github.com/jackyreaps/Resileos-QAI) | Titanos, hubs, `guild_ledger.json`, world assets | Compact authority, peer attestation |

**Policy stays here. Running state lives in Resileos. Framework truth lives in Human Medium.** They meet at namespaced subjects (`org:guild:*`, `world:*`, `user:*`, `guild_ledger.json`), not merged repositories.

## Where to start

1. **[The Compact](foundation/GS-FND-002-compact.md)** — the founding document. Four Operating Articles, four Structural Principles, the Authority Article, core definitions, and minimum standards. Everything else derives from it.
2. **[The Foundation Layer Map](foundation/GS-FND-003-foundation-layer.md)** — a short reader's map explaining how the Founding Signal and the Compact relate, and how the operational layer fits under them.
3. **[The Founding Signal](foundation/GS-FND-001-founding-signal.md)** — the public-facing statement of purpose and culture.
4. **[The Master Index](INDEX.md)** — every document in the system, with status and cross-references.

## Core principles

The Compact establishes four **Operating Articles** (economic and data mechanics) and four **Structural Principles** (spatial and political architecture):

**Operating Articles**
1. Public or authorized data only
2. Non-convertible system credits
3. The Tax-Integrity Floor
4. Civic substitution over capital accumulation

**Structural Principles**
1. Exemption through provision
2. Velocity of flow over hoarding
3. Polycentricity over patronage
4. Verifiability over secrecy

## How the system is governed

There is no central authority. Authority is granted by specific documents to specific bodies for specific purposes, bounded in time and scope, subject to sunset and revocation (Compact §7). Peer attestation replaces central enforcement (Compact §9). Fork is always available (Compact §10).

## Status

This is a live architectural document set. All documents in the repository are in draft status pending ratification by chartered guilds. **[INDEX.md](INDEX.md)** is the authoritative status record.

## Cross-repo pointers

- **Resileos-QAI implementation program** — `RS-INF-001` lives at `Resileos-QAI/docs/320-titanos/guild-infra-program.md`. It is the program of record for the runtime hub and ledger. It binds to this Compact and to GS-CHR-002 / GS-CHR-003, but it is not copied into this repo.
- **Ledger schema** — `RS-INF-002` lives at `Resileos-QAI/docs/320-titanos/ledger-schema.md`. It implements the Merit/Credits decoupling defined in this Compact.
- **Frame profile** — `RS-INF-003` lives at `Resileos-QAI/docs/320-titanos/frame-profile.md`. It defines how a guild's founding orientation and shear detection are recorded in the ledger.
- **Framework reference** — the QD-TER Human Medium framework and the `/Guild/README.md` pointer live in `jackyreaps/QD-TER-Human-Medium`.

## License

[LICENSE file to be added]

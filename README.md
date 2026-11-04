# The Guild System

A polycentric, merit-based architecture for collective intellectual work.

The Guild System is a set of structural, legal, and operational documents that define how autonomous guilds interoperate through a shared protocol: merit recognition, contribution verification, idea protection, and lawful civic provision. It is not a single organization. It has no headquarters and no central authority. It is a meta-structure — a minimal shared layer over many sovereign local guilds.

**Canonical location.** This repository is the single source of truth for Guild System policy. The QD-TER Human Medium repository carries a pointer to this repo at `Guild/README.md`; it does not carry the policy. The Resileos-QAI repository implements the runtime; it does not carry the policy either.

## What this repository is

The **policy layer**: the Compact, the Charters, the Operations protocols, the Matrices, and the Reference documents. It does not contain runtime code, hosted infrastructure, or framework claims.

## The three-project boundary

| Project | Repository | Owns | Does not own |
|---|---|---|---|
| **Guild System** | this repo | Compact, charters, merit policy, legal and ops | Runtime store, API host |
| **QD-TER / Human Medium** | [jackyreaps/QD-TER-Human-Medium](https://github.com/jackyreaps/QD-TER-Human-Medium) | Framework claims, measurements, pointer to this repo | Guild policy, hosted console |
| **Resileos-QAI** | [jackyreaps/Resileos-QAI](https://github.com/jackyreaps/Resileos-QAI) | Titanos, hubs, `guild_ledger.json`, world assets | Compact authority, peer attestation |

**Policy stays here. Running state lives in Resileos. Framework truth lives in Human Medium.** They meet at namespaced subjects (`org:guild:*`, `world:*`, `user:*`, `guild_ledger.json`), not merged repositories.

## Where to start

1. **[The Compact](foundation/GS-FND-002-compact.md)** — the founding document. Four Operating Articles, four Structural Principles, the Authority Article, core definitions, and minimum standards. Everything else derives from it.
2. **[The Foundation Layer Map](foundation/GS-FND-003-foundation-layer.md)** — a short reader's map explaining how the Founding Signal and the Compact relate, and how the operational layer fits under them.
3. **[The Founding Signal](foundation/GS-FND-001-founding-signal.md)** — the public-facing statement of purpose and culture.
4. **[The Master Index](INDEX.md)** — every document in the system, with status, ratification state, and cross-references.

## Core principles

Four **Operating Articles** (economic and data mechanics):

1. Public or authorized data only
2. Non-convertible system credits
3. The Tax-Integrity Floor
4. Civic substitution over capital accumulation

Four **Structural Principles** (spatial and political architecture):

1. Exemption through provision
2. Velocity of flow over hoarding
3. Polycentricity over patronage
4. Verifiability over secrecy

## How the system is governed

There is no central authority. Authority is granted by specific documents to specific bodies for specific purposes, bounded in time and scope, subject to sunset and revocation (Compact §7). Peer attestation replaces central enforcement (Compact §9). Fork is always available (Compact §10).

## Status

All documents are in **draft** status pending ratification by chartered guilds. Draft means content is written and published; it does not mean the document is in force. Only the Compact binds, and it binds provisionally until ratified.

**[INDEX.md](INDEX.md)** is the authoritative status record, with a ratification column.

## Cross-repo pointers

| Document | Lives at | Relationship |
|---|---|---|
| `RS-INF-001` Guild Infrastructure Program | `Resileos-QAI/docs/320-titanos/guild-infra-program.md` | Runtime implementation program — **planned, not yet uploaded** |
| `RS-INF-002` Guild Ledger Schema | `Resileos-QAI/docs/320-titanos/ledger-schema.md` | Data contract — **planned, not yet uploaded** |
| `RS-INF-003` Guild Frame Profile | `Resileos-QAI/docs/320-titanos/frame-profile.md` | Founding orientation in ledger form — **planned, not yet uploaded** |
| QD-TER Human Medium pointer | `QD-TER-Human-Medium/Guild/README.md` | Framework reference — exists |

The `RS-INF-*` documents are the implementation program of record. They are not copied here. They bind Resileos to this Compact; they do not amend it. Until they are uploaded to Resileos `main`, the pointers above are aspirational and are marked as such.

## License

[LICENSE](LICENSE) — see the file for terms.

## Security

See [SECURITY.md](SECURITY.md) for reporting hostile or predatory action against Guild members or guilds.

---
doc: GS-REF-003
title: Runtime Interface Boundary
status: draft
category: reference
depends_on: [GS-FND-002, GS-CHR-009, GS-CHR-012, GS-OPS-005]
runtime_refs: [RS-INF-001, RS-INF-002, RS-INF-003, RS-INF-004]
review_cycle: annual
---

# GS-REF-003 — Runtime Interface Boundary

A reference document. It states what the Guild System needs from a runtime, what Resileos provides, and what neither party may do. Its purpose is to keep authority off the runtime and keep policy out of the runtime's codebase.

## 1. Purpose

The Guild System and Resileos are separate projects with separate ownership. The Guild System owns policy. Resileos owns runtime. This document states the interface between them so that neither grows into the other.

It is a reference document. It does not create obligations. It cites the documents that do.

## 2. The Interface Table

| Guild System needs | Resileos surface | Resileos must not do |
|---|---|---|
| Membership and work tracking | `org:guild:*` hubs | Perform peer attestation |
| Merit and Credits balances | `guild_ledger.json` | Convert Merit to Credits, or Credits to fiat |
| Artifact publication | `world:*` + content hash | Adjudicate artifact disputes |
| Day flow | join → work → complete → burn → status | Grant or revoke legal authority |
| Founding orientation record | `meta.frame_profile` in the ledger | Assess whether the orientation has sheared |
| Rank and work board | RS-INF-003 | Appoint anyone to a network seat or class |
| Title and valor records | RS-INF-004 | Grant a title or valor credit without evidence |
| Emergency contact routing | Notification hooks | Coordinate defense or hold Defense Fund |
| Cross-guild recognition data | Attestation storage | Verify attestations on behalf of a guild |

## 3. What the Guild System Provides to Resileos

- The **Compact** (GS-FND-002) — the binding rules Resileos implements.
- The **charters** — the rules that constrain what a guild may do on the runtime.
- The **schemas** — `schemas/attestation.v1.json` and `schemas/local-charter.checklist.json` — the machine-readable forms Resileos validates against.
- The **frame profile fields** — `meta.frame_profile`, specified in RS-INF-002. These are the fields Resileos stores for founding orientation and shear detection. There is no separate frame-profile document; the specification lives in the ledger schema.
- The **portfolio bridge rules** — GS-CHR-012 §12. These govern how ranks, titles, and valor records feed representation, and they are the rules Resileos must not exceed.

## 4. What Resileos Provides to the Guild System

- A **running hub** where a chartered guild can execute the day flow (RS-INF-001).
- A **ledger** that stores Merit and Credits as decoupled balances (RS-INF-002).
- An **attestation store** that holds signed attestations in the GS-CHR-009 format.
- A **namespace scheme** (`org:guild:*`, `world:*`, `user:*`) that keeps guild state, artifacts, and operator preferences separate.
- A **rank and work board** (RS-INF-003) — local rank thresholds and work items that produce merit, credits, and optional title recommendations.
- A **title and valor registry** (RS-INF-004) — earned titles and recorded valor events per moniker per guild.

## 5. What Neither Party May Do

**Resileos may not:**

- Perform peer attestation. Attestation is a signed act by a peer guild (GS-FND-002 §9).
- Adjudicate a dispute between guilds. That is GS-CHR-007.
- Classify a legal demand. That is GS-CHR-006.
- Hold or move the Defense Fund. That is GS-CHR-006 §5.4.
- Execute a legal fork. That is GS-CHR-008.
- Implement ZKP identity verification as a mandatory gate. That is GS-CHR-011, and it is optional.
- Convert Merit to Credits or Credits to external value. Prohibited by Compact Art. II and RS-INF-002 §7.2.
- Appoint a Council member, Senate seat, Steward, Princeps, or Sovereign. Portfolios are evidence; bodies decide (GS-CHR-012 §12.2).
- Treat a rank name as a network office. A local rank named "steward" is not the Convocation Steward (GS-CHR-012 §12.2).

**The Guild System may not:**

- Require a specific runtime implementation. Any content-addressed, signed artifact store and any ledger satisfying RS-INF-002 are conforming. Resileos is one implementation.
- Amend its policy to match runtime convenience. The runtime adapts to the policy, not the reverse.
- Place policy in the runtime codebase. Policy lives in this repository.

## 6. The Soft Dependency

GS-CHR-009 §2 and §3 use the `world:` prefix in examples. This is illustrative. Any content-addressed, signed artifact store that publishes a stable `artifact_ref` and `artifact_hash` satisfies the Protocol. Resileos is one conforming implementation. The Guild System does not require Resileos, and a future implementation that satisfies the same schemas is equally valid.

The Guild System's dependency on Resileos is **operational** (a guild needs somewhere to run), not **architectural** (the policy does not name Resileos as the only valid runtime).

## 7. Cross-References

| Document | Relationship |
|---|---|
| GS-FND-002 §2 | Runtime pointer in the Compact |
| GS-CHR-009 §2, §3 | Artifact and attestation format |
| GS-CHR-012 §12 | Portfolio bridge — how ranks, titles, and valor feed representation |
| GS-OPS-005 §6 | Disclosure boundary that applies to the runtime's storage |
| RS-INF-001 | Guild infrastructure program (Resileos) |
| RS-INF-002 | Ledger schema — including `meta.frame_profile` |
| RS-INF-003 | Ranks and work board |
| RS-INF-004 | Titles and valor portfolio |

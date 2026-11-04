---
doc: GS-CHR-009
title: Interoperability Protocol
status: draft
category: charter
depends_on: [GS-FND-002, GS-CHR-002, GS-CHR-008]
review_cycle: annual
---

# GS-CHR-009 — Interoperability Protocol

## 1. Purpose

Defines how chartered guilds recognize each other's artifacts, merit attestations, and aliases. It is the document Resileos Phase C is blocked on — the attestation export format it defines is what `RS-INF-001` §6 Phase C implements.

The Protocol does not create a central authority. Recognition is peer-to-peer, signed, and verifiable without any service.

## 2. Artifact Standards

Every artifact recognized across guilds satisfies:

- **Content-addressed.** The artifact is identified by a cryptographic hash of its content.
- **Signed.** The publishing member signs the artifact with their moniker keypair.
- **Reproducible.** Verification instructions are published alongside the artifact.
- **Provenance-chained.** The artifact's history (who published, when, under what guild) is recorded.

The content-addressing and signing formats are the standards Resileos already uses for `world:` subjects (`RS-INF-001` §3).

## 3. The Attestation Export Format

A merit attestation that crosses guild boundaries is a signed JSON document with these fields:

```json
{
  "attestation_version": 1,
  "attestation_id": "att_<hash>",
  "issuer_guild": "<guild_id>",
  "issuer_moniker": "<moniker>",
  "issuer_public_key": "<key>",
  "artifact_ref": "world:<path>:<hash>",
  "artifact_hash": "<sha256>",
  "verification_evidence": {
    "method": "<enum>",
    "log_ref": "world:<path>:<hash>",
    "log_hash": "<sha256>"
  },
  "six_dimension_score": {
    "verification_strength": 0,
    "novelty": 0,
    "difficulty": 0,
    "downstream_use": 0,
    "robustness": 0,
    "teaching_value": 0
  },
  "issued_at": "<ISO-8601>",
  "signature": "<sig over all fields above>"
}

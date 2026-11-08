# GS-OPS-011 — Resileos board completion as merit candidate

status: draft
depends_on: [GS-CHR-002, schemas/attestation.v1.json]

A completed board item from a Resileos worker is a valid artifact for attestation.

## What Resileos emits

`complete_and_credit(guild_id, member, title, evidence)` returns a merit candidate:

- issuer_guild
- issuer_moniker
- artifact_ref
- verification_evidence
- score
- status: candidate

## What the guild still does

The guild process adds the public key and the signature, then records the attestation. Resileos does not sign and does not transfer merit.

## Cross-reference

Resileos document: `docs/guild-merit.md` in the Resileos-QAI repository.
Schema: `schemas/attestation.v1.json`.
Matrices: GS-MTX-003, GS-MTX-004.

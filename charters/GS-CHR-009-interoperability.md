---
doc: GS-CHR-009
title: Interoperability Protocol
status: draft
category: charter
depends_on: [GS-FND-002, GS-CHR-002, GS-CHR-008]
review_cycle: annual
---

# GS-CHR-009 — Interoperability Protocol

Defines how chartered guilds recognize each other's artifacts, merit attestations, and aliases. It is the document Resileos Phase C is blocked on — the attestation export format it defines is what `RS-INF-001` §6 Phase C implements.

The Protocol does not create a central authority. Recognition is peer-to-peer, signed, and verifiable without any service.

## 1. Purpose

Chartered guilds operate independently. They publish artifacts, award merit, and attest to peer guilds on different schedules, under different charters, using their own ledgers. This Protocol defines what it means for one guild to recognize another's work — the format, the trust handshake, and the revocation rules.

The Protocol is versioned. It is not a service. Any member of any guild can verify any attestation independently, given the artifact and the issuer's public key.

## 2. Artifact Standards

Every artifact recognized across guilds satisfies four conditions:

1. **Content-addressed.** The artifact is identified by a cryptographic hash of its content.
2. **Signed.** The publishing member signs the artifact with their moniker keypair.
3. **Reproducible.** Verification instructions are published alongside the artifact.
4. **Provenance-chained.** The artifact's history — who published, when, under what guild — is recorded.

The content-addressing and signing formats are the standards Resileos already uses for `world:` subjects (`RS-INF-001` §3).

## 3. The Attestation Export Format

A merit attestation that crosses guild boundaries is a signed JSON document. The fields below describe the structure; values are strings, integers, or nested objects as indicated.

```json
{
  "attestation_version": 1,
  "attestation_id": "att_<sha256-of-content>",
  "issuer_guild": "<guild-slug>",
  "issuer_moniker": "<moniker-slug>",
  "issuer_public_key": "<base64-public-key>",
  "artifact_ref": "world:<path>:<sha256>",
  "artifact_hash": "<sha256-hex>",
  "verification_evidence": {
    "method": "<enum>",
    "log_ref": "world:<path>:<sha256>",
    "log_hash": "<sha256-hex>"
  },
  "six_dimension_score": {
    "verification_strength": 0,
    "novelty": 0,
    "difficulty": 0,
    "downstream_use": 0,
    "robustness": 0,
    "teaching_value": 0
  },
  "issued_at": "<iso8601-timestamp>",
  "signature": "<base64-signature>"
}
```

A verifying guild can independently confirm:

- The artifact hash matches the referenced content.
- The verification evidence is retrievable and consistent.
- The signature is valid against the issuer's public key.
- The issuer is a member in good standing of the issuer guild, via the issuer guild's published membership record.

## 4. Recognition Rules

Guild A recognizes Guild B's attestation if and only if:

1. The attestation format is valid (§3).
2. The signature verifies.
3. The issuer guild is in good standing — attested within the current cycle per GS-FND-002 §9.
4. The verification evidence is independently reproducible.
5. Guild A has not issued a non-recognition notice under §6.

Recognition is per-attestation. A guild can recognize some attestations from another guild and not others. Recognition is not a binary relationship between guilds; it is a binary property of a single attestation.

## 5. Identity and Alias Resolution

A moniker is unique within a guild. The same moniker in two guilds refers to two distinct subjects unless the moniker's keypair has been explicitly linked.

**Key linkage.** A member may publish a linkage record stating: "I control moniker A in guild X and moniker B in guild Y." The record is signed by both keys. Guilds recognize the linkage if both signatures verify.

No linkage is required. Members may operate under unlinked monikers in different guilds. The system does not force cross-guild identity resolution.

## 6. Non-Recognition and Denunciation

A guild may refuse to recognize another guild's attestations by publishing a non-recognition notice. The notice names:

- The guild being non-recognized.
- The reason — for example, failed peer attestation, drift finding under GS-CHR-005, or invalid attestation format.
- The scope — all attestations, or specific categories.

Non-recognition is published, subject to member safety. It is not expulsion. The non-recognized guild continues to operate. It is simply not trusted by the recognizing guild for merit purposes.

A guild that has been non-recognized by two-thirds of guilds in good standing is no longer in the interoperability layer. It can still operate; it cannot participate in cross-guild merit recognition until the non-recognitions are lifted.

## 7. Revocation and Pruning

If a guild has been non-recognized, its attestations remain published but marked non-recognized in the public record. A verifying guild sees the non-recognition notice alongside the attestation.

If an attestation is found to be fraudulent, the issuer may revoke it by publishing a revocation record. Revocation is signed by the issuer. Revoked attestations are not recognized.

If a guild is pruned — through a drift finding under GS-CHR-005 or through the fork process under GS-CHR-008 — its attestations are marked with the pruning event.

## 8. Technical Handshake

The minimum trust handshake between two guilds:

1. Both publish their public keys and a signed membership record.
2. Both publish their attestation format version.
3. Both confirm compliance with this Protocol's current version.
4. Both publish any non-recognition notices they have issued.

No service is required. The handshake is the mutual publication of the above. Any member of either guild can verify the handshake.

## 9. Versioning

This Protocol is versioned. Version 1 is defined by this document. A version bump is required for:

- Changes to the attestation format.
- Changes to recognition rules.
- Changes to the trust handshake.

A guild that has not adopted the current version cannot issue recognized attestations until it does.

## 10. Cross-References

| Document | Relationship |
|---|---|
| GS-FND-002 §9 | Peer attestation |
| GS-CHR-002 | Merit Protocol — source of attestation content |
| GS-CHR-005 §4 | Drift findings trigger non-recognition |
| GS-CHR-007 | Fork disputes affect recognition scope |
| GS-CHR-008 | Fork does not break attestation traceability |
| GS-CHR-011 | Alias resolution — linkage records |
| RS-INF-001 §6 Phase C | Implements this Protocol's attestation export |
| RS-INF-002 | Ledger stores attestations; this Protocol defines their cross-guild format |

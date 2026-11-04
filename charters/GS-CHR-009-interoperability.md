---
doc: GS-CHR-009
title: Interoperability Protocol
status: draft
category: charter
depends_on: [GS-FND-002, GS-CHR-002, GS-CHR-008]
runtime_impl: [RS-INF-001, RS-INF-002]
review_cycle: annual
---

# GS-CHR-009 — Interoperability Protocol

Defines how chartered guilds recognize each other's artifacts, merit attestations, and aliases. It is the format Resileos Phase C implements, and the document that must be ratified before cross-guild attestations are honored.

The Protocol does not create a central authority. Recognition is peer-to-peer, signed, and verifiable without any service. The format is backend-agnostic: any content-addressed, signed artifact store that satisfies §2 is a conforming implementation. Resileos is one; it is not the only one.

## 1. Purpose

Chartered guilds operate independently. They publish artifacts, award merit, and attest to peer guilds on different schedules, under different charters, using their own ledgers. This Protocol defines what it means for one guild to recognize another's work — the format, the trust handshake, and the revocation rules.

The Protocol is versioned. It is not a service. Any member of any guild can verify any attestation independently, given the artifact and the issuer's public key.

## 2. Artifact Standards

Every artifact recognized across guilds satisfies four conditions:

1. **Content-addressed.** The artifact is identified by a cryptographic hash of its content.
2. **Signed.** The publishing member signs the artifact with their moniker keypair.
3. **Reproducible.** Verification instructions are published alongside the artifact.
4. **Provenance-chained.** The artifact's history — who published, when, under what guild — is recorded.

The `world:` prefix used in this Protocol and in §3 is illustrative. Any content-addressed artifact store that publishes a stable `artifact_ref` and `artifact_hash` satisfies this Protocol. Resileos is one conforming implementation. The Protocol does not require Resileos and does not require any specific storage backend. What it requires is that the artifact is content-addressed, signed, reproducible, and provenance-chained.

## 3. The Attestation Export Format

A merit attestation that crosses guild boundaries is a signed JSON document.

The canonical structure is defined by the JSON Schema at `schemas/attestation.v1.json`. A worked example is at `examples/attestation-sample.json`. The fields below describe the structure in prose; the schema is normative if the two diverge.

```json
{
  "attestation_version": 1,
  "attestation_id": "att_<sha256-of-canonical-serialization>",
  "issuer_guild": "<guild-slug>",
  "issuer_moniker": "<moniker-slug>",
  "issuer_public_key": "<base64-public-key>",
  "artifact_ref": "<content-addressed-reference>",
  "artifact_hash": "<sha256-hex>",
  "verification_evidence": {
    "method": "<enum>",
    "log_ref": "<content-addressed-reference>",
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

### 3.1 Field Semantics

- **`attestation_version`.** Integer. Currently `1`. Incremented only on breaking format changes.
- **`attestation_id`.** String matching `att_[a-f0-9]{64}`. The `att_` prefix followed by the SHA-256 of the canonical serialization of all fields except `attestation_id` and `signature`. This makes the ID self-verifying: any party can recompute it.
- **`issuer_guild`, `issuer_moniker`.** Lowercase slugs matching `[a-z0-9-]+`.
- **`issuer_public_key`.** Base64-encoded public key of the issuer's moniker keypair.
- **`artifact_ref`.** Content-addressed reference to the attested artifact. The format is implementation-defined; the requirement is that resolving `artifact_ref` yields content whose hash matches `artifact_hash`.
- **`artifact_hash`.** Lowercase hex SHA-256 of the artifact content.
- **`verification_evidence.method`.** Enumeration. See §3.2 for the accepted values.
- **`verification_evidence.log_ref`, `log_hash`.** Content-addressed reference to the verification log, and its SHA-256. The log must be retrievable; a verifier may re-run the verification from the log.
- **`six_dimension_score`.** Six integers from 0 to 5, per GS-CHR-002 §4.
- **`issued_at`.** ISO-8601 timestamp with timezone.
- **`signature`.** Base64-encoded signature over the canonical serialization of all fields except `signature`.

### 3.2 The `method` Enumeration

The `method` field must be one of:

| Value | Meaning |
|---|---|
| `proof_checker` | Verified by an independent proof checker |
| `proof_assistant_compilation` | Verified by compilation in a proof assistant |
| `execution_reproducible` | Verified by reproducible execution |
| `independent_replication` | Verified by independent replication of a benchmark |
| `vulnerability_reproduction` | Verified by reproducing the reported vulnerability |
| `independent_rerun` | Verified by an independent rerun of the audit |
| `independent_validation` | Verified by independent validation of a dataset |
| `independent_use` | Verified by independent use of the tool in another project |
| `verified_learner_outcome` | Verified by an audited learner outcome |
| `longitudinal_peer_attestation` | Verified by longitudinal peer observation |
| `two_member_peer_attestation` | Verified by two-member peer attestation — command contribution, per GS-CHR-002 §5 |

New values require a version bump (§9).

### 3.3 What a Verifier Can Independently Confirm

Given only the attestation and public resources:

1. The `artifact_hash` matches the resolved content at `artifact_ref`.
2. The `verification_evidence.log_hash` matches the resolved content at `log_ref`.
3. The `attestation_id` recomputes to the same value from the canonical serialization.
4. The `signature` verifies against `issuer_public_key`.
5. The `issuer_guild` is in good standing per GS-FND-002 §9.
6. The `issuer_moniker` is a current member of `issuer_guild` per that guild's published membership record.

A verifier who can confirm all six items has fully verified the attestation. Anything less is partial verification and should be recorded as such.

## 4. Recognition Rules

Guild A recognizes Guild B's attestation if and only if:

1. The attestation format is valid — conforms to `schemas/attestation.v1.json`.
2. The signature verifies against `issuer_public_key`.
3. The issuer guild is in good standing — attested within the current cycle per GS-FND-002 §9.
4. The verification evidence is independently reproducible — §3.3 items 1 through 4 pass.
5. Guild A has not issued a non-recognition notice under §6.

Recognition is per-attestation. A guild can recognize some attestations from another guild and not others. Recognition is not a binary relationship between guilds; it is a binary property of a single attestation.

## 5. Identity and Alias Resolution

A moniker is unique within a guild. The same moniker in two guilds refers to two distinct subjects unless the moniker's keypair has been explicitly linked.

**Key linkage.** A member may publish a linkage record stating: "I control moniker A in guild X and moniker B in guild Y." The record is signed by both keys. Guilds recognize the linkage if both signatures verify.

No linkage is required. Members may operate under unlinked monikers in different guilds. The system does not force cross-guild identity resolution. GS-CHR-011 defines the key hierarchy and linkage record format.

## 6. Non-Recognition and Denunciation

A guild may refuse to recognize another guild's attestations by publishing a non-recognition notice. The notice names:

- The guild being non-recognized.
- The reason — for example, failed peer attestation, drift finding under GS-CHR-005, or invalid attestation format.
- The scope — all attestations, or specific categories.

Non-recognition is published, subject to member safety. It is not expulsion. The non-recognized guild continues to operate. It is simply not trusted by the recognizing guild for merit purposes.

A guild that has been non-recognized by two-thirds of guilds in good standing is no longer in the interoperability layer. It can still operate; it cannot participate in cross-guild merit recognition until the non-recognitions are lifted.

## 7. Revocation and Pruning

If a guild has been non-recognized, its attestations remain published but marked non-recognized in the public record. A verifying guild sees the non-recognition notice alongside the attestation.

If an attestation is found to be fraudulent, the issuer may revoke it by publishing a revocation record. Revocation is signed by the issuer using the same keypair that signed the attestation. Revoked attestations are not recognized.

If a guild is pruned — through a drift finding under GS-CHR-005 or through the fork process under GS-CHR-008 — its attestations are marked with the pruning event. They are not deleted; they remain published with the pruning context.

Key revocation is handled separately by GS-OPS-002. An attestation signed with a key that has since been revoked remains published and is marked "signed with revoked key" — it is not automatically invalidated, because the signature was valid at time of signing. Recognition of such attestations is a per-verifier decision.

## 8. Technical Handshake

The minimum trust handshake between two guilds:

1. Both publish their public keys and a signed membership record.
2. Both publish their attestation format version.
3. Both confirm compliance with this Protocol's current version.
4. Both publish any non-recognition notices they have issued.

No service is required. The handshake is the mutual publication of the above. Any member of either guild can verify the handshake without contacting any server.

The handshake is a one-way publication per guild; two guilds "complete" the handshake when both have published the four items above and neither has published a non-recognition notice against the other. Non-recognition does not prevent the handshake; it prevents recognition of the non-recognized guild's attestations until the notice is withdrawn.

## 9. Versioning

This Protocol is versioned. Version 1 is defined by this document and `schemas/attestation.v1.json`.

A version bump is required for:

- Adding, removing, or renaming a required field in the attestation.
- Adding or removing a value in the `verification_evidence.method` enumeration.
- Changing the canonical serialization used for `attestation_id` or `signature`.
- Changing the recognition rules in §4.
- Changing the trust handshake in §8.

A guild that has not adopted the current version cannot issue recognized attestations until it does. Old attestations remain verifiable under their original version; the version is part of the format, and the schema for each version is retained.

## 10. Cross-References

| Document | Relationship |
|---|---|
| GS-FND-002 §9 | Peer attestation |
| GS-CHR-002 | Merit Protocol — source of attestation content and six-dimension scoring |
| GS-CHR-005 §4 | Drift findings trigger non-recognition |
| GS-CHR-007 | Fork disputes affect recognition scope |
| GS-CHR-008 | Fork does not break attestation traceability |
| GS-CHR-011 | Alias resolution and linkage record format |
| GS-OPS-002 | Key revocation — how revoked keys are marked |
| GS-REF-003 | Runtime interface — what Resileos does and does not do |
| RS-INF-001 §6 Phase C | Resileos implementation of this Protocol's export |
| RS-INF-002 | Ledger stores attestations; this Protocol defines their cross-guild format |
| `schemas/attestation.v1.json` | Normative schema for §3 |
| `examples/attestation-sample.json` | Worked example of §3 |

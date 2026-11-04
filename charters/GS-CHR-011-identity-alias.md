---
doc: GS-CHR-011
title: Identity and Alias Protocol
status: draft
category: charter
depends_on: [GS-FND-002, GS-CHR-002]
review_cycle: annual
---

# GS-CHR-011 — Identity and Alias Protocol

## 1. Purpose

Members participate under monikers. Monikers protect them from targeting, from retaliation, from disclosure of legal identity to hostile parties. This Protocol specifies how monikers are created, how they are bound to cryptographic keys, how credentials can be proven without revealing legal identity, and how linkage across guilds works.

It does not implement a central identity service. Identity is local to the member and to the guild.

## 2. Monikers

- A moniker is a lowercase slug `[a-z0-9-]+` unique within a guild.
- The fully qualified member key is `<guild_id>:<moniker>`.
- A moniker is bound to a cryptographic keypair. The public key is published; the private key is held by the member.
- Monikers are portable: a member may use the same moniker in another guild, but it refers to a different subject unless the member publishes a linkage record (§5).
- Monikers may not be reassigned. If a member exits, the moniker is retired.

## 3. Key Structure

Each member holds:

- **Identity key** — long-term, used to sign linkage records and attestations.
- **Signing key** — used to sign artifacts and merit attestations.
- **Encryption key** — used for secure communication with peers.
- **Recovery key** — held in escrow by trusted peers for key loss (GS-OPS-002).
- **Revocation key** — pre-signed revocation certificate for duress (GS-OPS-002).

## 4. Public Credentials Without Legal Identity

A member may prove competence without revealing legal identity by presenting a verifiable credential from a public issuer.

Permitted credential types:

- ORCID (academic authorship)
- DOI (published papers)
- Open-source merged contributions (via GitHub or equivalent)
- Public benchmark submissions
- Conference peer review service
- Verified course completion
- Public compute grant

**Not permitted:**

- Employer repository access
- Internal cluster access
- Proprietary telemetry
- Unpublished safety warnings
- NDA-protected model details

The goal is "prove you have a relevant public track record without exposing your legal identity." It is not "prove you work at Lab X."

## 5. Linkage Records

A member may publish a linkage record connecting two or more monikers. The record is signed by all keys being linked. Example: "moniker A in guild X and moniker B in guild Y are controlled by the same member."

Linkage is optional. No member is required to link monikers across guilds. No guild may require linkage as a condition of membership.

Linkage records are used for:

- Merit attribution across guilds (opt-in).
- Key continuity during forks (GS-CHR-008 §4.5).
- Cross-guild attestation of identity (opt-in).

## 6. Zero-Knowledge Credentialing (Proposed)

The following is specified for future implementation. Phase A of `RS-INF-001` does not implement ZKP; the `identity_provider` interface is a no-op.

The credentialing layer uses standard verifiable credentials (W3C VC, BBS+ signatures or SD-JWT). A member presents a proof that:

- They control a valid credential from an accepted issuer.
- The credential satisfies a predicate (e.g., "has a math PhD," "has five merged PRs").
- The credential is bound to their moniker public key.
- The credential has not been previously used (nullifier).

Recommended stack:

- W3C Verifiable Credentials
- BBS+ signatures or SD-JWT VC
- Circom + snarkjs or Halo2 for ZK proofs
- Semaphore-style anonymity sets for group membership
- StatusList2021 or cryptographic accumulators for revocation
- Sigstore / in-toto / SLSA for artifact provenance

The Guild does not invent cryptography. It uses audited libraries.

## 7. What Identity Does Not Solve

- **Metadata leaks.** Timing, network patterns, writing style can deanonymize.
- **Legal compulsion.** Subpoenas, key disclosure laws, platform logs still exist.
- **Small anonymity sets.** If only three people can prove a credential, the proof is weak.
- **Collusion.** Peer-review rings can game merit reputation.
- **Revocation tracking.** Issuers may be able to track presentations unless designed for unlinkability.
- **Legal exposure.** A ZKP does not make proprietary data legal to use. It does not protect against NDA violations.

Members should understand these limits before relying on pseudonymity.

## 8. Revocation and Duress

Revocation and duress handling are specified in GS-OPS-002. A member under duress can trigger a silent alert that:

- Notifies trusted peers and counsel.
- Initiates key rotation.
- Preserves the member's non-compromised assets.

The duress mechanism does not destroy data or endanger the member. It notifies.

## 9. Cross-References

| Document | Relationship |
|---|---|
| GS-FND-002 §3 | Moniker definition |
| GS-CHR-002 §11 | Merit recorded against moniker, not legal identity |
| GS-CHR-008 §4.5 | Key continuity during forks |
| GS-CHR-009 §5 | Linkage records for cross-guild recognition |
| GS-OPS-002 | Revocation, recovery, duress |
| RS-INF-001 §5 | `identity_provider` interface (no-op in Phase A) |
| RS-INF-002 | Ledger stores moniker-key bindings |

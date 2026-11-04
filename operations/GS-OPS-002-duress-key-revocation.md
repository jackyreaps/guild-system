---
doc: GS-OPS-002
title: Duress and Key Revocation Protocol
status: draft
category: operations
depends_on: [GS-CHR-011]
review_cycle: annual
---

# GS-OPS-002 — Duress and Key Revocation Protocol

## 1. Purpose

Keys can be compromised. Members can be coerced. This Protocol specifies how key revocation, recovery, and duress signaling work so that a compromised member does not compromise the network, and a coerced member can signal distress without endangering themselves.

## 2. Key Hierarchy

Per GS-CHR-011 §3:

- **Identity key** — long-term, signs linkage and attestations.
- **Signing key** — signs artifacts and merit attestations.
- **Encryption key** — secure communication.
- **Recovery key** — held in escrow by trusted peers.
- **Revocation key** — pre-signed revocation certificate.

## 3. Revocation

### 3.1 Pre-Signed Revocation

Each keypair has a pre-signed revocation certificate held by the member and by trusted peers. The certificate revokes the key when published.

### 3.2 Publication

Revocation is published to:

- The member's guild ledger (`RS-INF-002` §4 `revoke` event, Phase B).
- The public revocation log (content-addressed, mirrored).
- Peer guilds that have recognized the member's attestations.

### 3.3 Effect

Once published, the revoked key is no longer valid. Artifacts signed with the revoked key are marked "signed with revoked key" in the public record. They are not invalidated, but they are contextualized.

### 3.4 Automated Rejection

Automated systems (CI, validation pipelines) reject artifacts signed with revoked keys.

## 4. Recovery

### 4.1 Social Recovery

Recovery from key loss uses Shamir secret sharing or multi-sig quorum among trusted peers. The peer set is declared by the member in advance. Recovery requires a quorum of the peer set.

### 4.2 Time-Lock

Recovery is time-locked: there is a delay between recovery initiation and completion (e.g., 7 days). This gives the member time to cancel if the recovery is fraudulent.

### 4.3 Audit

All recovery events are logged and published (subject to member safety).

### 4.4 No Master Key

There is no central master key. There is no single point of recovery. The peer set is the recovery mechanism.

## 5. Duress

### 5.1 Duress Credential

Each member has a duress credential (a special key or passphrase). When used, it triggers a silent alert.

### 5.2 The Silent Alert

The duress alert:

- Notifies trusted peers and counsel.
- Notifies the Chamber.
- Initiates a monitoring period.

The alert does **not**:

- Destroy data.
- Endanger the member.
- Alert the coercing party.

### 5.3 Post-Duress Actions

When the Chamber receives a duress alert:

1. Verify the alert through a secondary channel if possible.
2. Assess risk.
3. Coordinate with counsel.
4. Prepare key rotation and (if needed) relocation.
5. Wait for the member to re-establish safe communication or for a clear signal to act.

The Chamber does not act unilaterally. It supports the member's own decision.

## 6. Transparency

- Revocation events are published without exposing personal data.
- A public key registry maintains revocation status.
- The registry is content-addressed and mirrored.

## 7. Testing

The duress and revocation mechanisms are tested:

- Annually, by each guild.
- On any change to the key hierarchy.
- By new members as part of onboarding.

An untested duress mechanism is not a duress mechanism.

## 8. Cross-References

| Document | Relationship |
|---|---|
| GS-CHR-011 §3 | Key hierarchy |
| GS-CHR-011 §8 | Duress handling |
| GS-CHR-006 §10 | Chamber emergency authority |
| GS-OPS-001 | First 24 hours (invoked on duress if member is detained) |
| RS-INF-002 | Ledger records revocation events |

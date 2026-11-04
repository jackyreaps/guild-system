---
doc: GS-FND-003
title: The Foundation Layer — A Reader's Map
status: draft
category: foundation
depends_on: [GS-FND-001, GS-FND-002]
review_cycle: biennial
---

# GS-FND-003 — The Foundation Layer: A Reader's Map

A short navigation document. It does not introduce new rules. Its only job is to explain how the two foundation documents — the Founding Signal and the Compact — relate to each other and to the operational layer beneath them, so a reader does not have to figure that out by reading the whole repository.

## 1. What the Foundation Layer Contains

Three documents.

**GS-FND-001 — Founding Signal & Cultural Manifesto.** The public-facing statement of what the Guild System is, why it exists, and what kind of culture it commits to. Written to be readable by someone encountering the system for the first time. Not binding. Declarative.

**GS-FND-002 — The Compact of the Guild System.** The binding document. Establishes the four Operating Articles, the four Structural Principles, the Authority Article, the minimum standards every chartered guild must meet, the document hierarchy, peer attestation, and the fork guarantee. Everything else in the repository derives its authority from this document.

**GS-FND-003 — this document.** A reader's map.

## 2. How the Two Documents Relate

The Founding Signal and the Compact overlap in subject matter but differ in function.

- The **Signal** says what the Guild System is *for*. It is declarative. It can be quoted, cited, and adopted by a guild as a statement of shared purpose.
- The **Compact** says what the Guild System *requires*. It is binding. A guild cannot adopt the Signal without the Compact and still be a chartered guild.

The Signal is not a summary of the Compact. The Compact is not a legal formalization of the Signal. They are two independent documents with overlapping scope but distinct authority.

If the Signal and the Compact contradict each other, the Compact governs (Compact §8).

## 3. The Operational Layer Underneath

The Compact establishes rules. The charters, operations, and matrices implement them. The mapping is roughly:

- **Charters (CHR)** derive their authority from the Compact and specify binding rules at the system level. They are where the Compact's abstract principles become concrete procedures.
- **Operations (OPS)** implement the charter rules at the operational level. They are the how-to layer.
- **Matrices (MTX)** map threats, risks, and decisions. They inform; they do not bind.
- **Reference (REF)** documents provide context. They are not normative.

The dependency chain is stated in `INDEX.md`.

## 4. How to Read the Repository

Different readers should start in different places.

**If you are considering founding a guild:** read GS-FND-001 (why), then GS-FND-002 §6 (minimum standards), then GS-CHR-010 (charter template). Then GS-CHR-005 (drift detection) and GS-CHR-008 (fork). These five are the adoption kit.

**If you are evaluating whether to join an existing guild:** read GS-FND-001 (culture), GS-FND-002 §3 (definitions), GS-CHR-002 (merit), GS-CHR-005 (what drift looks like), and GS-CHR-008 (your exit right).

**If you are a legal reviewer:** read GS-FND-002 §4 (Operating Articles) and §5 (Structural Principles), then GS-OPS-005 (insulation), GS-OPS-006 (resilience), and GS-CHR-006 (Chamber). The disclosure boundary is in GS-OPS-005 §6.

**If you are a technologist:** read GS-FND-002 §4 Article I (data boundary), GS-CHR-009 (interoperability), and the three Resileos documents (`RS-INF-001`, `RS-INF-002`, `RS-INF-003`) which specify the runtime.

**If you are looking for the shortest possible summary:** read GS-FND-001 §3 (commitments) and GS-FND-002 §6 (minimum standards). Those two sections capture the system's shape in a page and a half.

## 5. What the Foundation Layer Does Not Contain

- **No runtime specifications.** Those are in Resileos (`RS-INF-*`).
- **No framework claims.** Those are in QD-TER Human Medium.
- **No operational procedures.** Those are in the OPS documents.
- **No case studies or historical justifications.** The design stands on its own structure, not on lineage.

## 6. Cross-References

| Document | Relationship |
|---|---|
| GS-FND-001 | The public-facing signal this document maps |
| GS-FND-002 | The binding document this document maps |
| INDEX.md | The complete document inventory and dependency chain |
| RS-INF-001 | Runtime implementation |
| RS-INF-002 | Ledger data contract |
| RS-INF-003 | Frame profile — founding orientation and shear detection |

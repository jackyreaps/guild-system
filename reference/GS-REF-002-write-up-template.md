---
doc: GS-REF-002
title: Standard Write-Up Template
status: draft
category: reference
depends_on: [GS-FND-002]
review_cycle: annual
---

# GS-REF-002 — Standard Write-Up Template

A reference document specifying the structure every new GS-* document follows. It is not normative for existing documents; it is normative for future ones.

## 1. Purpose

Consistent structure makes the document set navigable. A reader should be able to find definitions, principles, boundaries, and cross-references in the same place in every document. This template specifies that structure.

## 2. Frontmatter

Every document begins with YAML frontmatter:

```yaml
---
doc: GS-CATEGORY-NNN
title: Document Title
status: draft
category: foundation | charter | operations | matrix | reference
depends_on: [list of GS-IDs this document depends on]
runtime_impl: [list of RS-INF-IDs, if applicable]
review_cycle: annual | biennial
---
```

Fields are required unless marked optional. `runtime_impl` is optional and appears only when the document is implemented in Resileos.

## 3. Body Sections

Every document follows this section order. Sections marked *optional* may be omitted when not applicable; all others are required.

1. **H1 Title** — matching the frontmatter title.
2. **Opening paragraph** — one paragraph stating what the document does and does not do.
3. **Purpose** — expanded statement of intent.
4. **Scope** *(optional)* — what is in scope, what is out.
5. **Definitions** — every term used in a specific way.
6. **Principles** — the rules the document enforces.
7. **Roles and Responsibilities** *(optional)* — who does what.
8. **Process or Protocol** — the operational content.
9. **Boundaries** *(optional)* — what the document does not govern, with cross-references.
10. **Legal and Compliance Boundaries** *(optional)* — legal limits.
11. **Threat Model** *(optional)* — applicable threats.
12. **Emergency Provisions** *(optional)* — emergency rules.
13. **Transparency and Reporting** *(optional)* — what is published.
14. **Fork and Exit Provisions** *(optional)* — if the document is fork-relevant.
15. **Cross-References** — table mapping to other documents.
16. **Review and Amendment** — how the document changes.

For **matrix** documents, the body is instead a single table or a small set of tables, plus a Purpose section and a Cross-References section. The other sections are omitted.

For **reference** documents, the body follows the section order but may collapse or expand sections freely, since reference documents are not binding.

## 4. Cross-References Table

Every document ends with a cross-reference table in this format:

| Document | Relationship |
|---|---|
| GS-XXX-NNN | One-line description of the relationship |

The table lists every other GS-* document this document references or is referenced by. It does not list RS-INF-* documents in the same table; those go in the frontmatter `runtime_impl` field or in a separate note.

## 5. Naming Convention

Format: `GS-CATEGORY-NNN`.

Categories:
- **FND** — Foundation
- **CHR** — Charters
- **OPS** — Operations
- **MTX** — Matrices
- **REF** — Reference

Numbers are zero-padded three-digit integers, sequential within category. Numbers are not reused. A superseded document retains its number and is marked superseded in the index.

## 6. Status Values

- **draft** — content written, not yet ratified
- **active** — ratified and in force
- **superseded** — replaced by a later document; the number is not reused

Draft documents are visible in the repository; they are not binding until ratified under the Compact's amendment process (GS-FND-002 §11) or the guild's own adoption process (GS-FND-002 §6).

## 7. Writing Conventions

- **Second person address.** Write to the reader as "you" or refer to the actor as the role ("a guild," "the Chamber"). Avoid passive voice where an active subject exists.
- **No historical justifications.** Rules stand on their own structural merit. A rule that needs a founding myth to justify it is a rule that has not been justified.
- **No meta-commentary.** Do not reference the drafting process, audit findings, or version history in the document body. Change history lives in git.
- **Cite the rule, not the decision.** When a document references another, cite the section that contains the rule. Do not cite a decision record that produced the rule.
- **Boundary statements where overlap exists.** If a document's subject overlaps another's, state the boundary explicitly at the top of the document.

## 8. Cross-References

| Document | Relationship |
|---|---|
| GS-FND-002 §8 | Document hierarchy this template serves |
| INDEX.md | The inventory this template populates |

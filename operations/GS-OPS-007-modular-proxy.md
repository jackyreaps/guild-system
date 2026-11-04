---
doc: GS-OPS-007
title: Modular Proxy Architecture — Corporate Tiering
status: draft
category: operations
depends_on: [GS-FND-002, GS-OPS-005, GS-OPS-006]
review_cycle: annual
---

# GS-OPS-007 — Modular Proxy Architecture

Specifies the corporate tiering that implements GS-OPS-005's structural insulation principles. It covers the legitimate corporate structures — foundations, holding companies, operating subsidiaries, local entities — that distribute liability and jurisdiction without concealing ownership.

This document covers **corporate tiering only**. It does not cover cryptographic routing, privacy pools, ephemeral wallet layers, or any mechanism designed to defeat lawful transaction traceability. Such mechanisms are prohibited under GS-OPS-005 §6 and GS-OPS-006 §9.

## 1. Purpose

A guild that is one legal entity is a guild that can be destroyed by one legal action. The purpose of corporate tiering is to ensure that a judgment against one entity, a seizure of one account, or a capture of one jurisdiction does not reach the guild's core reserves, IP, or membership.

This is not concealment. Beneficial ownership is available on lawful request at every layer. Tax filings are made at every layer. Third-party creditors can reach the assets of the entity that owes them. The failure mode this structure prevents is a single action destroying the whole group. It does not prevent a lawful judgment against one entity from being satisfied against that entity.

## 2. The Three-Layer Corporate Structure

```
Layer 1 — Asset Foundation
        |
        +-- Layer 2 SPV A --- Layer 3 Operating Entity 1
        |
        +-- Layer 2 SPV B --- Layer 3 Operating Entity 2
        |
        +-- Layer 2 SPV C --- Layer 3 Operating Entity 3
```

### 2.1 Layer 1 — The Asset Foundation

- **Structure.** Swiss Stiftung, Liechtenstein Anstalt, or an equivalent foundation or trust in a rule-of-law jurisdiction with strong property protections.
- **Function.** Holds core reserves, IP, and critical data infrastructure. Does not trade. Does not sign operational contracts. Does not interface with external markets.
- **Disclosure.** Beneficial ownership disclosed on lawful request. Annual filings. Not concealed.

### 2.2 Layer 2 — The Capital-Routing Layer

- **Structure.** Variable Capital Companies in Singapore, Protected Series LLCs in Delaware or Wyoming, or equivalents.
- **Function.** Segregated sub-funds or cells. Capital from Layer 1 is siloed into specific cells per project. Liabilities of one cell are statutorily firewalled from others. A compromise of Cell A cannot breach Cell B or propagate upward.
- **Disclosure.** Each cell files its own tax return. Each cell's beneficial ownership is disclosed on lawful request.

### 2.3 Layer 3 — The Contract Interface Layer

- **Structure.** Locally registered entities in the counterparty's jurisdiction — UK LTD, US Inc., European GmbH, or equivalents.
- **Function.** Handles public operations, employment, and vendor billing. Owns no core assets. Holds minimal working capital. Funded just-in-time from Layer 2.
- **Disclosure.** Standard filings. These are not disposable fronts. If they fail, they are wound down lawfully. If they are sued, they can be sued and can pay judgments up to their documented capital and any parent guarantees disclosed in their filings.

## 3. What Makes This Lawful

A corporate tier structure is lawful when all four conditions hold:

1. **Beneficial ownership is available on lawful request** at every layer.
2. **Tax compliance** is maintained at every layer.
3. **Third-party creditors can reach the assets of the entity that owes them.** A creditor of an operating company can sue that company, obtain judgment, and collect from that company's assets and any disclosed parent guarantees.
4. **The structure is disclosed.** It is not hidden. It is a documented corporate group.

The failure mode this structure prevents is a single seizure or judgment against one entity destroying the entire group. It does not prevent a lawful judgment against one entity from being satisfied against that entity.

## 4. Prohibited Structures

The following are prohibited under this document, under GS-OPS-005 §6, and under ordinary fraudulent conveyance law in every jurisdiction:

- Disposable fronts designed to absorb judgments with no intent to pay.
- Operating entities with no real balance sheet that exist only to absorb legal liability.
- Undisclosed parent guarantees that conceal the true obligor.
- Transfer of assets out of an entity to defeat a creditor — voidable preference or fraudulent transfer.
- Any structure that fails GS-OPS-005 §6.

These are not merely discouraged. They are the difference between a corporate group and a sham. A guild using sham structures has failed this document regardless of how many tiers it has.

## 5. Interplay With GS-OPS-005 and GS-OPS-006

- **GS-OPS-005** defines the structural principles — three-tier architecture, no direct sovereign exposure, disclosure boundary.
- **GS-OPS-007** — this document — specifies concrete corporate forms for those principles.
- **GS-OPS-006** defines reserve distribution across institutions, jurisdictions, currencies, and legal forms.

A guild's structure is compliant when it satisfies all three. A structure that satisfies GS-OPS-005 and GS-OPS-006 but uses sham entities fails this document.

## 6. Cross-References

| Document | Relationship |
|---|---|
| GS-OPS-005 | Structural principles |
| GS-OPS-006 | Reserve distribution |
| GS-OPS-004 | Compute and treasury compliance |
| GS-MTX-010 | Counterparty insulation matrix |

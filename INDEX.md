# Master Index — Guild System Documents

All documents are in **draft** status pending ratification. Draft indicates content is written and published; it does not indicate the document is in force. Only GS-FND-002 (the Compact) binds, and it binds provisionally until ratified by chartered guilds.

The authoritative document hierarchy is stated in Compact §8: FND > CHR > OPS > MTX > REF.

## Foundation (FND)

| ID | Title | Status | File |
|---|---|---|---|
| GS-FND-001 | Founding Signal & Cultural Manifesto | Draft | `foundation/GS-FND-001-founding-signal.md` |
| GS-FND-002 | The Compact of the Guild System | Draft — binding pending ratification | `foundation/GS-FND-002-compact.md` |
| GS-FND-003 | The Foundation Layer: A Reader's Map | Draft | `foundation/GS-FND-003-foundation-layer.md` |

## Charters (CHR)

| ID | Title | Status | File |
|---|---|---|---|
| GS-CHR-001 | Hostile-State Resilience Charter | Draft | `charters/GS-CHR-001-hostile-state-resilience.md` |
| GS-CHR-002 | Merit Protocol & Commensuration Rules | Draft | `charters/GS-CHR-002-merit-protocol.md` |
| GS-CHR-003 | Currency and Exchange Annex | Draft | `charters/GS-CHR-003-currency-annex.md` |
| GS-CHR-004 | Civic Substitution & Mutual Provision | Draft | `charters/GS-CHR-004-civic-substitution.md` |
| GS-CHR-005 | Branch Guardrails & Drift Prevention | Draft | `charters/GS-CHR-005-branch-guardrails.md` |
| GS-CHR-006 | Juridical Chamber Charter | Draft | `charters/GS-CHR-006-juridical-chamber.md` |
| GS-CHR-007 | Cross-Guild Dispute Resolution | Draft | `charters/GS-CHR-007-dispute-resolution.md` |
| GS-CHR-008 | Fork and Secession Protocol | Draft | `charters/GS-CHR-008-fork-secession.md` |
| GS-CHR-009 | Interoperability Protocol | Draft | `charters/GS-CHR-009-interoperability.md` |
| GS-CHR-010 | Local Guild Charter Template | Draft | `charters/GS-CHR-010-local-charter-template.md` |
| GS-CHR-011 | Identity and Alias Protocol | Draft | `charters/GS-CHR-011-identity-alias.md` |

## Operations (OPS)

| ID | Title | Status | File |
|---|---|---|---|
| GS-OPS-001 | First 24 Hours Emergency Protocol | Draft | `operations/GS-OPS-001-first-24-hours.md` |
| GS-OPS-002 | Duress and Key Revocation Protocol | Draft | `operations/GS-OPS-002-duress-key-revocation.md` |
| GS-OPS-003 | Distribution and Mirroring Protocol | Draft | `operations/GS-OPS-003-distribution-mirroring.md` |
| GS-OPS-004 | Compute and Treasury Compliance Annex | Draft | `operations/GS-OPS-004-compute-treasury.md` |
| GS-OPS-005 | Structural Insulation Protocol | Draft | `operations/GS-OPS-005-structural-insulation.md` |
| GS-OPS-006 | Financial Resilience and Distribution | Draft | `operations/GS-OPS-006-financial-resilience.md` |
| GS-OPS-007 | Modular Proxy Architecture (Corporate Tiering) | Draft | `operations/GS-OPS-007-modular-proxy.md` |

## Matrices (MTX)

| ID | Title | Status | File |
|---|---|---|---|
| GS-MTX-001 | Adversarial Legality Matrix | Draft | `matrices/GS-MTX-001-adversarial-legality.md` |
| GS-MTX-002 | Jurisdictional Compliance Matrix | Draft | `matrices/GS-MTX-002-jurisdictional-compliance.md` |
| GS-MTX-003 | Merit Anti-Gaming Matrix | Draft | `matrices/GS-MTX-003-merit-anti-gaming.md` |
| GS-MTX-004 | Merit Commensuration Matrix | Draft | `matrices/GS-MTX-004-merit-commensuration.md` |
| GS-MTX-005 | Guild Credit Exposure Matrix | Draft | `matrices/GS-MTX-005-credit-exposure.md` |
| GS-MTX-006 | Civic Substitution Matrix | Draft | `matrices/GS-MTX-006-civic-substitution.md` |
| GS-MTX-007 | Drift Matrix | Draft | `matrices/GS-MTX-007-drift.md` |
| GS-MTX-008 | Idea Protection Matrix | Draft | `matrices/GS-MTX-008-idea-protection.md` |
| GS-MTX-009 | Learning and Contribution Incentive Matrix | Draft | `matrices/GS-MTX-009-learning-incentive.md` |
| GS-MTX-010 | Counterparty Insulation Matrix | Draft | `matrices/GS-MTX-010-counterparty-insulation.md` |

## Reference (REF)

| ID | Title | Status | File |
|---|---|---|---|
| GS-REF-001 | Threat Pattern Analysis | Draft | `reference/GS-REF-001-threat-analysis.md` |
| GS-REF-002 | Standard Write-Up Template | Draft | `reference/GS-REF-002-write-up-template.md` |

## External programs of record (not copied into this repo)

| ID | Title | Location |
|---|---|---|
| RS-INF-001 | Guild Infrastructure Program | `Resileos-QAI/docs/320-titanos/guild-infra-program.md` |
| RS-INF-002 | Guild Ledger Schema | `Resileos-QAI/docs/320-titanos/ledger-schema.md` |
| RS-INF-003 | Guild Frame Profile | `Resileos-QAI/docs/320-titanos/frame-profile.md` |

## Dependency chain

```
GS-FND-002 Compact
  → GS-CHR-002, GS-CHR-003, GS-CHR-004, GS-CHR-005, GS-CHR-006
    → GS-OPS-001, GS-OPS-002, GS-OPS-005, GS-OPS-006, GS-OPS-007
      → GS-CHR-007, GS-CHR-008, GS-CHR-009, GS-CHR-010
        → Resileos Phase A, Phase B, Phase C
```

**Phase C of Resileos is blocked on GS-CHR-009.** It is now drafted; Phase C can proceed once it is ratified by guilds in good standing.

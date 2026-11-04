---
doc: GS-OPS-009
title: Emergency Liquidity and Mutual Credit Protocol
status: draft
category: operations
depends_on: [GS-FND-002, GS-CHR-003, GS-OPS-008]
review_cycle: annual
---

# GS-OPS-009 — Emergency Liquidity and Mutual Credit Protocol

Specifies how members and guilds obtain liquidity in emergencies and opportunities without converting Guild Credits to external value (Compact Article II), without triggering below-market-loan imputation rules, and without creating a taxable event where the law provides a non-taxable alternative.

The protocol has three mechanisms. They are not interchangeable. Each has a different tax profile, a different legal character, and a different compliance surface. Choosing the wrong mechanism for a given need is how mutual aid gets characterized as either tax evasion or unlicensed lending.

## 1. Purpose

A member facing a legal emergency needs cash for counsel in a jurisdiction that does not accept Guild Credits. A guild facing an opportunity needs fiat to secure compute before a window closes. A member between contributions needs bridge support while their next artifact is being verified.

Each of these is a legitimate need. None of them is well-served by a zero-interest fiat loan from the guild to the member, because:

- Below-market loans trigger imputation rules under IRC §7872 (US) and equivalent regimes in other jurisdictions.
- The imputed interest is treated as taxable to the lender and may create taxable income or expense for the borrower.
- The Tax Court's contrary position in some demand-loan cases is not a foundation that holds across jurisdictions.
- A structure that depends on winning a tax argument in court is a litigation strategy, not a compliance strategy.

The three mechanisms below avoid the imputation problem by not being below-market loans.

## 2. Mechanism 1 — Mutual Credit Facility

### 2.1 What it is

A set of member-to-member credit lines cleared through the guild's ledger, denominated in internal credits, extinguished by future contribution rather than by interest-bearing repayment. This is the primary emergency mechanism.

It is not a loan from the guild to the member. It is a set of mutual obligations among members, with the guild acting as clearinghouse.

### 2.2 Why it has favorable tax treatment

Mutual credit and time-bank exchanges are treated more favorably than ordinary lending in most jurisdictions because:

- **No external principal is advanced.** The unit is created within the network, not borrowed from a bank.
- **No interest accrues.** Credit is extinguished by service, not repaid with a premium.
- **Exchange is equal-value.** One credit for one credit of the same class.
- **Mutual or charitable character.** The facility is operated by the guild, not by a for-profit lender.

The IRS has issued informal guidance and private rulings treating hour-for-hour time bank exchanges as non-taxable where the value is equal and the organization is charitable or mutual in character. Several other jurisdictions treat mutual credit organizations similarly, though the specific rules vary.

### 2.3 How it works

1. A member in need requests credits from the mutual credit pool.
2. The pool extends credits based on the member's verified contribution history and the guild's published lending policy.
3. The member uses the credits for internal goods — compute, tools, courses, or for exchange through the guild's treasury (Mechanism 3).
4. The member extinguishes the obligation by future verified contribution, at a schedule set in the loan terms.
5. No interest is charged. No fiat principal was advanced. No imputation applies.

### 2.4 Limits

- **Mutual credit only.** The pool holds internal credits, not fiat. A member who needs fiat goes through Mechanism 3.
- **Per-member cap.** The guild sets a maximum credit extension per member, declared in its Local Guild Charter.
- **Verification required.** Extension requires verification of contribution history. A new member with no history is not eligible for the maximum extension.
- **Transparency.** Aggregate mutual credit activity is reported in the guild's annual transparency report. Individual balances are visible only to the member and to the guild's internal governance.

## 3. Mechanism 2 — Advance Against Future Contribution

### 3.1 What it is

An emergency issuance of credits to a member as a prepayment for future verified contribution. It is not a loan. It is an advance.

The distinction matters:

- A **loan** creates a debt obligation with a principal amount, a repayment schedule, and (if below market) imputed interest.
- An **advance against contribution** creates a right to future work. The member "repays" by completing work that the guild would have awarded merit and credits for anyway. There is no principal, no interest, and no forgiveness event.

### 3.2 Why it has favorable tax treatment

An advance against future services is closer to a prepayment than a loan. It does not trigger §7872 because there is no loan. If the member never performs, the advance may be treated as compensation at that point — but that is a contingent event, not a feature of the structure.

### 3.3 How it works

1. A member identifies a need (emergency, opportunity, bridge support).
2. The guild's internal governance authorizes an advance against specified future contribution — for example, "advance of X credits against completion of the next reproducibility audit."
3. The advance is recorded in the ledger as an `advance_issued` event.
4. When the member completes the specified contribution, the advance is recorded as settled with a `advance_settled` event. The member receives the merit for the contribution; the credits were already advanced.
5. If the contribution is not completed within the declared window, the guild's governance decides how to handle the shortfall — roll over, convert to mutual credit, or record as compensation.

### 3.4 Limits

- **Specified contribution required.** The advance must name what future work it is against. A general cash advance with no specified contribution is a loan in substance, not an advance.
- **Governance approval.** Advances above a threshold set in the Local Guild Charter require the guild's internal governance process.
- **Transparency.** Aggregate advance activity is reported annually.

## 4. Mechanism 3 — Regulated Fiat Bridge

### 4.1 What it is

For situations where actual currency is needed — a member facing a legal emergency that requires payment in fiat, a guild needing to pay counsel in a jurisdiction that does not accept credits, a vendor requiring immediate fiat payment — the guild does not lend fiat at zero interest. It uses a regulated bridge.

### 4.2 How it works

1. **The guild holds a line of credit with a regulated bank or licensed lender at a market rate.**
2. **The guild on-lends to the member at the same rate.** This is a pass-through. There is no below-market element and no imputation.
3. **The member repays in credits or in service**, and the guild services the bank debt from its treasury.
4. **The interest is real.** It is paid to a regulated counterparty. It is either deductible or capitalized according to the member's use of funds.
5. **Documentation.** The pass-through is documented per GS-OPS-004 §3 and disclosed in aggregate in the guild's transparency report.

### 4.3 Why not zero-interest

Zero-interest fiat lending by the guild to the member triggers §7872 imputation in the US and equivalent rules elsewhere. The guild would have imputed interest income; the member would have imputed interest expense that may or may not be deductible. The Tax Court's contrary position in some demand-loan cases is not a foundation that survives across jurisdictions, and the anti-avoidance provisions of §7872 apply where a principal purpose of the loan arrangement is tax avoidance.

The regulated pass-through avoids this entirely. The interest is real, it is paid at market rate, and it is documented.

### 4.4 Limits

- **Regulated counterparty only.** The bank or lender must be a licensed institution in a jurisdiction where the guild or member operates.
- **Market rate.** The pass-through rate equals the underlying rate. The guild does not subsidize the rate.
- **Tax documentation.** The member receives documentation of the interest paid, for their own tax purposes.
- **No concealment.** The pass-through is disclosed to lawful authorities on request under GS-OPS-005 §6.

## 5. What the Guild Does Not Do

None of the following are permitted, regardless of how they are characterized:

- **Zero-interest fiat lending from the guild to a member.** This is the structure that triggers imputation, and it is what the three mechanisms above are designed to avoid.
- **Fiat loans from the mutual credit pool.** The pool holds internal credits, not fiat.
- **Advances without a specified future contribution.** A general cash advance is a loan in substance.
- **Pass-through facilities at above-market rates.** The pass-through is a pass-through, not a profit center.
- **Conversion of Guild Credits to fiat.** Article II stands. The regulated bridge is a loan, not a conversion.
- **Any structure that fails GS-OPS-005 §6 (disclosure boundary).**

## 6. Private Arrangements Between Members

The Guild System governs what happens on its ledger and through its structures. It does not govern the private lives of its members.

If members make arrangements between themselves outside the guild's structures — whether along the lines of the mechanisms described in this Protocol, or otherwise — the guild does not review, endorse, or condemn those arrangements. Members are adults, responsible for their own conduct and their own legal compliance in their own jurisdictions.

This is not indifference. It is the limit of the guild's jurisdiction. A guild that tried to police every private transaction between its members would be overreaching in exactly the way the Compact warns against. A guild that claimed to shelter conduct it did not structure and could not control would be creating risk for everyone.

The guild's protection extends to guild work performed under guild structures. The Defense Fund, the Juridical Chamber, and the Counsel Network cover members facing retaliation for guild work — not private arrangements outside those structures. A member who acts alone acts alone.

The guild's public position on mutual aid is stated in §7. It makes that position as advocacy, not as cover.

## 7. The Moral Position, Stated Publicly

The Guild System holds that mutual aid between people helping each other is not the kind of transaction the tax code was designed to reach. Most jurisdictions already recognize this in fragments — gift exclusions, de minimis thresholds, favorable treatment for time banks and mutual credit, tax-exempt status for mutual aid organizations.

The protocol above is designed to build inside those recognized categories, not outside them. It does not depend on a court victory or an aggressive interpretation. It depends on the categories the law already provides.

A guild that argues with the tax code cannot protect its members. A guild that builds inside the recognized exclusions can. The moral claim — that mutual aid should not be taxed — is one the Guild System makes publicly. It does not make it by structuring a loan the code treats as taxable and calling it something else.

## 8. Cross-References

| Document | Relationship |
|---|---|
| GS-FND-002 Art. II | Credits non-convertibility — unchanged |
| GS-FND-002 Art. III | Tax-Integrity Floor |
| GS-CHR-003 §6 | Permitted and prohibited structures |
| GS-CHR-005 §2.2, §2.6 | Accumulation and Entanglement Drift |
| GS-OPS-004 | Compute and treasury compliance |
| GS-OPS-005 §6 | Disclosure boundary |
| GS-OPS-008 §5.2 | Borrowing — distinguishes guild as borrower from guild as lender |
| GS-MTX-005 | Credit exposure — confirms credits remain internal |
| RS-INF-002 | Ledger records `advance_issued` and `advance_settled` events |

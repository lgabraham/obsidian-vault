---
title: Annual Allocation Review — System Design
vault: g finance
created: 2026-06-14
status: design / not yet built
tags:
  - finance
  - system-design
  - allocation
  - investments
  - net-worth
---

# Annual Allocation Review — System Design

> [!abstract] Purpose
> A **yearly** review of our **overall allocation** across every investment, retirement, education, and alt account. The complement to the monthly [[Financial Model — System Design|financial model]]: that one runs *cash flow*, this one runs the *balance sheet*.

> [!important] How the two systems relate
> | | Monthly model | Annual allocation review |
> |---|---|---|
> | **Lens** | Income statement (flow) | Balance sheet (stock) |
> | **Question** | "Did we spend to plan? Is cash OK?" | "What do we own, how is it mixed, is it positioned right?" |
> | **Cadence** | Monthly | Yearly (+ a mid-year light check) |
> | **The bridge** | Savings *swept* to investing… | …becomes the *inflow* that reshapes allocation |

---

## Core principles

- **One net-worth roll-up.** Every account rolls into a single balance sheet, classified along several dimensions at once.
- **Primary residence is tracked, not allocated.** Home equity sits on the net-worth statement but is excluded from the *investable* allocation targets (you live in it; it's not a rebalancing lever).
- **Targets with drift bands, not point estimates.** Rebalance on *bands* (e.g. ±5 pts), not vibes — turns a judgment call into a rule.
- **Decide once a year, monitor lightly in between.** Strategy is annual; the monthly system already watches cash.

---

## Foundation: account inventory + holdings + classification

Three shared assets:

1. **Account inventory** — every account, its custodian, and its **tax wrapper**: taxable brokerage, Roth, Traditional/Rollover IRA, 529, HSA. See [[Account Inventory]].
2. **Holdings ledger** — each position: ticker/name, value, account, asset class. Snapshotted once a year (date-stamped) so you build a history.
3. **Classification dimensions** — every holding is tagged on all of these simultaneously:

> [!example] The four lenses every holding is tagged on
> - **Asset class** — US large / US small-value / international / bonds / real estate / crypto / private-alt / cash
> - **Tax wrapper** — taxable · Roth · traditional (pre-tax) · 529 · HSA
> - **Liquidity tier** — liquid · semi (penalty/locked: IRA, 529) · illiquid (startups, home)
> - **Risk tier** — core diversified · concentrated single-name · high-risk alt

---

## Review modules

### 1 · Net-worth roll-up
Total across all buckets, year-over-year. Split **investable net worth** (drives allocation) from **total net worth** (includes home equity). Track the YoY change and decompose it into *contributions* vs *market growth*.

### 2 · Allocation — target vs actual
The core module. Actual % vs target % by asset class, with **drift bands** and a rebalance flag when any class breaches.

> [!note] Things this view should surface for *our* current mix
> - **International equity = 0%.** Portfolio is 100% US — flag as a deliberate choice, not a default.
> - **Bonds ≈ 15% (VGIT).** Confirm that's the intended ballast given age + runway.
> - **Crypto + startups + TEF ≈ $410k of high-risk alt.** Track as a % of investable and set a *ceiling*.
> - **Single-name exposure (individual names ≈ $78k).** Cap as a % so it doesn't quietly grow.

### 3 · Asset location (tax efficiency)
*Same* allocation, but checked for **which wrapper holds what.** The rules of thumb:

- **Bonds / tax-inefficient income** → tax-deferred (traditional IRA).
- **Highest-expected-growth** → Roth (tax-free growth) and 529 (tax-free if used for school).
- **Tax-efficient index equity** → taxable (low turnover, qualified dividends, step-up basis).
- **Flag:** startups held *inside* an IRA (UBIT / valuation / liquidity complexity worth an annual look).

### 4 · Concentration & risk
Single-name %, crypto %, sector/employer overlap, and **home as a % of total net worth.** Each gets a ceiling; breaches become an action item.

### 5 · Goal sleeves
Allocation isn't just one pool — it's goal-funded sleeves, each reviewed against its target:

- **Education (529s)** — balance vs projected tuition runway; on-track / over / under. → [[Education Funding Plan]]
- **Retirement** — pre-tax + Roth balances vs a target retirement number.
- **FI / runway** — ties directly to [[Asset Base & Runway]] (liquid pool ÷ burn).

### 6 · Annual action checklist
The review *produces decisions*, not just charts:

- [ ] Rebalance any class outside its band
- [ ] Max contributions: Roth (or backdoor), HSA, 529, IRA
- [ ] Roth conversion opportunity? (esp. low-income years)
- [ ] Tax-loss harvesting sweep
- [ ] Trim concentrated / single-name positions to ceiling
- [ ] Beneficiaries + estate docs current
- [ ] Cash earmarks reconciled with [[Cash Dashboard]]

### 7 · Performance vs benchmark
Each sleeve vs a simple blended benchmark — sanity check, not a trading trigger. Guards against the individual-names / active sleeves quietly underperforming the index.

---

## The annual ritual (cadence)

> [!example] Once a year (+ a light mid-year drift check)
> 1. Snapshot every account → holdings ledger (date-stamped)
> 2. Roll up net worth; decompose contributions vs growth
> 3. Run allocation, location, concentration, and goal modules
> 4. Generate the **action checklist** with specific dollar moves
> 5. Execute rebalances / contributions / conversions
> 6. Archive the snapshot so next year has a comparison

A mid-year check is just module 2 (drift) — fast, no full rebuild.

---

## Inputs needed to build

- [ ] [[Account Inventory]] — every account, custodian, wrapper, login/where-statements-live
- [ ] One holdings export or statement per account (or a manual holdings list)
- [ ] **Target allocation** by asset class + drift band widths
- [ ] **Ceilings** for single-name, crypto, and alt exposure
- [ ] Projected tuition schedule for the education sleeve

---

## Open design decisions

- [ ] **Home equity** — included in a "total net worth" view only, excluded from investable targets? *(recommended)*
- [ ] **Rebalance trigger** — calendar (once a year) vs band-based (±X pts), or both
- [ ] **Alt ceiling** — what max % of investable for crypto + startups combined
- [ ] **International** — adopt a target intl weight, or stay deliberately US-only
- [ ] **Where it lives** — same workbook as the monthly model (new tabs) vs a standalone allocation sheet

---

## Companion notes

- [[Financial Model — System Design]] ← the monthly counterpart
- [[Account Inventory]]
- [[Asset Base & Runway]]
- [[Education Funding Plan]]
- [[Cash Dashboard]]
- [[Target Allocation 2026]]

---
*Drafted with Claude · 2026-06-14*

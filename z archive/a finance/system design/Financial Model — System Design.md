---
title: Financial Model — System Design
vault: g finance
created: 2026-06-14
status: design / not yet built
tags:
  - finance
  - system-design
  - budget
  - cash-management
---

# Financial Model — System Design

> [!abstract] Purpose
> A **living financial model** for our household, updated monthly. Three components on a shared foundation:
> 1. A **yearly budget** with category targets
> 2. A **monthly review** of actual spend (inputs: credit-card transactions via email + bank statements as PDFs)
> 3. An **active cash-management** review (liquidity, earmarks, forecasting)

---

## Core principles

- **One source of truth.** Every transaction from every source lands in a single ledger. The three components are just different *views* of that ledger.
- **Lock the taxonomy first.** If "what counts as Fun vs Health" drifts month to month, nothing downstream is comparable.
- **Repeatable inputs, fixed cadence.** The monthly update should be paste-and-go, not a re-design each time.
- **Separate the signal from the noise.** One-offs (a birthday, a big trip) get tagged separately so the trend line stays clean.

---

## Foundation: taxonomy + rolling ledger

Two shared assets everything else sits on:

- **Locked category taxonomy** — the buckets: `Savings`, `Health`, `Home`, `Transportation`, `Fun`, `Kids`, plus their sub-lines. See [[Category Taxonomy]].
- **Rolling transaction ledger** — every transaction, one row, categorized, appended each month. This is the spine.

> [!important] The two input sources are complementary, not redundant
> - **Credit cards** capture *variable / discretionary* life — food, fun, shopping.
> - **Bank statements** capture *fixed costs* (mortgage, ACH utilities, property tax, insurance), *income*, and *savings transfers* — most of which never touch a card.
> - **The bridge:** the "payment to credit card" line on the bank statement is an **internal transfer** — exclude it, or it double-counts against the card purchases it pays for.

---

## Layer 1 — Yearly Budget (the plan)

Annual target per category → divided into monthly targets. Split **every** category by *behavior*, because they review differently:

| Behavior | Examples | How it's reviewed |
|---|---|---|
| **Fixed** | Mortgage, property tax, insurance, tuition | Confirm it fired; target = actual |
| **Variable** | Restaurants, groceries, shopping, self-care | The real budget — can over/under |
| **Sinking fund** | Property tax, travel, arborist, est. taxes, one-off events | Accrue 1/12 each month |

> [!tip] Sinking funds are the piece most budgets miss
> Lumpy annual costs get a **monthly accrual** (set aside 1/12) so a $20k tax bill or a big trip doesn't blow up a single month's review. This is exactly what distorted Feb/Mar this year.

**Output:** a target row per category (monthly + annual), with seasonality flags on the lumpy lines.

---

## Layer 2 — Monthly Review (actuals vs plan)

A scheduled monthly ritual: **ingest → categorize → reconcile → compare → flag.**

1. **Ingest**
   - Card CSVs arrive in a dedicated Gmail label (forward / auto-filter).
   - Bank PDFs land in one watched folder (Drive / Box / local).
2. **Categorize** — each transaction maps to the taxonomy via a **living rules file** (merchant → category). See [[Merchant Rules]].
   - The compounding asset: every correction becomes a rule, so categorization gets more automatic each month.
   - Handles known edge cases: Toast/Square aren't merchants; refunds net against spend; card-payment transfers excluded.
3. **Reconcile** — dedupe across sources, drop internal transfers, surface anything uncategorized.
4. **Compare & flag** — actuals vs targets → variance report. Overspends, one-offs tagged separately, trends vs trailing average.

**Output:** a one-page [[Monthly Review Template|monthly review]] + an append to the historical ledger.

> [!note] Labor split
> I (Claude) do the parsing and first-pass categorization. You spend ~15 min approving and correcting the handful I'm unsure about. Corrections feed back into the rules.

---

## Layer 3 — Cash Management (liquidity, not categories)

A different question from "did we hit budget" → **"is the right cash in the right place at the right time?"** Tracks balances, earmarks, and timing.

- **Position** — cash across checking / HYSA / M Cash, with **earmarks** carved out (e.g. Paris/2026 $180k is committed, not free cash).
- **Forecast** — a rolling **3–6 month cash-flow projection** so crunches show up before they hit (e.g. the month property tax + tuition land together).
- **Sweep logic:**
  - Cash **above** (operating buffer + earmarks + near-term sinking-fund needs) → excess → candidate to invest.
  - Cash **below** buffer → flag to replenish.
- **Connection to Layer 1:** the accumulated sinking-fund accruals *are* the earmarked cash targets here.

---

## How it runs (automation)

> [!example] Monthly scheduled task
> 1. Pull card emails + bank PDFs
> 2. Parse, categorize (via rules), reconcile
> 3. Update ledger, refresh budget-variance view + cash dashboard
> 4. Send a summary flagging **only** what needs a decision: uncategorized items, overspends, upcoming cash needs
>
> You review, correct, done. Off-cycle alerts fire for big upcoming outflows.

---

## Open design decisions

- [ ] **Source of truth** — Google Sheets (live, collaborative) · Excel (richer formulas) · auto-refreshing dashboard. *Leaning Sheets.*
- [ ] **File plumbing** — how card CSVs reach a Gmail label; where bank PDFs get saved.
- [ ] **Automation vs. control** — full auto-categorization with after-the-fact review, vs. approving each month before commit.

---

## What's needed to build

- [ ] Locked [[Category Taxonomy]]
- [ ] One example of each input (a card CSV ✅ seen · a bank PDF ⬜ needed)
- [ ] Account list for the cash layer (checking, HYSA, M Cash, earmarks)

---

## Companion notes (to create)

- [[Category Taxonomy]]
- [[Merchant Rules]]
- [[Monthly Review Template]]
- [[Yearly Budget 2026]]
- [[Cash Dashboard]]
- [[Asset Base & Runway]]

---
*Drafted with Claude · 2026-06-14*

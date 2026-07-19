---
title: Deployment Dashboard — System Design
vault: g finance
created: 2026-06-14
status: design / not yet built
tags:
  - finance
  - system-design
  - deployment
  - investments
  - cash-management
---

# Deployment Dashboard — System Design

> [!abstract] Purpose
> Deploy ~**$1M of surplus cash** into the market **incrementally and by rule** — guiding *when* to invest (against a volatility/drawdown framework) and *where* each tranche goes (against [[Target Allocation 2026|allocation targets]], tilted by current price). Tracks progress over time so the decision is "follow the rule," not "is today the day?"

> [!warning] Framing — and not financial advice
> Investing the full sum at once (**lump-sum / LSI**) beats phasing-in ~2/3 of the time, because markets rise more often than not. This framework **knowingly trades a little expected return for two things you value**: downside capture (buying *more* when prices fall) and behavioral durability (a rule you'll actually stick to). The **time backstop** is what keeps the cost of waiting small. All parameters below are *yours to set* — they're illustrative starting defaults, not a recommendation.

---

## Core principles

- **Rules replace timing.** The dashboard answers "deploy $X to Y today?" with a yes/no from pre-set triggers — no daily discretion.
- **Deploy faster into fear, never slower into greed.** Calm markets → slow baseline. Drawdowns/spikes → accelerate.
- **A hard backstop.** All cash is invested within a fixed window no matter what, so it can't sit in cash indefinitely (DCA's real cost).
- **Every tranche fixes drift.** Route new money to the *most underweight* sleeve, so the $1M also rebalances the existing portfolio toward target.
- **No discretion creep.** The whole point is to follow it. Changes are made to the *parameters* between reviews, not to individual buys in the moment.

---

## Component 1 — The deployable pool

Define what's actually in play, separate from everything that isn't:

- **Deployable surplus:** ~$1.0M
- **Excluded (do not deploy):** operating cash buffer, the Paris/2026 earmark, near-term [[Financial Model — System Design|sinking-fund]] balances.

Split the $1M into **tranches** (e.g. **20 × $50k**) — the unit of deployment.

---

## Component 2 — WHEN to deploy (the trigger engine)

Two engines run in parallel; **the time floor always runs**, accelerators pull tranches forward.

### A · Time floor (the backstop)
Deploy a minimum amount on the 1st of each month regardless of market, sized so the whole sum is in within the backstop window.

> [!example] Starting default
> Backstop window = **12 months** → time floor ≈ **$80k/month** (~1.6 tranches). Shorter window = closer to lump-sum; longer = more averaging.

### B · Accelerators (deploy extra into stress)
Extra tranches when the market sells off. Two candidate signals — **drawdown is the cleaner primary** (it's what actually creates cheaper entry; VIX can spike on fear without lower prices), VIX as a secondary confirm.

| Drawdown from S&P ATH | Extra this event | VIX level | Extra this event |
|---|---|---|---|
| −5% | +1 tranche ($50k) | > 25 | +1 tranche |
| −10% | +2 tranches | > 32 | +2 tranches |
| −15% | +3 tranches | > 40 | +3 tranches |
| −20% | +4 tranches | | |

> [!note] Rules that keep it sane
> - **Take the *max* of the two accelerator signals**, don't sum them (avoids double-counting one panic).
> - **Cooldown:** each tier fires once per leg down — it re-arms only after price recovers above it or breaks a deeper tier.
> - **Monthly cap** (e.g. **$250k**): even a crash deploys over a few months, so if it keeps falling you've still got dry powder.
> - **Pull-forward, not additive:** accelerated buys draw from the remaining schedule, keeping the end date fixed (vs. finishing early and being fully exposed sooner). *(This is a design fork — see below.)*

---

## Component 3 — WHERE each tranche goes (allocation- + price-aware)

Each deployment routes to **close the biggest gap to your target end-state**, not just mirror the current mix.

1. **Compute the end-state.** Target $ per sleeve = (current portfolio **+ $1M**) × target %. This treats the $1M as the chance to fix existing drift.
2. **Gap = end-state target − current holding.** Route the tranche to the **largest positive gap(s)**, filling biggest-first (or proportionally across the top gaps).
3. **Price overlay (secondary tilt):** among comparable sleeves, bias toward whatever is **furthest below its own 200-day average** (or a valuation z-score). A *tilt*, not an override — avoids value traps.

> [!tip] The $1M is your rebalancing lever
> Deploying new cash fills underweights without selling anything (no taxable gains). This is the ideal moment to add the **missing international sleeve** and bring **bonds** to target — see [[Annual Allocation Review — System Design]].

---

## Component 4 — The dashboard (what it tracks)

| View | Shows |
|---|---|
| **Progress** | % deployed, $ remaining, tranches fired, projected finish date |
| **Trigger log** | Every event: date · trigger (time floor / VIX>32 / −10% DD) · amount · routed-to · price level |
| **Live signals** | Today's VIX, drawdown from ATH, which tiers are *armed*, next scheduled time-tranche |
| **Allocation drift** | Current vs target by sleeve → drives the routing recommendation |
| **Next action** | "Deploy $X → [most-underweight sleeve]" or "No action; next floor tranche [date]" |
| **Scorecard** | Phased approach vs hypothetical lump-sum *and* vs staying in cash — honest cost/benefit |

---

## Component 5 — Parameters you set once

- [ ] Total deployable + tranche size
- [ ] Backstop window (12 / 18 / 24 mo)
- [ ] Drawdown tiers + VIX tiers + tranche multipliers
- [ ] Monthly cap
- [ ] Pull-forward vs additive
- [ ] Target end-state allocation (from [[Target Allocation 2026]])
- [ ] Price-overlay method (200-DMA / z-score / off)

---

## Cadence & automation

> [!example] How it runs
> - **Weekly (and on stress days):** check VIX + drawdown vs armed tiers → output a deploy/no-deploy call with amount + destination.
> - **Off-cycle alert:** a tier breach pings immediately ("S&P −10% — deploy $100k, route to …").
> - **Monthly:** reconcile what was actually bought, update progress + drift, refresh the scorecard.
> - **On completion:** archive the trigger log; fold the new holdings into the [[Annual Allocation Review — System Design|annual review]].

---

## Open design decisions

- [ ] **Primary trigger** — drawdown-from-ATH *(recommended)*, VIX, or both with max-of logic
- [ ] **Backstop window** — 12 vs 18 vs 24 months (the dial between lump-sum and slow DCA)
- [ ] **Accelerated buys** — pull-forward (fixed end date) vs additive (finish early in crashes)
- [ ] **Monthly cap** size
- [ ] **End-state target** — correct the gaps (add intl, fix bonds) vs mirror current mix
- [ ] **Price overlay** — on (which method) or off for simplicity

---

## Next step

Once the parameters above are set, write the **operational instructions / runbook** (the scheduled-task prompt that checks signals and tells me what to deploy) — to live alongside this note. → [[Deployment Runbook]]

---

## Companion notes

- [[Financial Model — System Design]]
- [[Annual Allocation Review — System Design]]
- [[Target Allocation 2026]]
- [[Asset Base & Runway]]
- [[Deployment Runbook]]

---
*Drafted with Claude · 2026-06-14*

# Technical — Connect Guide

_Technical-aptitude interview (likely [[Interviewers|Nick Rhemus]]). The job: prove I genuinely understand **Connect** — and explain it so both technical and non-technical people get it._

> [!warning] The lesson from last time
> Last round I answered "what is Stripe?" so well the interviewer said it was the best he'd heard — **then got overconfident on Connect, went too deep, and got lost.** The failure mode isn't *too little* knowledge, it's *too much, unstructured.* This guide is built in tiers with a **hard stop** so that can't happen again.

## How to run this interview

1. Give the **tiered answer** below: Tier 0 → Tier 1, then **stop.**
2. **Hand it back:** *"That's the core — want me to go a level deeper on any piece?"*
3. Only go to **Tier 2** on the *specific* thing they ask about. Don't volunteer all of it.
4. If you feel yourself reaching for a metaphor mid-sentence, you're already too deep — finish the sentence and stop.

---

## Tier 0 — What is Stripe (≈15s, the proven winner)
> **Stripe is economic infrastructure for the internet** — the financial plumbing that lets any business move money online without becoming a bank or a regulated entity.

Keep it to that. It worked last time; don't add to it.

## Tier 1 — What is Connect (≈60–90s, the core — then STOP)
> **Connect lets a platform facilitate payments between *other* parties** — its own buyers and sellers — instead of just taking payments for itself. Think a marketplace or SaaS platform where money needs to flow to many third-party merchants.
>
> The core innovation: to move money on behalf of third parties, you normally need **money-transmission licenses** and a regulated entity. **Stripe holds the licenses**, so a platform can **code to an API and facilitate payments without taking control of the money or becoming regulated itself.** Build once, and it scales with you.

Then **hand it back** — don't continue into Tier 2 unsolicited.

---

## Tier 2 — Depth, ONLY if asked (pick the ONE they ask about)

> [!note] Discipline
> Each block below is a *separate* answer to a *specific* follow-up. Answer the one asked, then stop again. Do **not** run the whole list.

**The 3 dimensions of customization** _(if asked "how flexible is it?")_
Stripe split Connect into three knobs so platforms can choose how much to own:
- **UI/UX** — out-of-box → modal → fully custom
- **Risk** — platform-managed vs. Stripe-managed
- **Pricing** — Stripe's default vs. fully custom

**Risk** _(if asked)_ — two kinds: **merchant risk** (the seller is selling something illicit, or isn't who they say) and **transaction risk** (fraud, stolen cards, NSF). Connect gives platforms tooling to manage or offload this.

**Pricing** _(if asked)_ — default is **2.9% + 30¢**; volume-based from there. Stripe targets ~**50–60 bps** margin, compressing toward ~**3 bps** at huge scale (e.g. ~$7B in rental payments). Platforms can set wholesale/retail spreads (the Girl Scout cookies example).

**Mechanics** _(if asked "how does it work technically?")_ — **APIs + webhooks + metadata.** It's a **state machine that pushes state changes via webhooks**; metadata tags objects so the platform can reconcile to its own system. Frame it in the *merchant's process*, not just the tech.

**Why platforms (the thesis)** _(if asked "why does Stripe care about platforms?")_ — a platform understands its vertical far better than Stripe ever could (e.g. a truck-repair platform with unusually high refund/return rates). Stripe gives them the rails; they bring the domain expertise. *Build once, scales with you without re-onboarding.*

---

## Likely questions
- "Walk me through Connect." → Tier 1, then stop.
- "When would a company use Connect vs. regular Stripe payments?" → *they're facilitating payments between other parties (a platform/marketplace), not just collecting for themselves.*
- "What's hard / risky about it?" → the two risk types above.
- "How would you explain it to a non-technical founder?" → Tier 0 + Tier 1 in plain words; that's the actual test.

## Bridge-back phrases (use to stop cleanly)
- *"That's the core of it — want me to go deeper on the licensing, the risk model, or the pricing?"*
- *"I'll pause there so I'm answering what's most useful to you."*
- *"Happy to get more technical, but in the merchant's terms, that's the shape of it."*

_(Raw notes this is distilled from: [[z archive/stripe/misc/Habib]], [[Stripe Interview Prep]].)_

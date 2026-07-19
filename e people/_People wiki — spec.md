---
title: People Wiki — Template & Structure
type: spec
last_updated: 2026-06-04
tags: [meta, spec, people]
---

# People Wiki — Template & Structure

The standard for the `e people` folder. Draft v1 — for Geoff to review before we build out wikis.

---

## 1. Structure — a folder per person (current convention)

Every roster person gets their **own folder** under `e people/`, named with their **first name, all lowercase**:

- **Folder:** `e people/<firstname>/` (e.g. `rish/`, `dane/`, `marcin/`). Use the name Geoff actually uses — e.g. **Jeff Andre → `jef/`** (he writes "JeF"), not `jeff`.
- **Inside each folder:**
  - the wiki index, **`<firstname> — wiki.md`** (em dash);
  - that person's **source notes**, gathered (moved) from the Bear archive and elsewhere.
- **Tier** stays a frontmatter field (`tier: 1/2/3`) for sorting/roster — not location.
- **Only move notes clearly about that one person.** Multi-person or same-name notes stay in the archive until confirmed (see §3a). A shared first name is not a match — there are multiple Andrews, Jeffs, Bens, Karens in the archive.
- **Sensitive data** (SSNs, medical IDs) → keep in `id/` (or the person's info note), referenced by link, never headlined.
- **`names/`** (baby-name brainstorms) and **`Mimosa/`** are left untouched. **Mimosa is omitted by request.**

## 2. File naming

- Folder: **`<firstname>/`** lowercase (the name Geoff uses).
- Wiki index: **`<firstname> — wiki.md`** (em dash), inside the folder, beside that person's source notes.

## 3. The wiki template

Frontmatter for structured/queryable fields, a one‑line **Snapshot**, then the four agreed sections, then **Sources**.

```markdown
---
name:
aka:
relationship:        # partner / son / cofounder / friend / colleague ...
tier:                # 1 inner circle · 2 close · 3 wider
location:
birthday:
contact:
connected_to:        # [[Other Person]], [[Other Person]]
last_updated: 2026-06-04
tags: [person]
---

# {Name}

**Snapshot.** One or two lines — who they are to me, the essence.

## Vitals & contact
- Full name / aka:
- Relationship:
- Birthday:
- Location:
- Contact: (phone, email — sensitive IDs link to [[id/...]])
- Family & connections: [[...]]
- How we met / how I know them:

## History & arc
The narrative of the relationship over time — key chapters, turning points,
shared history. Dated where the notes allow.

## Candid reflections
The honest private read: the dynamics, what I value, what's hard, the patterns.
(This is where material like "Hard truths" lives.) For my eyes.

## Open threads & gifts
- Active follow-ups / things to do:
- Gift ideas:
- Their preferences (food, interests):
- Dates coming up:

## Sources
Backlinks to the original notes this wiki draws from:
- [[note]]

## Update log
- YYYY-MM-DD — what changed
```

*Maintenance:* `last_updated` + the **Update log** track drift. Default is on-demand ("refresh Micah" → I re-sweep notes/messages/files for anything new and propose edits). Once all 20 exist, a monthly scheduled digest can flag wikis with meaningful new material.

## 3a. Identity rules (don't assume)

- **Never map a first name, nickname, or initials to a roster person without direct evidence.** "Drew" ≠ Andrew, "Sam" ≠ any one Sam, etc. A shared name is not a match.
- When an identity is uncertain, **attribute it tentatively and flag it for confirmation** rather than asserting it.
- **Always prefer the most recent fact** (especially addresses) and keep older values as labeled history.
- Distinguish people who merely *share a name* — there can be several "Andrew"s, "Jeff"s, "Sarah"s in the sources.

## 4. How each wiki gets built

For each person I'll sweep the Bear archive, `e people`, daily notes, and meetings for every mention, then synthesize into the template — quoting your own words where they're vivid, dating the history, and listing every source note at the bottom so nothing is lost and you can trace any claim.

---

## Appendix — Proposed roster (for confirmation)

Built from two signals: your **phone Favorites** (who you've curated as personal) and **note volume** (how much written material exists to draw on). Relationship guesses are mine — please correct.

*(Tiers below are closeness groupings only — they set the `tier` field, not where the file lives. Folder vs. single file follows the material rule in §1.)*

### Tier 1 — Inner circle
| # | Person          | Likely relationship | Notes on file |
| ----- | --------------- | ---------------------------------------- | ------------- |
| ~~1~~ | ~~Mimosa~~      | **Omitted at Geoff's request** (privacy) | — |
| 2 | Dane Hurtubise  | Cofounder (Spoken); emotionally central | 170 |
| 3 | Naya (Jean)     | Child | 94 |
| 4 | Enso (Lawrence) | Child | 31 |

### Tier 2 — Close friends & key collaborators
| # | Person | Likely relationship | Notes on file |
|---|--------|--------------------|--------------|
| 6 | Micah Davis | Close friend (only child) | 60 |
| 7 | Rish Gupta | Close friend / collaborator | 96 |
| 8 | Marcin Jakub Pogroszewski | Friend / business | 54 |
| 9 | Lief Andre | Friend / family (Andre) | 39 |
| 10 | Dhruv | Friend / collaborator | 45 |
| 11 | Andrew Moore | Friend / collaborator | — |
| 12 | Ben Springwater | Friend | 2 + messages |
| 13 | Collin Bjork | Friend | messages |
| 14 | Khalid Dherbas | Friend (UK) | 19 |

### Tier 3 — Family & wider favorites
| # | Person | Likely relationship | Notes on file |
|---|--------|--------------------|--------------|
| 12 | Beverly Abraham | Family (mother?) | 3 + messages |
| 13 | Karen Abraham | Family | messages |
| 14 | Rebecca Andre | Family / in-law | messages |
| 15 | Jeff Andre | Family / in-law | messages |
| 16 | Savannah Jean English | Family / close (the "Sav" in notes) | 3 |
| 17 | Paulie Harraka | Friend | messages |
| 18 | Punit Shah | Friend / colleague | 1 |
| 19 | Skye Gilbert | Friend / colleague | messages |
| 20 | Robin Perani / Jessica Talbert / Jeff Boes | Friends | messages |

### Tier 2 — second wave (built 2026-06-04)
| Person | Relationship | Folder | iMsgs |
|--------|--------------|--------|-------|
| Jeff Boes | Close friend / chosen brother (UT Austin, 20 yrs) | `jeff/` | 5,201 |
| Jesse Buckingham | Close friend / Vooma founder I backed (GSB) | `jesse/` | 1,671 |
| Jessica Talbert | Close friend (GSB), Spoken investor | `jessica/` | 2,547 |
| Robin Perani | Close friend, family-to-family (Marin) | `robin/` | 2,454 |
| Patrick Schmitt | Close friend (GSB), Spoken investor; vows w/ Naomi | `patrick/` | 1,440 |
| Peter Bouck | Dear friend (UT/Paul Woodruff lineage) | `peter/` | 137 |
| Gene Cook | Founder friend / advisee (Supergifter) — business-leaning | `gene/` | 298 |
| Paulo Serna | Old friend, slow-cadence/deep (East Bay) | `paulo/` | 373 |

*Note: `jeff/` = **Jeff Boes**; distinct from `jef/` = Jeff Andre. Patrick has his own `patrick/` folder; the joint vows note stays in `naomi+patrick/`.*

### Tier 2/3 — third wave (built 2026-06-04)
| Person | Relationship | Folder | iMsgs |
|--------|--------------|--------|-------|
| Kenny Diekroeger | Close friend (GSB), Spoken investor | `kenny/` | 3,713 |
| James Dempsey | Close friend ("Piggies"), New England | `james/` | 5,255 |
| Spike Lipkin | Close friend (crew); Newfront; Marin | `spike/` | 3,160 |
| Dan Kerrigan | Old friend (Boston) | `dan/` | 3,489 |
| Jordan Blashek | Close friend / chosen brother; author of *Union* | `jordan/` | 916 |
| Celine Chalhoub | Close friend, couple-to-couple (w/ Nico) | `celine/` | 935 |
| Derek Lynch | Dear/tender friend (NM) | `derek/` | 847 |
| Robert "Robbie" Mitchnick | Close friend + Spoken investor (NYC) | `robbie/` | 837 |
| Sarah Petnic | Close friend, Andre-family-embedded (tie to confirm) | `sarah/` | 3,294 |

*Resolved mystery threads: Kenny = "decaf espresso/holiday stomp/650"; James = "split pig council/Houston-281"; Dan = "Boston/what's cookin homie." Jen Buckner intentionally skipped (work). `sarah/` = **Sarah Petnic** (≠ Ben's Sarah, ≠ Kenny's wife Sarah).*

### Note-heavy — other swap-in candidates
Still have lots of written material if you want more added: **Nimit** (30), **Mihai** (25), **Jeff Chang**, **Sam** (coaching).

### Confirmed / resolved
- **Micah** = close friend (only child). → Tier 2, keeps his existing folder.
- **Dhruv** and **Andrew Moore** added to the roster.
- Building order: **start with Micah.**

### Still open
- Anyone important who is *neither* a phone favorite nor frequent in notes that I'd otherwise miss?

### Resolved via email
- **Mimosa's maiden name is Andre** → the **Andre family (Lief, Rebecca, Jeff) are Mimosa's family / Geoff's in-laws.**
- **Geoff's birthday: Feb 20, 1986** (the "40 Years of Geoff" party was held Feb 14 — a reminder that **party dates ≠ birthdays**; never infer an exact birthday from an invite).
- Wedding-invite emails are sparse for the core people (older / other channels). Better approach: enrich each person from email by searching *their own address* during their individual build, rather than broad sweeps.

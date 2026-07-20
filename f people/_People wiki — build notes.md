---
title: People Wiki — Build Notes (lessons to self)
type: process
last_updated: 2026-06-04
tags: [meta, process, people]
---

# Build Notes — lessons from Geoff's edits

Working memory for building these wikis well. Read before each new person.

## Pre-flight checklist (run for every person)
1. Pull **all four sources**: notes (Bear archive + e people), **WhatsApp** (ChatStorage.sqlite), **iMessage** (chat.db), **email** (search their own address).
2. **Address:** use the **most recent** one; check group threads for updates; keep older as labeled history.
3. **Identity:** never map a nickname/first name/initials to someone without direct evidence. Flag uncertain people "(confirm)".
4. **Relationships:** don't infer from folder placement or proximity in a list — confirm.
5. **Quantities/facts drift** (e.g. watch counts): prefer the latest, state confidence, don't lowball from one old note.
6. **No exact birthdays from party dates.**
7. Don't overstate (no "reached the Nasdaq" when it was a tower-billboard milestone).
8. Fill `last_updated` + an **Update log** entry noting sources used and any corrections.

## Corrections log (what I got wrong → the rule)
- Said Micah gave **2 watches** → actually **4, incl. a Grand Seiko**. *Rule: facts accrete; verify quantities, don't anchor on one note.*
- Filed **Micah** as possibly Geoff's child → he's a **close friend (only child)**. *Rule: don't infer relationship from folder grouping.*
- Put **Rish in "all else"** → felt wrong. *Rule: tier = metadata; folder-vs-file by material; flatten into `e people/`.*
- Inferred **Geoff's birthday = Feb 14** from a party → it's **Feb 20**. *Rule: party dates ≠ birthdays.*
- Listed **Marcin in Austin** → he moved to **Ann Arbor**. *Rule: people move a lot — always most-recent address.*
- Called the bachelor-party **"Drew" = Andrew Moore** → it's **Drew Winget**. *Rule: a shared/short name is NOT a match; never assume identity.*
- Overstated **Spot AI "reached the Nasdaq"** → it was a Nasdaq-tower milestone, not an IPO. *Rule: don't inflate.*
- Assumed **Spoken "died"** → it's **still operating** in 2026. *Rule: check live signals before declaring a company/relationship dead.*
- **Jeff Andre is spelled "JeF" → folder `jef/`.** A plain "Jeff.md" note turned out to be **Jeff Boes** (not in the 20). *Rule: use the name Geoff actually uses; a first name alone can point to several people.*
- Names that collide in the archive (leave ambiguous ones until confirmed): **Andrew** (Moore vs Yates vs others), **Jeff** (Andre/JeF vs Boes vs Chang vs Levere), **Ben** (Springwater vs Buckingham vs others), **Karen**, **Rebecca**, **Jess/Jessica** (Talbert vs others), **Robin** (Perani vs Carole Robin the author vs others), **Peter/Paul/Paulo**.
- The **"650 / Codenames / kid Eowyn"** mystery thread from the tier-2 proposal = **Robin Perani** (resolved 2026-06-04 via iMessage). *Rule: unidentified high-volume threads can be cracked by matching note content (kid names, games) to a contact.*
- **Geoff's home address = 3424 Victor Ave, Oakland CA 94602** (4th floor; site of the Feb 14 2026 40th-birthday party). Do **not** attribute this to others who appear near it in notes (e.g. it sits under "Gene Cook" in Explorer Fund 3 but is Geoff's, not Gene's).
- Almost wrote that **Jeff Boes** was at "my father's celebration (2019)" — the 2019 msg was about **"Paul's celebration,"** a different event; Geoff's father died **~May 2018** (per Peter Bouck's condolence). *Rule: don't merge two named events into one.*

## Second wave (2026-06-04) — Jeff Boes, Jesse Buckingham, Jessica Talbert, Robin Perani, Patrick Schmitt, Peter Bouck, Gene Cook, Paulo Serna
- All 8 built from notes + iMessage + WhatsApp-contacts (for number resolution). Folders: `jeff/ jesse/ jessica/ robin/ patrick/ peter/ gene/ paulo/`.
- `jeff/` = **Jeff Boes** (≠ `jef/` Jeff Andre). Patrick got his own folder; joint vows stay in `naomi+patrick/`.
- Source-DB access this session: had to re-request **~/Library/Messages** and the **WhatsApp group container** (only the vault was mounted at start).

## Third wave (2026-06-04) — Kenny Diekroeger, James Dempsey, Spike Lipkin, Dan Kerrigan, Jordan Blashek, Celine Chalhoub, Derek Lynch, Robbie Mitchnick, Sarah Petnic
- Proposed the next 10 from **iMessage volume × note cross-refs**; Geoff cut **Jen Buckner** (work) → built 9. Folders: `kenny/ james/ spike/ dan/ jordan/ celine/ derek/ robbie/ sarah/`.
- Cracked three long-unidentified high-volume threads via content: **Kenny** = "decaf espresso / holiday stomp / 650"; **James Dempsey** = "split pig council / ramen / Houston-281"; **Dan Kerrigan** = "Boston / what's cookin homie."
- **Sarah Petnic**: built with relationship **flagged, not assumed** — she's deep in Andre-family logistics (kids Syl & Ruthie, Napa/707, "Jef will stay home with Ruthie," Andre family dinners) but also reads as a peer friend "included" by Geoff & Mimosa. *Rule: with multiple same-name people (3+ Sarahs) and an ambiguous tie, describe the evidence and ask.*
- **Two Natashas:** James Dempsey's partner Natasha ≠ Dane's partner Natasha. *Rule: don't merge same-named partners across people.*
- Geoff's father **died ~May 2018** — re-confirmed by condolence messages from Celine, Derek (May 7–8, 2018).

## Consent / scope
- **Mimosa is intentionally omitted** at Geoff's request — she's not interested in this, and he knows her well enough not to need it. **Do not build or maintain a Mimosa wiki.**
- Respect that some people are off-limits; when in doubt about a sensitive person, ask before building.

## Source mechanics (so I don't re-derive each time)
- WhatsApp: `ChatStorage.sqlite` → `ZWACHATSESSION` (ZPARTNERNAME, ZCONTACTJID) + `ZWAMESSAGE` (ZTEXT, ZMESSAGEDATE [Apple epoch sec], ZISFROMME, ZFROMJID, ZCHATSESSION). Contacts: `ContactsV2.sqlite`.
- iMessage: `chat.db` → `message` (text, date [Apple epoch ns], is_from_me, handle_id) JOIN `handle` (id = phone/email). Needs Full Disk Access (granted).
- Group threads are the best place to catch **current addresses** and life changes.

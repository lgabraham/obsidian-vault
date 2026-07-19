# Vault map & filing rules

_Read this first. This vault is for **thinking in markdown** — notes, drafts, journaling, planning. Binaries (PDFs, images, Office docs) and finished shareable artifacts do NOT live here; they go to Google Drive._

## Structure
- `a Inbox` — capture point; triage from here
- `b Daily` — daily notes / journal
- `c Weekly` — weekly notes / reviews
- `d Creativity` — creative writing & ideas
- `e People` — notes on people
- `f Home` — household / home
- `g Meetings` — meeting notes
- `h Agents` — agent prompts/configs **only** (not agent outputs)
- `i Archive` — old notes

## Rules
- **Markdown only.** If you create or receive a binary, put it in Google Drive `z archive/vault records` and link to it from the note.
- **File by subject, not by source.** An agent-written finance memo is a finance doc → it belongs in Drive `e finance + legal`, not in `h Agents`.
- When unsure where a note goes, drop it in `a Inbox`.
- Naming: lowercase letter + space + name. (Existing folders are Capitalized; lowercase them from inside Obsidian if desired so links update.)

See `~/Documents/README.md` for the full cross-store map (Documents · Drive · Vault).

---

## System map

_Where everything lives, what syncs where, and what's backed up._

### Stack
- **iCloud** — photos, contacts, desktop. Syncs to iPhone.
- **Google** — Gmail + Drive. Drive holds binaries and finished, shareable artifacts; system of record.
- **Obsidian** — this vault. Markdown thinking only. Synced across machines and phone via **Obsidian Sync**.

### Devices
- **iPhone** — mobile hub. Photos, contacts, and iCloud Desktop/Documents; source of truth for contacts.
- **M5 Mac** — primary machine. Runs Obsidian; full Drive + iCloud sync.
- **M1 Mac** — role TBD. Candidates: always-on box for scheduled tasks, or an offline machine for sensitive-data work.

### Sync & backup
- **Vault** — backed up via Obsidian Sync, so it isn't relying on a single local copy.
- **iCloud** — syncs photos, contacts, and the desktop to the iPhone and other Apple devices.
- **Drive** — home for binaries and finished work; the vault stays markdown-only by rule (above).
- Contacts are phone-first via iCloud — edit them there, not in scattered notes.

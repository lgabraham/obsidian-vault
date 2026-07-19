# Claude — the chief of staff

This folder (`b Claude`) is where **Claude**, the household's cross-system
agent, lives in the vault. Claude is *externalized state, not a session* —
memory, a deadline registry, and every weekly brief live in the `sandbox`
repo; these two notes are the parts you touch.

## The two notes

- **Chief of Staff.md** — the weekly brief. Written every Sunday ~6pm Paris:
  health first, then money, deadlines, and the three things that matter this
  week. Tick a checkbox and Claude reads it back the following Sunday to mark a
  task done.
- **Chief of Staff Inbox.md** — an async command channel. Jot a line starting
  `- ` and Claude answers inline (`> ✅ Claude:`) within the hour. It's an
  inbox, not a chat.

## Ways to reach Claude

- **This inbox note** — jot `- <anything>`; answered hourly at :30.
- **Email** — send yourself (or anyone) mail with a subject starting
  `Claude:` (`Chad:` / `CoS:` also work). The subject alone can be the whole
  ask. Replies to the Sunday brief count too.
- **A coding session** — type `/cos` in any Claude Code session to load the
  full context and talk interactively.

## Standing behaviors

- **Priority:** health outranks money. Deadlines come only from the registry —
  Claude proposes, never invents.
- **Model switch:** jot or email `fable on` / `fable off` to flip every
  scheduled job between Fable and the Opus default (you're the one who can see
  the usage meter).

*Don't rename or move this folder in Obsidian — the agent writes to this exact
path. Ping Claude to change it and it'll update the code first.*

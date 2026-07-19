---
tags:
  - agent/log
type: survey
created: 2026-06-02
---

# Archive Survey — `i Archive`

Goal: figure out what's usable as LLM context vs. what's just weight.

## Headline numbers

- **494 MB**, ~6,762 files total (on-disk; logical content is larger due to duplicate files)
- Only ~3,500 are real notes (markdown); the rest are binary documents, images, and media
- **467 MB (95%) sits in one folder: `papers (dropbox)/`**

## What each bucket means for LLM use

| Bucket | Count | Size | LLM usability |
|---|---|---|---|
| Markdown / text notes | ~3,780 | ~4 MB | Ready now — ideal context |
| PDFs with text layer | 247 | — | Convertible to markdown cleanly |
| Scanned PDFs (no text) | 186 | — | Need OCR before usable |
| Office docs (.doc/.docx/.xls) | ~1,900 | large | Convertible, but mostly legacy |
| Images (.jpg/.png/.tiff) | 847 | large | Need OCR/vision; mostly not text |
| Media (.mov/.wav/.wma) | 9 | 255 MB (logical) | Not text context |
| Junk/system (caches, DB files) | ~194 | ~45 MB | Delete candidates |

## Folder-by-folder

- **`bear/`** — 3,306 markdown files. A Bear notes export. **Real notes, keep, already ideal.**
- **`i phonely/` (71), `40/` (30), `misc/`, `civic/`, `mandolin/`, `numeral/`, `anything/`, `dupe/`** — small markdown sets. Keep.
- **`writings (drive)/`** — 23 `.docx`. Small; look like personal writing. **Good conversion candidates.**
- **`personal (drive)/`** — 20 MB, mixed. Worth a closer look before deciding.
- **`personal (dropbox)/`** — small mixed bag (pdf/jpg/txt/docx).
- **`papers (dropbox)/`** — **467 MB.** Old UT coursework (2005–2007), MBA 2016 application materials, correspondence, Poetry, plus pure junk: `Microsoft User Data`, `eFax Messenger User Data`, `Updater`. **The bulk of the weight; little ongoing context value.**

## Recommendation

1. **Leave the markdown as-is** — it's already perfect LLM context (`bear/` + the small note folders).
2. **Move `papers (dropbox)/` out of the vault** to plain cloud/disk storage. Instantly drops the vault from ~494 MB to ~27 MB and fixes sync + mobile.
3. **Convert the worthwhile binaries to markdown** so they become real context: start with `writings (drive)/` (23 docx) and the 247 text-layer PDFs.
4. **Skip/OCR-later**: the 186 scanned PDFs and 847 images — only OCR the ones you actually want searchable.
5. **Delete junk**: `Microsoft User Data`, `eFax Messenger User Data`, `Updater`, stray `.DS_Store`.

## Next actions (pick any)

- [ ] Relocate `papers (dropbox)/` out of the vault
- [ ] Convert `writings (drive)/` docx → markdown
- [ ] Convert text-layer PDFs → markdown
- [ ] Purge junk folders

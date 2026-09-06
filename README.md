# Vault map

This repository is written by the ring assistant and read by Obsidian. Every change is a
commit whose message is what was said. Files and what they accept:

- `todo.md`: the checklist, `- [ ] item` lines under `# Todo`. Operations: add_line (heading
  "Todo"), tick (match an open item), list.
- `journal/YYYY-MM-DD.md`: the wearer's own journal, one file per local day, entries under
  `## HH:MM` headings, verbatim. Only for notes meant as journal (kind "journal"); never for
  facts to remember.
- `notes/inbox.md`: loose facts and thoughts to remember, one dated bullet each (kind "note",
  the default). Other `notes/*.md` files may be created for a topic when the wearer names one.
- `log/YYYY-MM-DD.md`: the straight log of every capture, written by the app. Never a target.
- `people/*.md`: reserved for the personal CRM (v2).
- `log/*.md` tables such as a food log: add_row appends a row matching the header.

Operations (at most three per note, applied in order):
- append(file, text): add a block at the end; the file is created from its template if missing.
- add_line(file, heading, line): add one line at the end of the section under a heading.
- tick(file, match): mark the one open checkbox matching `match` as done.
- add_row(file, cells): append a table row; the cell count must match the header.
- list(file): read a checklist back (open items and count).

Conventions: paths are lowercase, `.md`, at most one folder deep; never `README.md`.

## Reading and editing it yourself

- **PC (Obsidian):** install Git for Windows and Obsidian; clone the repo; open the folder as
  a vault; install the community plugin "Git" and enable pull on startup and auto push; set
  Daily Notes to folder `journal/` with format `YYYY-MM-DD`.
- **iPhone:** the GitHub app opens any file for an edit and a commit. Obsidian mobile is not
  set up in v1.
- Production writes to `main`; staging writes to the `staging` branch (reset it from `main`
  whenever).

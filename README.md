# Vault map

This repository is the writing: what is true now, kept for David to read and correct. It is
written by the ring assistant and by David on GitHub, and read in Obsidian. Every assistant
change is a commit whose message names the note it came from.

What is *not* here: the transcript of what he said (that is the relay's log), the table of what
was made of each note (records on the relay), reminders (timer rows on the relay) and composed
pages like the morning briefing (views). Those are queried, not filed.

## Files and what they hold

- `README.md`: this map. Kept true whenever the layout changes.
- `dates.md`: facts that belong to a day, one bullet each — `- 02-24 · Emily's birthday` for
  something yearly, `- 2026-10-03 12:00 · Dentist` for a one-off. The morning briefing reads
  it, and nothing else finds dates: a dated fact written nowhere else is a fact the briefing
  will not know. Passed one-offs are taken out.
- `instructions.md`: David's standing word to the assistant — who the people are, what the
  targets are, how he wants things filed. It is appended to the assistant's prompt for every
  job. Not yet written.
- `travel.md`: travel reference — loyalty programme numbers and status, a section per
  programme. Today: United MileagePlus.
- `kinds/<kind>.md`: one document per kind of record, naming the properties every row of that
  kind carries, what to infer when he does not say it, the questions the rows answer, and what
  has been learned about how he talks about it. A kind is born on the second note of its sort.
  Today: `meal`, `exercise_set`, `todo`, `measurement`, `cart`, `proposal`, `lookup`.
- Topic documents may be added where nothing fits, named plainly, at most one folder deep,
  lowercase, `.md`.

## The previous system's files

Read for history; nothing is filed into them any more.

- `todo.md`: the old checklist, `- [ ] item` under `# Todo`. The live list is now records of
  kind `todo`, on `/notes/todo`. The open items here were never moved across.
- `notes/inbox.md`: loose facts captured before records existed.
- `journal/YYYY-MM-DD.md`: the wearer's own journal, entries under `## HH:MM`.
- `log/YYYY-MM-DD.md`: the old straight log of captures, Sep 6-8 only.
- `schedule.md`: the old reminder table, empty since reminders became timer rows.
- `people/*.md`: never created; a person's document is written when there is something to say
  about them.

## Reading and editing it yourself

- **PC (Obsidian):** install Git for Windows and Obsidian; clone the repo; open the folder as
  a vault; install the community plugin "Git" and enable pull on startup and auto push; set
  Daily Notes to folder `journal/` with format `YYYY-MM-DD`.
- **iPhone:** the GitHub app opens any file for an edit and a commit. Obsidian mobile is not
  set up in v1.
- Production writes to `main`; staging writes to the `staging` branch (reset it from `main`
  whenever).

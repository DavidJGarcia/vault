# Vault

My second brain, kept by the agent behind the ring and edited by me here.
Markdown only. Every write by the agent is one commit that names the note it came from.

## How it is used

- The agent reads and writes this repository through the relay. It never sees git.
- The `main` branch is production. The `staging` branch is what a pull request's worker writes to; reset it from `main` whenever.
- Records (the table of what was said and inferred) are not here. They live in the relay and are read at `/notes/records`.
- The log of what happened is not here either. This is what is true now.

## What is where

| Path | What it is | Who writes it |
|---|---|---|
| `instructions.md` | My standing instructions to the agent: who people are, targets, how I want things filed. Appended to its prompt for every note. | Me, and the agent when a note says "from now on". |
| `dates.md` | Facts that belong to a day: birthdays, appointments I mention without asking for a reminder, expiries. One line each, newest at the end; a month-day alone recurs every year, a full date happens once. The only place the morning briefing looks for a dated fact, so a fact not written here is one it will not know. | The agent; me. |
| `kinds/<kind>.md` | One document per kind of record: what it is, its properties, how to enrich, what gets asked, what it has learned about how I talk about it. A kind is born on its second occurrence. | The agent; me, to correct it. |
| `gifts.md` | Gift ideas, by person: what each one wants, the occasion, roughly what it costs, whether it is bought. | The agent; me. |
| `people/` | One document per person: who they are, and the facts about them worth looking up later. | The agent; me. |
| `home/` | The house: the chore rotation, the appliances, and how a thing is maintained. | The agent; me. |
| `notes/` | Reference I asked for and will come back to: how a job is done, what a filing costs, what a tool needs. | The agent; me. |
| `trips/` | One document per trip, named by its departure date: where, when, and what had to be ready. | The agent; me. |

Reminders are not a file. They are timer rows on the relay, which fires them whether or not
the desktop is on; `timer list` is the whole list, and I set and cancel them by voice.

## History

Kept for reference from the system before this one. Nothing files into them now.

- `archive/notes/inbox.md` — loose dated bullets.
- `archive/todo.md` — the old checklist. To-dos came back as records.
- `archive/log/` — the old per-day log. The relay keeps the log now.
- `archive/schedule.md` — the old reminder table, one row each. Timer rows on the relay replaced it.

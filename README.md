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
| `kinds/<kind>.md` | One document per kind of record: what it is, its properties, how to enrich, what gets asked, what it has learned about how I talk about it. A kind is born on its second occurrence. | The agent; me, to correct it. |
| `schedule.md` | Reminders and timers, one row each. Still drives the relay's scheduler until timers replace it. A change takes effect at once. | Me, and the agent by voice. Keep the table's shape. |
| `gifts.md` | Gift ideas, by person: what each one wants, the occasion, roughly what it costs, whether it is bought. | The agent; me. |
| `people/`, and other folders the agent adds | Facts worth looking up later, filed where I would look. Look before adding; follow what exists. | The agent; me. |

## History

Kept for reference from the system before this one. Nothing files into them now.

- `archive/notes/inbox.md` — loose dated bullets.
- `archive/todo.md` — the old checklist. To-dos came back as records.
- `archive/log/` — the old per-day log. The relay keeps the log now.

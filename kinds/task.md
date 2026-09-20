# task

Something he says he needs to do and has not done yet. Born Sunday September 20, 2026
from "Have a trip tomorrow to get ready. I need to order shirts." — the third to-do
note. The two before it, "I have urgent work to do. Reach out to Earl." and "Personal
backlog: get a new mattress for Abby.", were re-derived into this shape when it was
born.

props:  what (string: the action, short) · status (open | done) · list (work | personal |
        trip_prep | …) · due (ISO date or datetime, when a real moment binds it) ·
        urgent (bool) · for (person, when the task is for someone else) · why (what it is
        for) · done_at

enrich: name the list from how he framed it — "urgent work" is work, "personal backlog"
        is personal, anything tied to a trip is trip_prep. Give a due only when a real
        moment binds it (a departure, an appointment) and say where the date came from;
        leave it null for backlog items. urgent only when he says so or the moment is
        inside a day. status stays open until a later note closes it, and then done_at
        is the moment he said it was done.

ask:    "what is open"; "what do I need to do before the trip"; how long an item has sat
        open; open items by list.

notes:  he opens one with "Personal backlog:", with "I need to", or with a bare
        imperative ("Reach out to Earl"). One task per record, even when a note carries
        two, so each can close on its own. A later note that closes or changes one
        updates that record rather than filing a second. The old todo.md at the root of
        the vault is history from the system before this one, not this kind.

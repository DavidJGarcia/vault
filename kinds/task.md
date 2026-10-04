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
        **Superseded by `todo` on September 21, 2026.** This kind stopped taking new
        rows the day the todo kind was born, and nothing has been filed here since
        September 21. Its fourteen rows are history: twelve trip_prep items for the San
        Ramon trip, all closed between September 20 and 21.
        The two that were still open were invisible — not on `/notes/todo`, not in the
        open list, not in a briefing — so the weekly pass of October 4, 2026 moved them
        to `todo`: "Reach out to Earl" (rec_20260916T153456145718cf3b09, open since
        September 16) and "Get a new mattress for Abby"
        (rec_20260916T124414936113c9a91d, same day). Each carries `moved_from_kind` and
        `moved_by`, and the undo is on the row. The twelve closed rows were left here
        rather than moved, because `update --done` can only mark a row done now and
        would have dated September's packing to October.

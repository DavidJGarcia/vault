# personal_fact

A standing fact about David himself: true until he says otherwise, not an event.
Born Tuesday, October 6, 2026 from "Just 5 ft. 5.5 in. tall." — the second of its
sort, after "I work at the accounting firm Armanino" (October 5, 2026), which is
now filed under this kind too.

props:  field (string: one lowercase word for what the fact is about — height,
        employer, …) · value (the fact in the fewest words; a number where it is
        a number) · unit (string, when value is a number) · detail (string:
        what the fact amounts to, including anything found out about it) ·
        filed_to (list of vault paths) · sources (list of URLs) · assumed (list)
enrich: work out what the fact implies and put it in detail — a height read
        against his weigh-in rows, an employer's offices and headquarters — and
        write the fact into `people/david.md` under the heading it belongs to,
        naming the path in filed_to.
ask:    "how tall am I", "where do I work"; everything standing about him in one
        query. `people/david.md` is the readable form of the same thing.
notes:  one row per field — a later note that changes the same field updates
        that row rather than filing a second. He says these flatly and in
        fragments ("Just 5 ft. 5.5 in. tall."), never as a reminder, and the age
        of the note changes nothing: filed at spoken_at. A body fact belongs
        here and is read against `kinds/weigh_in.md`, never filed as a weigh_in.

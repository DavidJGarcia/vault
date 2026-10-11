# person_fact

A standing fact about someone other than David: who they are to him, who belongs
to whom, what they are allergic to, when they were born. True until he says
otherwise, not an event. Born Sunday, October 11, 2026 from "Jensen's son is
named Edmund." — the third of its sort, after "Dad's birthday is May 11, 1955."
(September 17, 2026) and "Abby is allergic to cefalexin." (September 21, 2026),
both of which are now filed under this kind too. Facts about David himself are
`personal_fact`; this is everyone else.

props:  person (string: the name as he said it) · relation (string: who they are
        to him, or that it was never said) · field (string: one lowercase word
        for what the fact is about — birthday, allergy, son, …) · value (the
        fact in the fewest words; a date as YYYY-MM-DD) · detail (string: what
        the fact amounts to, including anything found out about it) ·
        filed_to (list of vault paths) · sources (list of URLs) · assumed (list)
enrich: look through `people/`, `gifts.md` and the earlier records for who the
        person is before writing that the relation was never said; transcribe
        the name as heard and say the spelling is unverified. Write the fact
        into `people/<name>.md` under the heading it belongs to, starting that
        document when there is none, and name the path in filed_to. A fact that
        belongs to a day goes in `dates.md` as well — that is the only place the
        briefing looks. These are private people: do not search the web for
        them. A drug, a place or anything public in the fact may be looked up.
ask:    "what do I know about X"; who is related to whom; every standing fact
        about the people around him in one query. The `people/` documents are
        the readable form of the same thing.
notes:  one row per person and field — a later note that changes the same pair
        updates that row rather than filing a second. He says these flatly, in
        one short sentence, with no relation and no occasion ("Jensen's son is
        named Edmund."), and the age of the note changes nothing: filed at
        spoken_at. A fact about a kid's health belongs here, under field
        allergy or condition, and is said about one of the six kids (David,
        Derek, Abigail, Jeffrey, Andrew, Cody).

# captains_log
A spoken journal entry, opened with "Captain's log". Born Sunday November 9, 2026 from the
second one — "The temple open house on Saturday was a long wait and then a rushed tour" —
the first being Saturday November 7, 2026, "Yesterday we went up to the Archibalds' house".

props:  covers (the day or days the entry is about, ISO date or range) · entry (what
        happened, his account tidied) · people (list: who was there, resolved to the names
        already on record) · places (list) · assumed (list: every reading taken,
        transcription fixes included) · sources (list, when the web was read)
enrich: resolve "yesterday", "today", "Saturday" against spoken_at plus lag_s and put the
        date in covers; name the people and places from what is already on record, and fix
        a garbled name rather than filing the garble; look up a public event he names.
ask:    "what did I do that weekend" — the account of a day when no other record covers it.
notes:  he narrates a day or two just past, so an entry is an observation filed at
        spoken_at and its age changes nothing. An entry often corrects rows filed by
        assumption while he was away (Friday November 6's meals, filed place: home, were at
        the Archibalds'). An entry about a trip is also written into that trip's document
        under trips/: the record is the row, the document is the reading.

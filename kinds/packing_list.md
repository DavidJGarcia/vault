# packing_list

Items he names for a trip he is packing for. Born November 5, 2026 from
"Packing list: iPads, chargers", the second note of its sort thirty seconds after
"Packing list for in the morning: toothbrushes, mouth guard, deodorants. Maybe more to add."

props:  trip (YYYY-MM-DD, the departure date) · items (list of strings, one thing each) ·
        open (bool: he said more was coming) · file (the vault document holding the merged list)
enrich: split a transcription that glued the items together ("iPadschargers" is iPads and
        chargers); date the departure from what he said ("in the morning" is tomorrow);
        read plurals as packing for more than himself; keep `open` true until he says the
        list is done.
ask:    "what's on my packing list" — every row for one departure is `--prop trip=<date>`,
        and the document at `file` is the same list, merged and tickable.
notes:  he adds to a list in several short captures, seconds or hours apart, each its own
        row; the list itself lives in trips/<departure date>.md and that is what he reads.
        A packing list is not a to-do list and not a reminder: nothing buzzes unless he
        asks for a time.

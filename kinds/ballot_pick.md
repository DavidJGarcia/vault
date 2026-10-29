# ballot_pick

A choice he has made in one contest on his ballot. Born October 29, 2026 from
"Hinoza for governor next", the second pick of the November 3, 2026 election; the
first was "Talerico is my pick" the same morning, retyped to this kind.

props:  contest (string: the office as the ballot prints it) · contest_no (int: 1-22 on the
        vote view) · choice (string: the candidate as the view lists them, party letter
        included; "For" or "Against" on a proposition) · picked_on (YYYY-MM-DD)

enrich: match what he said against the candidate names on the `vote` view, not the numbers -
        he says "Talarico", never "choice one", and the transcription will be rough
        ("Hinoza" for Hinojosa). Fill contest and contest_no from the view. A name that
        fits two contests (Hawkins in Place 7, Kelly in Place 2 and Agriculture) is asked
        about rather than guessed - mark nothing.

ask:    "what have I picked so far"; which contests are still open; the Picked N of 22
        counter on the view, rebuilt from these rows if the page is ever lost.

notes:  the record is the durable copy; the arrow on the `vote` view is what he reads, and
        every pick rewrites that page whole (instructions.md, October 29, 2026). A later
        pick that contradicts an earlier one updates that row rather than filing a second -
        he changed his mind, there is still one choice. He often adds "next" or "which race
        is next", which is a question about the first contest with no arrow, not part of
        the pick.

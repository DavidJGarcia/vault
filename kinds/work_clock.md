# work_clock

A boundary of his workday, said as he crosses it: a clock-in or a clock-out. Born
September 28, 2026 from "Done with work.", the second of its sort after "Start work."
that same morning at 9:04.

props:  edge (string: in, out) · started_at (ISO, on both rows: the in of this session) ·
        ended_at (ISO, out rows only) · hours (float, out rows only: the span in hours) ·
        duration (string, as it reads: "7h 46m") · day (YYYY-MM-DD) · weekday (string)

enrich: on an out row, pair it with the day's unclosed in row and work out the span;
        put the span and the two clock times on the wrist, since that is what the note
        is asking to be told. Breaks are not subtracted - he has never mentioned one -
        so hours is the whole span, and say so when it matters. An out row with no in
        row for the day carries ended_at alone and no hours.

ask:    "how long did I work today"; "how many hours this week" is one call,
        `records --kind work_clock --agg sum:hours --by day`, hours living only on the
        out rows so nothing is counted twice. "When did I stop" is the last out row.

notes:  he says it plainly and briefly - "Start work.", "Done with work." - and names
        nothing else, so a boundary is all it is. Each crossing is its own row: an out
        row is not a correction of the in row. Clocking out reads as the workday over,
        not the day, so household to-dos still belong on the wrist afterwards.

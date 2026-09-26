# weigh_in

A body weight read off the bathroom scale. Born September 26, 2026 from "Weigh in
at 144.6." — the second of two weigh-ins that morning. The first, "Weigh in at
145.0." at 06:58 the same day, was untyped and was re-filed under this kind when
it was born.

props:  weight_lb (number, one decimal as the scale reads) - when (morning,
        midday, evening; from when he spoke it) - fasted (true when it is a
        morning reading before any meal is logged that day) - assumed (list)

enrich: pounds when he names no unit — every weight in his records is pounds and
        he is in Texas. Take `when` from the hour he spoke, not from the word.
        Mark `fasted` true for a morning reading with no meal row yet that day.
        On the wrist, give the change against the previous weigh-in and name
        which one it is measured against; never store the difference on a row —
        a later correction moves it. Trend comes from the rows:
        `records --kind weigh_in --agg avg:weight_lb --by day`.

ask:    "what did I weigh this morning"; "am I down this week"; weight by day,
        and the trend across weeks.

notes:  he says "Weigh in at N" flatly, no unit, one decimal. He weighs more
        than once in a morning: on September 26, 2026 he read 145.0 at 06:58 and
        144.6 an hour later. Two readings an hour apart are two rows, not a
        correction — he corrects by saying so. instructions.md sets no target
        weight, so nothing is compared against one.

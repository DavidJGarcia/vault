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
        On the wrist, give the trend and not the change against the previous
        weigh-in (his standing instruction of October 4, 2026, in
        instructions.md): the morning series, each day's morning readings
        averaged, the last 7 days against the 7 before. Never store a difference
        or a trend on a row — both come from the rows, so a later correction
        moves them. Read the rows for it (`records --kind weigh_in`) and keep
        morning rows only; `--agg avg:weight_lb --by day` is no use on its own
        because it averages evening readings in with the morning ones.

ask:    "what did I weigh this morning"; "am I down this week"; the morning trend
        week over week.

notes:  he says "Weigh in at N" flatly, no unit, one decimal. He weighs more
        than once in a morning: on September 26, 2026 he read 145.0 at 06:58 and
        144.6 an hour later. Two readings an hour apart are two rows, not a
        correction — he corrects by saying so. instructions.md sets no target
        weight, so nothing is compared against one.
        He also weighs in the evening, after eating: 146.4 at 19:27 on
        September 26, 2026, against 144.6 that morning. Evening readings run
        heavier than morning ones and are not comparable to them; compare
        morning to morning, and keep an evening reading out of the morning trend.
        The ring mangles "Weigh in" often, and a bare number with a stub in
        front of it is this kind: "Weight in 146.4", "Evening way in 145.2",
        "Y in 141.4" (September 29, 2026) — all the same note.
        He weighs early: 05:29 on September 29, 2026 is a morning reading.
        Added by the weekly pass of October 4, 2026, from the ten rows on file: he weighs
        most mornings but not every one — nothing on September 30 or October 2 — so a gap
        of a day or two is ordinary and not worth remarking on. And the morning series
        swings further than the trend does: 145.0, 144.6, 144.0, 142.0, 141.4, 139.4,
        141.8, 143.6, a range of 5.6 lb inside nine days, with +4.2 lb over the three days
        from October 1 to October 4. A day-to-day change of two to four pounds is water and
        sodium, not fat — 4 lb of fat is about 14,000 kcal, and his logged days run
        1,300-2,500 — so the day-to-day number is noise and the trend is the signal, which
        is why he asked for the trend instead on October 4, 2026.
        The windows are short while the series is: on October 4, 2026 the earlier week held
        only two mornings. When the earlier window has fewer than three days, give the
        trend and say the baseline is thin, in those words or fewer.

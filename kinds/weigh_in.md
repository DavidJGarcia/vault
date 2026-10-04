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
        He also weighs in the evening, after eating: 146.4 at 19:27 on
        September 26, 2026, against 144.6 that morning. Evening readings run
        heavier than morning ones and are not comparable to them; compare
        morning to morning.
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
        1,300-2,500 — so the change against the last reading belongs on the wrist as he
        asked, but it is not the trend. For the trend, compare a week of mornings to the
        week before.

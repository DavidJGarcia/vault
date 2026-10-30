# litter_emptying

The Litter-Robot waste drawer pulled and emptied. Born October 14, 2026 from
"I emptied the litter robot", the second one after the October 9 emptying that
carried his standing 5-day rule.

props:  by (string: who emptied it) · days_since (number: days since the previous
        emptying, from its `at`) · next_due (YYYY-MM-DD: the day the reminder is
        moved to) · device (string: Litter-Robot waste drawer, not the litter
        itself) · rule_held (bool) · timer (what was done to t_c4c588a5c59f2085)
        · filed_to (the documents written)
enrich: read first person ("I emptied", "just emptied") as David himself; a named
        kid is that kid. Compute days_since from the previous row rather than
        asking. next_due is 18:00 on the last day whose 18:00 is still inside
        five days of this emptying — this day plus four when he emptied it before
        18:00, plus five when at or after — and the reminder is moved to match.
        Set rule_held false and say so when days_since is over 5.
ask:    "when did I last empty the litter robot"; days between emptyings; whether
        the 5-day rule has ever been broken; who does it.
notes:  the reminder is timer t_c4c588a5c59f2085, "Empty the litter robot",
        every:5d at 18:00 — moved forward on every row here, because the rule is a
        maximum and the clock restarts at each emptying. The kids'
        trash-and-litter turns in home/chores.md are a different thing and do not
        count as an emptying. Each row is also written into the table in
        home/chores.md.

        The timing was amended on October 24, 2026, after the first break of the
        rule: a morning emptying plus five days at 18:00 fires *after* the
        deadline, which is what let October 18 (9:49 a.m.) run to October 23
        (9:41 p.m.), 5 days 12 hours. instructions.md carries the amended rule.
        Five rows so far: Oct 9, Oct 14 (4.4 d), Oct 18 (4.1 d), Oct 23 (5.5 d),
        Oct 28 (4.9 d).

        He does not always say it the same day: October 28 was reported on
        Friday October 30 as "I emptied the litter box Wednesday evening". So
        read the day he names, file the row at that moment and not at spoken_at,
        and check the timer against it rather than assuming the row has already
        rolled wrong — an evening with no hour is filed at 20:00, which counts as
        at or after 18:00. He also says "litter box" for the Litter-Robot.

        Past due follows up on its own from October 30, 2026 (instructions.md,
        "Home, continued"): when now is more than five days past the newest row's
        `at`, the morning briefing names it every morning — `Litter robot: 6d,
        past due` — until an emptying is filed, and the weekly pass says it in
        the view. Inside five days, no row. The timer alone cannot do this: it
        repeats every:5d whether or not the drawer was pulled, so a missed
        occurrence leaves no trace and only these rows show whether it was done.

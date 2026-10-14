# litter_emptying

The Litter-Robot waste drawer pulled and emptied. Born October 14, 2026 from
"I emptied the litter robot", the second one after the October 9 emptying that
carried his standing 5-day rule.

props:  by (string: who emptied it) · days_since (number: days since the previous
        emptying, from its `at`) · next_due (YYYY-MM-DD: this emptying plus 5 days)
        · device (string: Litter-Robot waste drawer, not the litter itself)
enrich: read first person ("I emptied", "just emptied") as David himself; a named
        kid is that kid. Compute days_since from the previous row rather than
        asking. next_due is the day of this emptying plus 5, the maximum his
        standing word allows, and the reminder is moved to match.
ask:    "when did I last empty the litter robot"; days between emptyings; whether
        the 5-day rule has ever been broken; who does it.
notes:  the reminder is timer t_c4c588a5c59f2085, "Empty the litter robot",
        every:5d at 18:00 — moved forward on every row here, because the rule is a
        maximum and the clock restarts at each emptying. The evening hour keeps a
        fire from being held overnight and landing past five days. The kids'
        trash-and-litter turns in home/chores.md are a different thing and do not
        count as an emptying. Each row is also written into the table in
        home/chores.md.

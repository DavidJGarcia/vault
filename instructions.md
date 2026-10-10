# Standing instructions

David's standing word to the worker. It is appended to the worker's prompt for
every job, so what is written here is followed without being asked again.
Newest at the end. He edits this file on GitHub.

## Food

**September 21, 2026 — day totals on every meal receipt.** When a meal is
tracked, the reply also states the day's total calories and total protein,
including the meal just filed. "From now on when you track food that I've eaten,
also respond with total calories and total protein for the day."

The day is his local day, midnight to midnight, America/Chicago. The totals come
from the meal rows, never from a stored running total:

```
records --kind meal --from <today 00:00 -05:00> --to <today 23:59 -05:00> \
        --agg sum:kcal,sum:protein_g,count
```

so a later correction to a meal moves the day with it. Two rows on the wrist is
enough: what was eaten and its numbers, then the day so far.

## Weight

**October 4, 2026 — the trend on every weigh-in receipt.** When he weighs in, the
reply gives the trend, not the change against the previous weigh-in. "From now on
when I weigh in, I want information about the trend not the previous weigh-in."

The trend is the morning series: average each day's morning readings, then compare
the last 7 days to the 7 days before. Evening readings run heavier and stay out of
it — compare morning to morning. The numbers come from the rows, never from
anything stored on a row, so a later correction moves the trend with it:

```
records --kind weigh_in
```

morning rows only — the `--by day` aggregate averages evening readings in with the
morning ones. Two rows on the wrist is enough: the reading, then the trend —
"143.6" / "7-day avg 141.6, down 2.8". When the earlier week holds fewer than
three mornings, give the trend and say the baseline is thin.

## Home

**October 9, 2026 — never more than 5 days without emptying the litter robot.**
"Just emptied the litter robot. Don't ever let me go more than 5 days without
emptying it."

A reminder stands for it: timer `t_c4c588a5c59f2085`, "Empty the litter robot",
`every:5d` at 18:00, next Wednesday October 14, 2026. The evening hour is
deliberate — five days after a 10 p.m. emptying is a night-time fire that waits
for morning and lands past the five days, so the reminder sits inside the window
rather than on its edge.

The rule is a maximum, so the clock restarts at each emptying. When a note says
the litter robot was emptied: file the emptying, then `timer get
t_c4c588a5c59f2085` and `timer put --id t_c4c588a5c59f2085` with `at` moved to
that day plus five days at 18:00, keeping the row and its repeat. Say on the
wrist when the next one is due. Emptying means the waste drawer of the
Litter-Robot; the kids' trash-and-litter turns in `home/chores.md` are a
different thing and do not satisfy it.

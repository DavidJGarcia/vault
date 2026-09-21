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

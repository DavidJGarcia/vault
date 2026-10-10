# exercise_set

One set of one strength exercise, said at the machine. Born late: sixteen rows of this
sort sat untyped from September 14, 15 and 16, 2026, the first from "Row, I left off on
120." on the morning of September 14. The weekly pass of October 4, 2026 wrote this
document and typed all sixteen, because without a kind "when did I last train" could
not be asked at all.

props:  exercise (string: the movement, named plainly - leg press, leg curl, leg
        extension, calf raise, chest press, incline press, pec deck fly, lateral
        raises, lat pulldown, front pulldown, row, rear delts, biceps curl, tricep
        extension) - set (int: which set of that exercise this is) - reps (number;
        null when he names a working weight and no count) - weight_lb (number) -
        per_side_lb (number, when he loads plates and says them per side) - form
        (string, his own word about how the set went: "weak", October 8, 2026) -
        final_set (bool, when he says "final set") - segments (list of {reps,
        weight_lb}, for a drop set said as one note) - ceiling_lb (number, when he
        says what he could go up to rather than what he did) - day (YYYY-MM-DD) -
        assumed (list)

enrich: carry the exercise from the previous row of the session when he does not name
        one - he names it on the first set and then says "second set", "final set".
        Pounds always; he never says the unit. Set number from the words, else one
        past the last row of that exercise today. On the wrist give the set as he
        said it and what it was against the last time he did that movement, since
        that is what the note is for.

ask:    "when did I last train"; "what did I lift"; "am I going up on the leg press";
        sessions per week is `records --kind exercise_set --agg count --by day`, and
        the top weight per movement is `--agg max:weight_lb`. One movement's history
        is `records --kind exercise_set --prop 'exercise=leg press'`, which is the
        query to run when he asks at the machine where he is. `notes/gym.md` holds
        the same thing written out, one line per movement, as of the last session -
        read it first, then the rows for anything newer.

notes:  he logs a whole session set by set, one short note each, a minute or two apart,
        and the session is a block of rows rather than one row. Mornings around
        06:05-06:45, one evening session on file (September 16). The ring mangles the
        weight more than anything else he says, and the fix is the same every time -
        read it as pounds: a clock time ("15 at 1:40" is 140 lb, "I could go up to
        1:30" is 130 lb), a currency amount ("10 at GBP 130" is 130 lb), or a bare
        "1 lb". When it is unreadable, say on the wrist what was assumed - he
        corrects it in the next breath, as he did at 06:31 on October 6. "Can set" is
        "next set". Reps can be a half - "8.5 at 80" is eight full reps and a partial.
        Some machines he loads with plates and says the load per side ("incline press
        with 60 on each side", October 7, 2026): weight_lb is the total plate weight,
        per_side_lb is what he said, and the carriage weight is unknown and not
        counted - so a per-side movement does not compare with the pin-stack numbers
        of another. The ring also mangles the movement's name, and the next note
        settles it: "Stupid leg curl" was seated, "Cap extension" was calf,
        "Bilateral raises" was lateral. He asks where he stands mid-session, three
        times in the four days of October 5-8, and he acts on the answer - told 140
        on the calf raise at 06:27 on October 6, he loaded 150 six minutes later.
        Eight of his fourteen movements were logged for the first time in that one
        week, so most of them have no earlier session to compare against; say so
        rather than inventing a comparison.

# exercise_set
One set of one exercise, spoken as he finishes it. Born 2026-09-16 from "Second set: 15 at 80."
— the second set note, after "Chest press 15 at 80 for set 1." four minutes earlier.

props:  exercise (string, lowercase: chest press, …) · set (int: which set of that exercise
        this session) · reps (int) · weight_lb (number: pounds, so sums are one query) ·
        volume_lb (reps × weight_lb) · assumed (list)
enrich: when he names no exercise, carry the one from the most recent set of the same session
        (within a couple of hours) and record that as assumed. When he names no set number,
        take the next one after the last set of that exercise. Weight is pounds unless he says
        kilos; note the assumption the first time in a session.
ask:    "how much did I lift this week"; sum:volume_lb and count by day, or by exercise; "what
        did I press last time" is the last row for that exercise.
notes:  he speaks one set per note, terse and mid-workout: "15 at 80" is reps at weight, and
        "second set" is the set number, not the rep count. Sets arrive minutes apart, so a
        bare note almost always belongs to the exercise of the note before it. Notes often
        reach here days late; they are filed at the moment he spoke them.

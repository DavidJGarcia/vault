# supplement

Something taken for its effect rather than eaten as food - creatine, a vitamin, a
mineral. Born Thursday, November 12, 2026 from "I had 10 g of creatine this
morning", the second of its sort after "Log 1 scoop of creatine" (September 14,
2026), which is now filed under this kind too.

props:  what (string: lowercase name - creatine, vitamin d, ...) - amount (number)
        - unit (string, as he said it) - dose_g (number: the dose in grams, worked
        out when he gave a scoop or a capsule count) - taken_at (ISO) - basis (how
        dose_g was arrived at) - assumed (list)

enrich: convert a scoop or a capsule count to grams and say the basis - a level
        scoop of creatine monohydrate is 5 g. Say how the dose compares with the
        maintenance dose when it differs; creatine maintenance is 3 to 5 g a day.

ask:    "am I taking my creatine"; "when did I last take X"; doses per day or week.

notes:  a supplement that carries macros worth counting - psyllium fibre, protein
        powder - is a `meal` row instead, so the day totals and the nutrition
        checks see it. This kind is for the ones with no countable nutrition, so
        nothing here is double-counted against the day.
        He paused his supplements before his Function Health blood draw of
        Wednesday, November 11, 2026, because supplemental creatine raises serum
        creatinine and reads as a low eGFR (the reasoning is in the question
        record of October 29, 2026), and resumed the next morning with 10 g.
        Muscle stores fall slowly over about four weeks, so no reloading dose is
        needed after a pause of a week or two: the maintenance scoop is enough.

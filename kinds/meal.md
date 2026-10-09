# meal

Something eaten or drunk, one row per eating. Born September 19, 2026 from
"Track 1, Kirtland Signatures, Carmel S'mores Cluster." The week already held two
dozen untyped food notes, so the kind was born here and those rows were re-filed
under it.

props:  items (list) - portion (string, as he said it) - kcal (number) -
        protein_g (number) - place - meal (breakfast, lunch, dinner, snack) -
        basis (how the numbers were arrived at) - assumed (list) - sources (list of URLs)

enrich: when he does not weigh or say, estimate kcal and protein from typical
        portions and put the basis next to the number on the wrist. A brand and
        product name means label numbers, not an estimate. Day totals are never
        stored on a row - they come from
        `records --kind meal --from ... --agg sum:kcal,count --by day`.

ask:    "how many calories today"; "how much protein this week";
        "when did I last eat X"; calories and protein per day.

notes:  he opens with "Track" or "Log". A second helping of the same thing a few
        minutes later updates the same row rather than filing a new one. He names
        brands often, and the label beats an estimate. Transcription mangles brand
        names ("Kirtland Signatures" for Kirkland Signature) - resolve them and say
        what was resolved.
        A bare number in a Track note is the count of that helping, not a running
        total for the day. On September 19, 2026 "Track 11: Jesus." was read as a
        running count and the cluster row was raised to eleven; he corrected it to
        three nine minutes later. When a number looks like a jump, keep the helpings
        already counted and say what was assumed.
        "a white X" is a transcription slip for "a bite of X": on September 21,
        2026 "a white frozen pepperoni pizza" was filed as a whole white (alfredo)
        pizza, 420 kcal, and he corrected it to a bite of an ordinary pepperoni
        one, about 60 kcal, thirteen minutes later. A puzzling adjective in front
        of a food is worth reading as a portion word first.
        Every meal receipt carries the day so far: total kcal and total protein
        for his local day, including the meal just filed (his standing
        instruction of September 21, 2026, in instructions.md). One query,
        `--agg sum:kcal,sum:protein_g,count`; never a running total on a row.
        "the usual" for breakfast, redefined September 30, 2026 by "Update the
        usual to include 1 cup of blueberries and 3/8 cup of unsweetened vanilla
        almond milk": 27 g Sprouts chocolate whey, 1/2 cup dry rolled oats (40 g),
        1 cup fresh blueberries (148 g) and 3/8 cup unsweetened vanilla almond
        milk (90 ml) - 345 kcal, 24.5 g protein. This replaces the 1 1/2 cups of
        blueberries and no milk of September 22-25, 28 and 29. Expand "the usual"
        from this line, and change it here when he changes the recipe again.
        "a third cup" is 1/3 cup, not the third cup of three. On October 7, 2026
        "I'm having a third cup of pumpkin spice popcorn" was filed as three cups of
        drizzled kettle corn, 335 kcal, and he corrected it six minutes later to
        1/3 cup of LesserEvil Pumpkin Spice Popcorn, 18 kcal. Read a fraction word
        before an ordinal: "a half cup", "a third cup", "a quarter cup" are
        measures.
        A note comparing two ingredients revises the row just filed rather than
        filing a new one. On October 7, 2026 a homemade beef taco was filed at
        5:43 pm, and five minutes later "I'm having more beans than beef" - beans
        were never mentioned in the first note. Read as the fill ratio of that
        taco: beans added as the larger share (1/2 cup refried pinto), the beef
        halved from 4 oz to 2 oz, the fill the same size overall - 405 kcal to
        415, protein 32 g to 24 g. He describes one plate across two captures, so
        a short follow-up with no verb of eating is usually a correction.
        A restated ingredient is a confirmation, not a second helping. On October 7,
        2026 the taco of 5:43 pm already listed guacamole, and at 5:49 pm he said
        "Oh and guacamole." - the row stayed at 2 Tbsp and the receipt said it was
        already counted. When he names an ingredient the row already holds, say so
        rather than adding it again; he gives a quantity when he means more.
        "N more" can mean a food no row holds, and the total he names can cover
        helpings that were never spoken. On October 9, 2026 "I'm having 8 more."
        was filed as eight 0.78 oz Rice Krispies Treats bars, 720 kcal, that bar
        being the only thing counted so far that day; two minutes later he
        corrected it to "8 more whole almonds for a total of 18". The 10 earlier
        almonds had never been captured, so the row was made to carry all 18,
        127 kcal. When "more" has no antecedent in the day's rows, say plainly
        what it was read against.

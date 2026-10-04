# measurement
A dimension of a physical thing, spoken so it can be looked up later. Born 2026-10-04 from the
weekly pass, which found three untyped notes measuring the same fish tank: "Remember the width
of the fish tank is 16 7/8.", "That's the inside width specifically." and "The inside length of
the fish tank is 34 7/8."

props:  subject (string, lowercase: fish tank, …) · dimension (string: width, length, height,
        depth, diameter) · surface (inside | outside) · value (number) · unit (string: in) ·
        value_as_said (string: "16 7/8", his words) · assumed (list)
enrich: inches unless he says centimetres or millimetres, and record that as assumed. Spoken
        fractions become decimals in `value` and stay verbatim in `value_as_said`. When he
        says only "the width", carry the subject from the measurement before it. Inside is the
        useful number for anything he is going to fit something into, so when he does not say,
        take what he is measuring for from the subject and record the assumption.
ask:    "how wide is the fish tank"; every dimension of one subject, newest first.
notes:  he speaks one dimension per note, terse, mid-measuring, and often corrects the one
        before it a few seconds later ("that's the inside width specifically"). A correction
        updates the row it refines rather than making a second row, so the subject has one row
        per dimension and a query cannot double-count. The 2026-09-12 clarification note is
        kept as an untyped row carrying `folded_into`, because its value now lives on the
        width row. Keep `dimension` and `surface` separate; the early rows also carried a
        redundant `measurement` key ("inside length") and it has been taken off with
        `update --unset`.

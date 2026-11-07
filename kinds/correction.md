# correction

A note that corrects something already filed — a figure that was wrong, a word the
transcription mangled, a thing read out of a photo the wrong way. Born November 6, 2026
from "I think you're overestimating on the pizza. These are like ten inch Walmart plates",
which rescaled the four pizza slices of that dinner; the first of its sort was the
transcription correction of October 18, 2026, "When I said 'paste sauce' I meant 'paste
picante sauce.'"

The record is not the correction. The correction is the **edit to the row that was wrong**,
and that row carries `corrected_by` naming this capture. This record is the account of
what moved and why, so a later question about a number can find out where it came from.

props:  what (what was filed wrong and what is right) · corrects (list: the record ids,
        or event ids where no record was filed) · method (how the new figures were
        derived, when numbers moved) · before / after (objects: the figures as they
        stood and as they now stand) · heard / means (a transcription correction: the
        words as transcribed and what he actually said) · assumed (list)

enrich: find every row the correction reaches, not only the newest one — a reading
        applied to four photos is wrong in all four. Re-derive each figure rather than
        scaling the total, so the rows stay comparable with each other. Say the arithmetic
        in `method`: a correction with no stated method is as unfounded as the estimate
        it replaced. When the correction moves a day's food or money totals, record the
        day before and after too, since that is what he saw on the wrist.

ask:    "why is that number what it is"; which rows a given correction touched; how often
        a reading of his photos turns out to be off, and in which direction.

notes:  He corrects in his own voice and expects the fix, not a question — "these are like
        ten inch Walmart plates" is a measurement, and it governs over anything read from
        a photo. A correction that is really a standing rule ("from now on coffee is a
        drink") is a standing_instruction instead and goes in instructions.md; this kind is
        for a one-time fix to what is already filed. Where the correction changes how a
        kind should be read in future, write that into the kind's own document as well.

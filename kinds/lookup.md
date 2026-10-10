# lookup

A question he asked that was answered by looking it up — the web, a store's site, his YNAB
budget, his own documents. Born 2026-10-09 from "How much have I spent on gas this month, and
which category is furthest over budget?"; the first was the 2026-10-05 H-E-B milk and Home
Depot filter check.

props:  question · answer (the figure or finding, as he read it) · asked_of (web | store | ynab
        | vault) · period (from/to, when the question covers a span) · sources (list of URLs)
        · checked_at · the structured detail beside answer, named for what it is
enrich: spell out what "this month", "this week" or "my store" meant, as dates and as the place
        or budget consulted, so the figure can be read again later.
ask:    "what did I ask, and what was the answer at the time"; whether a figure has been
        looked up before, and what it was then.
notes:  the answer is kept so a later figure can be compared with it, never so the question can
        be answered from the record — a question asked again is looked up again. A money
        question is answered from YNAB only (jobs/ynab.md); a price or stock question from the
        store itself.

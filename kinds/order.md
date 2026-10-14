# order

An order placed with a store. Born 2026-10-13 with the first order the agent placed: the
Nike All-Field 4.0 youth football on Amazon, after he said "go ahead and order that football".

props:  retailer (amazon | walmart | heb | homedepot) · status (placing | placed | abandoned |
        rehearsed) · order_number · items (list of {name, qty, price}) · expected_total (before
        the button) · total (what this change spent, set only once placed) · delivery (date, or
        the window for InHome) · how (auto | approved | asked) · url · proposal (the proposal it
        buys, if any) · for an addition to a booked order: adds_to, qty_before, and order_total
        (the order's new total)
enrich: nothing invented; the store's own summary page is the source.
ask:    "what did I order this week"; spend per store per month; the last time he bought X.
notes:  `total` is what this record spent — the whole order, or only what an addition added —
        and exists only on a placed record, so a month's spending is the sum of totals over
        status placed; a placing record carries only expected_total. The order's new total
        after an addition is order_total. A record with practice: true spent nothing and is
        never history or spending. `how` is auto when the buy rule allowed it, approved when he
        said yes to a proposal, asked when he told the agent to check out. Filed as placing
        before the button and completed as placed after it, so a run repeated on the same note
        checks the store before buying again.

        Amazon's Buy Now is the way to order one item out of a shared cart without checking the
        whole cart out; it also takes that item's line out of the cart. Amazon checkout may
        auto-apply his Prime Visa rewards points, which pays the order to $0.00 on the card: the
        payment is not changed either way, and the record carries `charged` beside `total` and no
        YNAB entry, because no bank charge will ever arrive to match one.

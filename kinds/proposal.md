# proposal
Something the agent would buy, waiting for his yes. Born 2026-10-13 from "Find me a
gerbil water bottle on Amazon that's not too tall."

props:  retailer (amazon | walmart | heb | homedepot) · item · url · price · qty · total
        · seller (Amazon: who sells it, and its rating) · why (the reason for this pick)
        · weighed (the alternatives and why not) · revised_by (the note that last changed
        its price or item, which cannot approve it) · closed (why it ended, when it
        ended without a yes or a no)
enrich: nothing. Open until he answers; done when bought, deleted when declined.
ask:    "what's waiting for me to approve".
notes:  filed whenever a buy is not an automatic one — a first purchase, a choice between
        versions, research, a price that jumped, anything past his limits. The reply ends
        with how to say yes.

        **He often answers by buying it himself, and that closes the proposal.** Three
        of the first four went that way: the gerbil bottle (he ordered the Kaytee glass
        one, Oct 14), the travel food scale (the MAXUS, Oct 19) and the AMS desiccant
        (the 16-pack, Oct 19) — each time one of the alternatives that had been weighed
        beside the pick, bought within a day or two and never mentioned again. So when
        his order history shows he has bought the thing the proposal was about, the
        question is settled: `update --done` with a `closed` prop saying what he bought
        and that it was not a yes or a no, rather than leaving the row open forever.
        The agent's pick usually stays in his cart; that is not a sign he still wants it.

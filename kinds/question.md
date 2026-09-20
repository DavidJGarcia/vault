# question

Something he asks that is answered from the world rather than from his own records: a
fact, a time, a price, how a thing is done. Born September 20, 2026 from "Is there free
Wi-Fi on United Airlines?" Three earlier asks had been carrying `type: question` in their
props untyped since September 18, so the kind was born here and those rows, with the two
condenser-coil asks, were re-filed under it.

Not for a question answered by summing his own rows: that is `nutrition_check`.

props:  asked (the question as read) - topic - answer (the short answer he was given) -
        details (whatever else the answer turned on) - reading (what the question was
        taken to mean, when it needed reading) - repeat_of (record id, when he has asked
        it before) - vault (file the answer was written to, when it was) - sources (list
        of URLs) - searches (number) - assumed (list)

enrich: read the question against what else is going on that day - an open trip, a game
        tonight, something he bought an hour ago - and say on the wrist what you read it
        as. Answer first, caveat second. When the answer is worth looking up again later,
        write it in the vault where he would look for it and name that file in props.

ask:    "what did I ask about X"; "have I asked this before"; what the answer was and
        where it came from.

notes:  he asks in one short sentence with no context, and the context is almost always
        something else he said that day. A question asked twice earns a vault page: the
        condenser coils came back a day later.

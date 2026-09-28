# route_time

A route timed end to end, with which way he went at the fork. Born September 28, 2026
from "We went right and it took us 5 minutes and 20 seconds", the second of its sort
after the left run of September 15, 2026.

props:  direction (string: left, right - the way taken) · duration_s (int, seconds) ·
        duration (string, m:ss as he said it) · route (string: which drive is being
        timed, when he says; null when he has not) · with_others (bool: he says "we")

enrich: read m:ss into duration_s; carry the route from the previous timed run when he
        does not name one; compare against the other direction's runs already stored and
        put the difference on the wrist, since that is the whole point of timing it.

ask:    "which way is faster"; every run per direction, and the spread between them.

notes:  he says the direction and the time and nothing else. Both runs so far are just
        after 07:10 on a weekday morning, and he says "we", so it reads as a morning
        drive with someone. Where it goes he has never said - do not invent it. Each run
        is its own row: two runs of the same direction are two times, not a correction.

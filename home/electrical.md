# Electrical

House wiring questions and the answers given, so the same one is not worked out twice.

## The GFCI outlet

Asked October 21, 2026 and twice on the morning of October 24, 2026. The to-do
"Swap out GFCI outlet" was ticked done October 4, 2026.

**The symptom.** The new GFCI's face reads green but the receptacle powers nothing.

**The cause.** Line and load are reversed: the incoming feed from the panel was
landed on the LOAD terminals. The green light only means the device's own sensing
circuit has power — it does not mean the contacts are energized, and most newer
self-testing GFCIs deliberately refuse to pass power, and refuse to latch on
RESET, when they see reversed line/load.

**The fix — the whole cable pair moves, not one wire.**

- Incoming feed: black to LINE brass, white to LINE silver.
- Downstream run (if any): black to LOAD brass, white to LOAD silver.
- LINE and LOAD are at opposite ends of the device; LOAD usually sits under a
  yellow or orange factory tape label.

Never put one cable's black on LINE and its white on LOAD. A GFCI compares the
current going out on a hot against the current coming back on the neutral of the
same pair; cross a white between feed and load and it reads that as a fault, so it
trips at once or never latches. A crossed neutral can also backfeed the
downstream run.

**Which pair is the feed.** Breaker off, everything capped, breaker back on: the
pair that reads hot is the feed. Or trace the cable entering from the panel side
of the box. Neither needs a meter beyond a basic tester.

**Order of work.** Breaker off · move the wires · breaker on · press RESET until
it clicks and stays in.

**If the feed is on LINE and it still will not reset.** A loose or open neutral, a
pigtail not made up, or a dead unit — self-testing GFCIs do fail at install. To
tell the device from the downstream run: power off, cap the LOAD wires, power
back on. If the face now works, the fault is downstream.

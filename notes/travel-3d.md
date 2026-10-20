# Travel time splits, in 3D

Built Tuesday, October 20, 2026, from "Build me an interactive 3D graph of our travel time
splits where y is the length of travel time, direction we went is color-coded, x is
clustering by the time that we started, and z is clustering by day of the week."

The data is the ten `route_time` records - every run timed between Tuesday September 15 and
Tuesday October 20, 2026, and nothing from anywhere else. Rebuild it from
`records --kind route_time` when there are more.

## How to open it

The vault is Markdown only, so the graph lives here as its source. Copy the block under
**The file** at the bottom, save it as `travel-3d.html`, and open it in any browser. It
loads Plotly from a CDN, so it wants an internet connection the first time; it needs
nothing else, and no data leaves the file.

Drag to rotate, scroll to zoom, hover a point for its date and its times. The legend
switches a direction off. The drop lines (on by default) run from each point down to the
floor, which is what makes a 3D scatter readable - without them you cannot tell how far
back a point sits. The same ten runs are under the graph as a table, so nothing is
reachable only by hovering.

## The axes

| Axis | What it carries |
|---|---|
| **y**, vertical | the drive itself, 4:00 at the floor to 11:00 at the top |
| **colour** | the way taken at the fork: left is blue circles, right is orange diamonds |
| **x**, across | the time the drive started, 07:05 to 07:14 |
| **z**, into the screen | the day of the week, Monday to Friday |

Your y is drawn vertical and your z into the screen, which is how the letters read on a 2D
chart even though a 3D plotting library calls the vertical axis z. Friday is on the axis
and empty: you have never timed one.

**The start time is derived, and you never said it.** Each note gives the direction and the
length, and the ring stamps the moment you spoke, which is just after you arrived. So the
start is that stamp minus the drive. It is right to the second if you spoke as you pulled
up, and a little early if you waited a moment first. Everything below about start times
rests on that.

## The ten runs

| Date | Day | Started | Drive | Way | Start cluster |
|---|---|---|---|---|---|
| Sep 15 | Tue | 07:06:32 | 5:45 | left | early |
| Sep 28 | Mon | 07:08:03 | 5:20 | right | early |
| Sep 29 | Tue | 07:06:32 | 6:13 | left | early |
| Oct 1 | Thu | 07:05:51 | 7:22 | right | early |
| Oct 5 | Mon | 07:11:45 | 8:44 | left | late |
| Oct 6 | Tue | 07:07:56 | 6:02 | right | early |
| Oct 7 | Wed | 07:07:45 | 4:00 | left | early |
| Oct 8 | Thu | 07:06:38 | 5:53 | right | early |
| Oct 19 | Mon | 07:12:48 | 11:00 | left | late |
| Oct 20 | Tue | 07:09:52 | 5:22 | right | middle |

The clusters are the gaps in the start times, not round numbers: seven runs start between
07:05:51 and 07:08:03, then a gap of 1m 49s to Oct 20 alone at 07:09:52, then a gap of
1m 53s to the two late ones, 07:11:45 and 07:12:48.

## What the graph shows

**Start time is the strongest thing in it.** The early cluster averages 5:48, Oct 20 alone
is 5:22, and the two late starts average 9:52. Four extra minutes of drive for four extra
minutes in the house. As a correlation across all ten it is r = 0.68, which sounds firmer
than it is: drop Oct 19 and it falls to r = 0.34, so two mornings are carrying most of it.
Two more late starts would settle it either way.

**And it changes the answer to which way is faster.** On the raw averages right leads, 6:00
over five runs against 7:08 for left. But both late starts were left turns, and both were
Mondays. Hold the start time still and it reverses:

| | left | right |
|---|---|---|
| early starts, before 07:09 | **5:19** over 3 | 6:09 over 4 |
| late starts | 9:52 over 2 | never |
| all runs | 7:08 over 5 | 6:00 over 5 |

Left owns the fastest run on record (4:00, Oct 7) and both of the slowest (8:44 and 11:00).
Right has never been worse than 7:22 and never better than 5:20: it is the steadier way,
and on the evidence here it is not the faster one. The `vs_other_direction` note on each
`route_time` record compares raw averages and so says the opposite; this is the same data
with the late mornings separated out.

**Day of week is mostly those same two mornings again.** Monday averages 8:21 over three,
Tuesday 5:51 over four, Wednesday 4:00 over one, Thursday 6:38 over two. But two of the
three Mondays are the two late starts, and the third Monday, Sep 28 started at 07:08, was
5:20, the second-fastest run on record. So Monday is not slow; leaving at 07:12 on a Monday
is. Nothing has ever been timed on a Friday.

**What would settle it:** a left run and a right run started inside the same minute, and a
late-start right turn. Right has never once started after 07:09:52, so the two directions
have never been compared on equal footing.

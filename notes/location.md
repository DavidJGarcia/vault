# Making Index aware of where I am

How an iPhone tells the worker where David is. Written Friday, November 13, 2026, answering
"I'd like to know how to make you aware of my location so that you can do things based on my
location (such as at home or at the office)."

## The short answer

Nothing has to be built. The relay already takes a capture from anything that can make an
HTTPS POST, and iOS Shortcuts can make one when the phone crosses a geofence. Arriving at the
office posts a note that reads "Arrived at the office"; the worker files it exactly like a
spoken note, and the newest such record is where he is.

## The endpoint that already exists

`POST https://project-index.azurewebsites.net/pebble`

- Header `Authorization: Bearer <ring token>` - the `WEBHOOK_TOKEN` app setting on the
  production app in the Azure portal. The same token the ring uses, so there is no new secret
  and nothing to deploy.
- Body, `Content-Type: application/json`:

```
{"transcription": "Arrived at the office",
 "recordedAt": "2026-11-13T14:13:53-06:00",
 "client": "shortcut"}
```

`transcription` becomes the event's text, `recordedAt` becomes `spoken_at` (epoch
milliseconds or an ISO string, both are read), `client` is free text. Confirmed against
`index/capture.py` and `index/api.py` on November 13, 2026: a ring-token POST carrying those
fields raises a normal `capture` event with `source: ring`.

## The automations to create

On the iPhone: Shortcuts - Automation - "+" - **Arrive** or **Leave**.

1. Pick the place (Home, Work) and leave the time range and days open.
2. Turn **Run Immediately** on and **Notify When Run** off, so nothing has to be tapped.
3. One action, **Get Contents of URL**: the URL above, Method POST, the one header, and
   Request Body set to JSON with the three fields.

Four of them covers home and office: arrive home, leave home, arrive office, leave office.
Word each one the way he would say it out loud, because that text is the whole of what the
worker reads: "Arrived at the office", "Left home".

## What it costs

Every capture is acknowledged on the wrist with the `Index · Heard` buzz, so each crossing
buzzes him - roughly four a day. There is no quiet capture today. If that grates, the fix is
a small relay change: a `/location` path that stores a position without acknowledging it. That
is an item for the coding-agent prompt at the foot of a weekly pass, not something to do by
hand.

Geofences are also approximate: iOS fires them a few hundred metres out, sometimes minutes
late, and occasionally not at all until the phone wakes. Good enough for "he is at the
office"; not good enough for anything that must be exact.

## What it buys

- `place` on a meal row read rather than assumed from the hour.
- "Remind me when I get home" - a reminder that waits on an arrival instead of a clock.
- Commute times filed on their own, as `route_time` rows.
- The morning briefing knowing whether the day starts at home or at the office.

## Coordinates, if they are wanted

The same Shortcut can add **Get Current Location** and put the latitude and longitude in the
text - "Arrived at the office (30.34, -97.56)" - which makes the place verifiable rather than
asserted. Not needed for home and office; useful if location ever has to drive something
finer.

## Other routes, and why not

- **OwnTracks or Overland**, which post position continuously over HTTP: gives a position
  every few minutes instead of at crossings, but needs a relay endpoint built to receive it
  and costs battery. More than the question asks for.
- **Find My / iCloud**: no API anything else can read. Dead end.
- **Just saying it** - "I'm at the office" - works today with no setup at all, and is what has
  been happening implicitly. The Shortcut only saves him the sentence.

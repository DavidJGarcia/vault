# The talking briefing

The plan for the morning out loud. Asked for Thursday October 22, 2026, from "Give me a
doc in my vault with the project plan for the talking version of the morning." Nothing is
built yet; this is the order to build it in, and what would prove each step wrong.

## What exists today

The 05:35 job row fires the briefing, the worker composes the morning on the desktop and
sends it as one or more Pushover messages, about seven rows of twenty characters each, and
writes the same text as the view at /notes/views/brief. That is the whole of it. There is
no audio anywhere in the system.

It has been asked about once before. On September 14, 2026 the question was long audio
replies in general, and four delivery paths were researched: an outbound Twilio call read
aloud over auto-answer, a private podcast feed, chunked notifications read by Siri's
Announce Notifications, and a custom iPhone app. The recommendation then was the call.
Nothing was built, and the morning is a better first use than a reply is, because the
morning is the one message already too long for the wrist.

What is available to play it: the iPhone, the car over Bluetooth, the Alexa in the kitchen.
Not the watch. Connect IQ cannot play arbitrary audio, and the 265S takes music only from
Garmin's own providers.

## The one design decision

The talking brief is a second composition, not the wrist text read aloud. Everything that
makes the wrist message good makes it bad speech: twenty-character rows, labels with
colons, "Thu: Emily's bday", a list of names with no verb in it. Speech wants whole
sentences, numbers said as words, and no labels at all. Roughly 45 to 75 seconds, which is
700 to 1,100 characters at normal reading speed.

So the briefing job composes both in the same run, from the same facts: the wrist message
it already sends, and a spoken script written to be heard once. The script lands as its own
view, brief_spoken, which keeps the rule that the relay never composes.

## Who renders the audio

The worker, not the relay. The relay makes no model calls and holds no AI credential, and
the briefing already depends on the desktop being awake: when it is off, the relay says so
rather than inventing a morning. So the worker renders the MP3 and uploads the bytes, and
the relay stores and serves them, which is the boring half it is good at.

That needs one new pair of relay paths, PUT /audio/<name> and GET /audio/<name>.mp3, the
first binary the relay has ever served.

Voice: Azure AI Speech neural text-to-speech, in the same subscription the relay already
runs in. Sixteen dollars per million characters, with a free tier of 500,000 characters a
month. A 1,200-character brief every day is about 36,000 characters a month, inside the
free tier fourteen times over. If the Azure voice grates after a week, ElevenLabs is the
upgrade, and that one is a monthly subscription rather than pennies.

## The trap: authentication

App Service authentication fronts the app with a redirect to a login page and an
excluded-path allowlist, and a path outside that list never reaches Python. Nothing that
plays audio can sign in to Entra: not a podcast app, not Alexa, not a Shortcut running
while the phone is locked. So the audio paths go on the allowlist and carry an unguessable
token in the URL, and that token is the whole of their security. Update both apps at once
and record the new list in provision.json.

## The phases

### Phase 1 - the phone reads the script. One evening, no cost.

No audio file and no text-to-speech at all. The briefing job writes brief_spoken beside
brief; an iOS Shortcut set as a Time of Day automation at 05:40 fetches that text from the
relay and runs Speak Text, with "Run Immediately" chosen and "Allow Running When Locked"
on. Siri's voice, off the nightstand.

Proves the only thing that matters, whether hearing the morning beats reading it, for the
price of one evening and nothing a month. Falsifies: if you reach for the watch anyway, or
find yourself waiting through sentences you had already read, the project stops here having
cost an evening.

One thing to confirm on the device first. Speak Text is documented to work from a locked
automation, but some actions do not run locked. Test that before building on it.

### Phase 2 - real audio on the relay

The worker renders the script to MP3 and uploads it; the new GET serves it. Every player
becomes available at once: the Shortcut plays the file instead of speaking it, the car
plays it over Bluetooth, and a one-item RSS feed at the same prefix makes it a private
podcast, which Overcast, Pocket Casts and Apple Podcasts all subscribe to by URL.

Proves a real voice is worth the step up from Siri's. Falsifies: if you never press play,
pulling is the wrong model and only the pushed versions, phases 1 and 4, can work.

### Phase 3 - Alexa in the kitchen

"Alexa, what's my flash briefing." A Flash Briefing skill takes the RSS or JSON feed built
in phase 2, polls it every fifteen minutes, and expects an endpoint that is not password
protected, which the capability URL technically is not. That is the compromise to accept
knowingly or to decline. Most of the work is already done by then.

Falsifies: if asking for it out loud is more friction than picking up the phone that is
already in your hand.

### Phase 4 - it calls you. Last, and maybe never.

The September recommendation: the relay places a Twilio call that reads the brief, and the
iPhone auto-answers it to the headphones. About $1.15 a month for the number plus about
1.4 cents a minute. It is the only version that is genuinely pushed, with nothing to press.
The costs are real: auto-answer applies to every caller, not just this one, and a call
takes over the audio and interrupts. Keep it behind the other three, as the answer to
"having to press play killed it".

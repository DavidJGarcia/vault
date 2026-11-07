# Features worth building into Index

Asked Saturday November 7, 2026: "What cool features could I add to you that would
be fun or useful?" The sibling of `notes/index-gaps.md`, asked the same morning,
which is about using what already works. This one is about new capability - things
that need a build, a connector or a setting, not a habit.

Ranked by what it gives back for what it costs. Nothing here is built.

## The four worth doing first

### 1. Read your calendar

`notes/work-calendar-access.md` (October 21, 2026) already worked out three ways to
read your work Outlook calendar read-only, and nothing was built. Right now
`dates.md` is hand-kept and the briefing cannot say what your day holds - the one
thing a morning briefing most obviously should.

Unlocks: the day's meetings in the briefing, a conflict named before you hit it,
drive time to the first thing that is not at home, and "am I free Thursday night"
answered instead of guessed. A to-do due Friday could be placed against an actually
free hour.

Cost: a Microsoft Graph app registration and a token this worker can refresh. A
build, not a setting.

### 2. A feed from the Garmin

The 265S already records sleep, resting heart rate, HRV, steps, and every gym
session set by set. All of it is dictated by voice today - 203 `exercise_set` rows
spoken aloud - or not captured at all, which is the case for everything that is not
food or the gym.

Unlocks: sets logged without saying them, so the gym view builds itself; sleep and
resting HR beside the weight trend, which is where they actually mean something;
"you slept 5h and your resting HR is up 6" on a morning the briefing would
otherwise be blind to.

Cost: Garmin Connect has no clean personal API. The realistic paths are the Health
API (a developer agreement), a third-party exporter on a schedule, or Apple Health
on the iPhone exported nightly. Worth one afternoon of research before picking.

### 3. Let a photo be a capture

The capture event already carries a `files` list and it is always empty. One photo
would end the biggest guessing game in here.

Unlocks: a nutrition label or a barcode photographed instead of described, so the
calorie count stops being an estimate; a paper receipt split into YNAB lines; the
part number on a failing thing read off the sticker; the fridge shelf answering
what is actually in the house.

Cost: a way to get a photo from the phone to the relay, and the ring is not it.
Probably a shortcut on the iPhone or an inbox the relay watches.

### 4. Audio replies

The wrist is capped at 256 characters and seven rows, which is why a long answer
arrives as three messages written backwards. You asked about this twice in
September.

Unlocks: a spoken morning briefing on the drive, a long answer heard instead of
scrolled, and the 256-character ceiling stops shaping what can be said.

Cost: text-to-speech plus somewhere to put the file and something on the phone that
will play it. The awkward part is playback, not the speech.

## Three more, each genuinely useful

- **Location, with geofences.** You asked about this in September. "Remind me when I
  get to H-E-B" instead of at a time; the briefing knowing whether you are home;
  drive times computed rather than estimated. Cost is an iPhone shortcut posting
  arrivals, not continuous tracking.
- **An inbox the worker can read.** Forward order confirmations, receipts and
  shipping mail to one address. The weekly pass currently clicks through Walmart and
  Amazon order history to memo your charges; the confirmation email says the same
  thing in a form that needs no browser.
- **A pantry model.** Your meal rows are highly predictable - oats, blueberries,
  protein powder most mornings - and your Walmart orders say what came in the house
  and when. Subtract one from the other and the grocery list writes itself, and says
  "you run out of blueberries Tuesday" before you notice.

## The fun ones

- **A bedtime story a night**, built from the kids' own names and whatever they are
  into this month, delivered as text or audio. The people files already hold the
  material.
- **The chore rotation, read back.** `home/chores.md` exists and the trash-and-litter
  turns are already spoken; whose turn it is could be asked by voice and answered
  without anyone arguing.
- **A "when did I last" ledger that prompts.** Two rows exist (litter, nail trims)
  and the litter rule proves the pattern. Air filter, fridge filter, oil change, AC
  service, softener salt: each costs four words once and then answers forever.
- **The talking horn**, which is the one build already planned end to end
  (`notes/talking-horn.md`) and sitting at phase 0.

## Rejected, with the reason

- A second assistant beside this one. Hark was researched October 7, 2026
  (`notes/hark.md`): no API, so nothing it did would land in these records.
- Anything that writes to a store or a budget without asking. The rules in
  `jobs/shopping.md` and `jobs/ynab.md` are deliberate and none of the above
  loosens them.

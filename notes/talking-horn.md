# The talking horn

The plan for a second horn that says the light is green. Asked for Thursday October 22,
2026, from "Can you put a plan together for that?" - the horn asked about at 07:06 and
07:09 that same morning, not the briefing. Nothing is built yet; this is the order to build
it in, and what would prove each step wrong.

## What it is

A second, quieter horn on its own button whose only job is to tell the car ahead that the
light has turned green. The stock horn stays exactly as it is and keeps its own button: it
is the statutory warning device, and nothing in this plan touches it.

## What exists today

Nothing to buy. The idea is patented twice as a courtesy horn (US12043173B2, US10005388B1)
and nobody sells a module that speaks. The precedent is DIY: an ex-NASA engineer wired
three honks into a VW Jetta, the politest of them a pair of quick quiet chirps for exactly
this situation. Generic second-horn hardware - horn, relay, socket, button, fuse - is off
the shelf and cheap.

## The one design decision

The chirp is the project and the voice is a layer on top of it. Both builds are the same
circuit: a momentary button pulling a control leg to ground, and a sound-maker behind the
grille. Build the chirp first and the speaking version changes what the button fires, not
how it is wired - the button, the ground run, the fused feed and the hole in the grille are
all reused. That is why phase 2 is cheap after phase 1 and would be expensive before it.

## The law, which sets the shape

Texas Transportation Code 547.501: the car must have a horn audible at 200 feet; a warning
device may not emit an unreasonably loud or harsh sound or a whistle; sirens, whistles and
bells are barred outside authorized emergency vehicles; and the horn is for an audible
warning when it is needed for safe operation. A second, softer device beside a compliant
stock horn is not banned anywhere in it. A loudspeaker that says words is not named either
way, so it falls to an officer's judgment of harsh or unreasonable - which is the part to
be careful with.

Underneath the state code, Texas cities regulate sound amplification in vehicles by
plainly-audible distance, commonly 50 feet and sometimes 100. Manor's own chapter has not
been read yet (below). Three design rules come out of all of this and none of them cost
anything:

- Aimed forward, at the car in front, and quieter than the stock horn.
- Short. One or two seconds. The continued or frequent sounding of a loudspeaker is what
  the city ordinances actually prohibit.
- Whatever siren tones come in a vehicle PA kit stay unused, permanently. They are the one
  thing 547.501 names outright.

## The phases

### Phase 0 - decide the line, with a phone. One evening, nothing.

No wiring. Record the line on the phone, play it from a speaker on the dash at two or three
lights this week, and see whether a voice is actually better than two soft chirps would be.
The candidate line is "Light's green" - two words, under a second, and it reads as help
rather than complaint. Anything longer than three words is longer than the moment.

Proves the only thing that matters before any money is spent, which is whether the talking
version is the one you want. Falsifies: if you would rather have tapped the horn, or the
sentence runs past the gap you had, the project is phase 1 and stops there.

### Phase 1 - the polite chirp. About $50, one afternoon.

A quiet second horn on its own momentary button, with the stock horn untouched. Disconnect
the battery negative first.

- 12V low-tone or courtesy horn, mounted behind the grille.
- Standard 4-pin 30A automotive relay with socket: pin 30 to battery positive through a 15A
  inline fuse, pin 87 to the horn, pin 86 to the button, pin 85 to chassis ground.
- Momentary push button on the column or the dash.
- 16-14 AWG wire, crimp terminals, a ring terminal for the ground.

Two taps of the button is the polite double chirp. Proves the circuit, the mounting and the
button position, all of which phase 2 inherits. Falsifies: if the chirp alone gets the car
in front moving, the project is finished at fifty dollars and phase 2 is a toy - which is
the good outcome, not the disappointing one.

### Phase 2 - it speaks. About $60 to $110 on top, a second afternoon.

The same button, now also pulling a trigger pin to ground on a stand-alone sound board.

- Adafruit Audio FX Sound Board with 2x2W amp, 16MB (around $25): no microcontroller at
  all, 3-5.5V in, and a named WAV plays when its trigger pin touches ground. The 2x2W Class
  D amp drives a 4-8 ohm speaker directly.
- 12V-to-5V buck converter to feed it.
- A 4-8 ohm weatherproof driver behind the grille, facing forward.
- If 2W is not intelligible: a 12V 30W vehicle PA kit with an IPX6 horn speaker, with the
  sound board on its line in and the microphone and siren functions left alone. Those kits
  run about $60 to $100.

The falsification test is intelligibility, not volume: can the driver ahead make out the
words at twenty to thirty feet with their windows up and their radio on. That is the test
this build can genuinely fail - a 2W driver behind a grille may be a mumble, and a 30W horn
speaker loud enough to be clear may be louder than the stock horn, which defeats the point.
If it fails at both 2W and 30W, the answer was the chirp.

### Phase 3 - a second message. Optional, and only if phase 2 is a success.

The sound board has several trigger pins, so a second button is a second line: "thank you"
for the car that let you in is the one worth having. Costs a button and a WAV file.

## Rejected, with the reason

- Replacing the stock horn with a talking one. It leaves the car without a compliant
  warning device, which is the one thing 547.501 is unambiguous about.
- Driving the voice from the factory horn button. Then there is no real horn when a real
  horn is needed, and you cannot chirp politely and warn loudly with the same press. The
  separate button is the whole design.
- Using the siren tones in a PA kit, even once. See the law above.
- Bluetooth from the phone instead of a sound board. Pairing, latency and the phone's
  attention, for a thing that has to work in under a second with nothing in your hand.
- Loud. The point is that it is quieter than the horn. If it carries fifty feet behind the
  car it is both the wrong build and a city ordinance problem.

## Still open

- Which car. Nothing in the vault records it. The relay wiring is identical on any 12V
  vehicle, but grille space, where the factory horn sits and which feed to tap are not -
  name the car and this plan can name the wire.
- Whose voice says it. Yours is the obvious one; one of the kids saying "light's green" is
  the version that probably never gets annoying.
- Manor's city code on vehicle sound amplification, which has not been read. Ten minutes
  before a speaker gets mounted, and it sets the volume ceiling.
- Where the button goes: column, dash, or something reachable without looking.

## Checked

- Texas Transportation Code 547.501: https://codes.findlaw.com/tx/transportation-code/transp-sect-547-501/
- Second-horn relay wiring: https://engineerfix.com/how-to-install-a-car-horn-and-relay-system/
- Adafruit Audio FX Sound Board + 2x2W amp: https://www.adafruit.com/product/2217
- Its trigger-pin behaviour: https://learn.adafruit.com/adafruit-audio-fx-sound-board/overview
- 12V 30W vehicle PA with IPX6 horn speakers: https://www.audiovolt.co.uk/products/12v-30w-vehicle-pa-system
- Vehicle sound amplification by plainly-audible distance, as Texas cities write it: https://codelibrary.amlegal.com/codes/texascity/latest/texascity_tx/0-0-0-3037
- The patented courtesy horn: https://patents.google.com/patent/US12043173

The two questions this came from, with the full legal reading and the DIY precedent, are in
the records of October 22, 2026.

# Raising average HRV

Asked November 9, 2026: "If I want my average HRV to increase 50-100% over an
extended period of time and I already have decent baseline health and habits,
what would I work on?"

## First, the honest framing

A 50-100% rise in average HRV is a large number. HRV is set mostly by age,
genetics and aerobic fitness, and for someone already sleeping, eating and
training reasonably, 10-30% over six to twelve months is a strong result.

The people who do post 50-100% are almost always starting from a *suppressed*
baseline - nightly alcohol, 6 hours of sleep, no aerobic base, untreated sleep
apnoea, a chronic calorie deficit, or months of overreaching. So the route to a
number that big is not stacking more good habits on top of good habits. It is
finding the one suppressor still in place and removing it. Items 1, 3, 5 and 7
below are the ones that can move a baseline that far on their own.

Measured as a 7-day rolling average of the overnight reading from the Garmin
Forerunner 265S. Night-to-night swings of 30-50% are normal noise and mean
nothing.

## The list, strongest first

1. **Build an aerobic base.** Regular aerobic training is the single largest
   modifiable influence on HRV in the meta-analytic literature - bigger than any
   supplement, breathing practice or sleep tweak. 30-45 min at 60-75% of max HR
   (zone 2), 4-5 times a week, for months, with one harder interval session
   folded in later. **This is his biggest structural gap**: all 203 of his
   `exercise_set` rows since September 14, 2026 are resistance machines on a
   four-day split, and nothing on record is cardio. Lifting alone does very
   little for vagal tone.

2. **Slow-paced breathing, daily.** 6 breaths a minute (about 4 s in, 6 s out),
   10-20 min a day. The best-documented deliberate trainer of vagal tone: it
   raises HRV acutely during the session and raises resting HRV over weeks of
   practice. One 8-week trial put resting RMSSD up 5.5 ms over control. Needs no
   device, only a paced metronome. Resonance-frequency breathing (finding his own
   rate, usually 4.5-6.5/min) is a refinement, not a prerequisite.

3. **Alcohol to zero.** The largest single-night suppressor there is. Pooled
   wearable data across ~21,000 people and 5M nights: each additional drink costs
   3-4 ms of overnight HRV and adds ~2.4 bpm to sleeping heart rate; two or three
   drinks takes 20-30% off the night, and the hit lasts into a second night. If
   he drinks at all, this is free percentage points.

4. **Sleep regularity before sleep duration.** 7.5-8.5 hours, but the variable
   that moves overnight HRV most is the *consistency* of bed and wake times -
   same window within about 30 minutes, including weekends. Irregular timing
   depresses the overnight reading even when total hours look fine.

5. **Rule out sleep apnoea and mouth breathing.** This is the classic cause of
   "good habits, bad HRV", and the one item that can produce a 50-100% jump by
   itself. Untreated mild apnoea flattens overnight HRV all night. Worth a home
   test if there is snoring, dry mouth on waking, or morning headaches. Nasal
   breathing at night (and during zone 2) helps even without apnoea.

6. **Last food 3 hours before bed; last caffeine 8-10 hours before bed.**
   Digestion during sleep raises sleeping heart rate and takes a visible bite out
   of overnight HRV. Caffeine's half-life is ~5 hours, so an afternoon coffee is
   still circulating at bedtime and suppresses HRV even when sleep onset feels
   normal.

7. **Come off the calorie deficit for a block.** He has been running 1,600-1,700
   kcal with a 140 g protein target and losing ~1.6 lb/week at 141 lb and BMI
   23.2. A sustained deficit plus four lifting days is a sympathetic load, and
   energy deficit reliably depresses HRV. Eating at maintenance for 8-12 weeks
   lifts it. **The weight-loss goal and the HRV goal are competing**, and at BMI
   23 there is nothing left to gain from leanness on the HRV side.

8. **Manage training load, don't just add to it.** A hard session the evening
   before suppresses that night's reading. Move hard work earlier in the day,
   keep one genuinely easy day, and autoregulate - the 265S reports an HRV status
   band, and the rule is to back off when it drops out of range rather than to
   push through. Chronic overreaching is a common reason a fit person's HRV
   stalls or falls.

9. **Sauna.** 15-20 min at 175-195F, 3-4 times a week, after training. Decent
   evidence for improved vagal tone and baroreflex sensitivity, and it stacks
   with the aerobic work rather than competing with it.

10. **Omega-3, 2 g/day EPA+DHA.** One of the few supplements with randomised
    evidence for raising HRV specifically - trials show higher RMSSD and SDNN,
    and a 48% rise in high-frequency power in one cardiac population. Then
    magnesium (glycinate, at night) only if his intake runs short, which his own
    `nutrition_check` rows can answer.

11. **Lower resting heart rate is the proxy to watch.** Resting HR and HRV move
    inversely and resting HR is the less noisy of the two. If the 265S shows
    resting HR drifting down over months, HRV is following, whatever a given
    night says.

12. **Measurement hygiene.** Same device, same wrist, same strap tightness, and
    compare 7-day averages to 7-day averages. Changing watch or fit mid-project
    will manufacture a 20% "change" out of nothing.

## What is not on the list

Cold plunges (acute spike, no durable resting-HRV evidence), vagus-nerve
stimulators and tDCS gadgets, grounding mats, breathwork of the
hyperventilation kind (Wim Hof - sympathetic, not vagal), and chasing a lower
body-fat percentage.

## Sources

- https://pmc.ncbi.nlm.nih.gov/articles/PMC13381940/ - resonance vs fixed 0.1 Hz breathing, 4-week RCT
- https://www.ncbi.nlm.nih.gov/pmc/articles/PMC8924557/ - resonance breathing RCT, young adults
- https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5575449/ - resonance frequency breathing, HRV and BP
- https://www.whoop.com/us/en/thelocker/what-happens-when-you-give-dry-a-try-how-reducing-alcohol-consumption-affects-physiology/ - alcohol and overnight HRV
- https://www.mensjournal.com/health/new-wearable-data-reveals-the-scary-truth-about-your-overnight-recovery-after-a-night-of-drinking - the 21,000-member PLOS Digital Health analysis
- https://pmc.ncbi.nlm.nih.gov/articles/PMC13010831/ - omega-3 and HRV, review of RCTs
- https://www.nature.com/articles/s41598-023-38344-x - omega-3 and vitamin D RCT, RMSSD and PR interval
- https://www.ajconline.org/article/S0002-9149(06)00029-4/fulltext - omega-3, HF power +48%
- https://pmc.ncbi.nlm.nih.gov/articles/PMC12082064/ - review, HRV biofeedback as non-invasive vagal neuromodulation

## November 9, 2026 - more on items 2, 9 and 10

Asked an hour after the list: "On the HRV topic tell me more about the 6 breaths
and the 15 breaths. Line about the sauna and the mega 3."

### Item 2, the breathing: 6 is the rate, 15 is the minutes

The wrist row read "6 breaths/min 15m". The 15 is minutes, not breaths.

- **6 breaths a minute is the pace** - one breath every 10 seconds, about 4 s in
  through the nose and 6 s out. Ordinary resting breathing is 12-16 a minute, so
  this is half speed, and it feels slow for the first week.
- **15 minutes is the dose**, the middle of the 10-20 min a day the trials use.
  Once a day is enough; twice is better only if it is easy to fit.
- **Why 6 and not 5 or 10.** At about 0.1 Hz - six breaths a minute - breathing,
  blood pressure and heart rate line up with the baroreflex loop, and the
  beat-to-beat swing in heart rate is at its largest for the least effort. That
  is the resonance frequency. Each person's own sits between 4.5 and 6.5 a
  minute; 6 is the default that suits nearly everyone, and hunting for his exact
  rate is worth nothing until the habit is in place.
- **Slow, not big.** Exhale longer than inhale, breathe low into the belly, and
  do not try to fill the lungs - over-breathing blows off CO2 and brings
  lightheadedness, which is the usual reason people quit in week one.
- **His own watch paces it.** The Forerunner 265S has a Breathwork activity, and
  its *Coherence* pattern is 6 s in, 6 s out - 5 breaths a minute, inside the
  resonance band - with a vibration cue on each phase, so it can be done with
  eyes shut and no app or gadget to buy. The watch reports breaths per minute
  and the stress change afterwards.
- The in-session rise in HRV is immediate and is not the point. The change in
  *resting* HRV shows up after four to ten weeks of daily practice.

### Item 9, the sauna: it moves down the list, out of the HRV column

The best test of exactly this protocol came out negative, and it is newer than
the evidence item 9 was written from. A 2025 multi-arm randomised trial put 38
sedentary middle-aged adults through 8 weeks of Finnish sauna, 15 minutes
immediately post-exercise, three times a week, starting at 149F and stepping up
to 176F. **Adding the sauna gave no HRV benefit over the exercise alone** - no
improvement in resting heart rate and none in RMSSD.

What survives:

- The **acute** effect is real but transient. Vagal activity falls *during* the
  heat; about 30 minutes into the cool-down the parasympathetic indices sit
  above baseline. That is an evening unwind, not a training effect.
- The positive long-run studies are in patient groups - daily 15-min infrared
  for two weeks in chronic heart failure, 3x/week for six weeks in allergic
  rhinitis - not in healthy people who already train.
- **The same cohort did get something from it**: exercise plus sauna beat
  exercise alone on cardiorespiratory fitness and systolic blood pressure. So
  the sauna is worth keeping for those, and for how it feels. It is no longer
  one of the HRV levers.

### Item 10, omega-3: 1-2 g/day EPA+DHA, three months before it shows

- **The dose that has evidence is 1 g/day of EPA+DHA combined** and up. The
  VITAL Rhythm trial used exactly 1 g (460 mg EPA + 380 mg DHA) and got a longer
  PR interval and a rise in RMSSD against placebo - both vagal. The review
  reading across the trials: at least 1 g/day, and **at least three months**
  before HRV moves. 2 g is comfortably above the threshold; nothing suggests
  more than that does more for HRV.
- **Read the label for EPA+DHA, not the capsule size.** A "1000 mg fish oil"
  softgel is usually about 300 mg of EPA+DHA, so 2 g is six or seven of them. A
  triple-strength concentrate gets there in two. Price per gram of EPA+DHA is
  the only number that matters.
- **The food route works.** Farmed Atlantic salmon runs about 2.2 g EPA+DHA per
  100 g cooked, so the 70 g portion on his October 18 row was roughly 1.5 g -
  one meal, most of a day's dose. Two salmon dinners a week averages out near
  the target, and sardines or mackerel do it cheaper. His meal rows show salmon
  rarely, which is the gap the capsules would fill.
- Practical: take it with a meal containing fat, keep it cold, and expect a
  mild blood-thinning effect at 2 g and up - worth a word to a doctor before any
  procedure. Magnesium stays conditional on what his `nutrition_check` rows say
  about intake.

**Proportion.** Items 2, 9 and 10 are the cheap end of the list. The breathing
is the second-strongest item on the page and costs 15 minutes. The sauna is now
a fitness and blood-pressure item rather than an HRV one, and omega-3 is a few
percent at best. Item 1 - the aerobic base he has no rows for - is still worth
more than all three together.

### Sources added November 9, 2026

- https://pmc.ncbi.nlm.nih.gov/articles/PMC12231185/ - post-exercise sauna, 8-week multi-arm RCT, no HRV benefit (2025)
- https://oulurepo.oulu.fi/bitstream/handle/10024/27848/nbnfi-fe2019091828656.pdf?sequence=1&isAllowed=y - recovery from sauna, acute parasympathetic rise 30 min after
- https://www.nature.com/articles/s41598-023-38344-x - VITAL Rhythm, 1 g/day omega-3, RMSSD and PR interval
- https://pmc.ncbi.nlm.nih.gov/articles/PMC13010831/ - omega-3 and HRV review: 1 g/day and 3 months as the thresholds
- https://www8.garmin.com/manuals/webhelp/GUID-F41EAFB3-6CC9-42DE-9C6C-9E358DBB0671/EN-US/GUID-B3BD9AA0-2235-43BC-AAD0-D38008420EAD.html - Forerunner 265 Breathwork activity, Coherence 6 s in / 6 s out

## Where to actually sauna (November 9, 2026)

Asked the same morning as the list above: does the Planet Fitness in Manor have a
sauna? No. Planet Fitness builds no saunas or steam rooms at essentially any club,
and the Manor one (1910 E US 290 Hwy Unit 370, in Manor Crossing) is a standard
18,600 sq ft build. The Black Card buys recovery without heat — HydroMassage beds,
massage chairs, the Total Body Enhancement booth (red light and vibration) — none
of which is a sauna.

Nearest heat to Manor:

- **Gold's Gym Pflugerville**, 21315 N SH 130 northbound — dry sauna, about ten
  minutes up the toll road. The practical option.
- **Cowboys Fit**, Pflugerville — sauna and steam room.
- **Castle Hill Fitness**, downtown Austin — two infrared saunas.
- **Big Tex Gym**, north Austin — infrared sauna.
- **Squatch Frontier Fitness** — traditional sauna with a cold plunge.

Worth remembering that item 9 moved down the list the same morning: the 2025 RCT
found no HRV benefit from 15 min post-exercise sauna three times a week. Keep it
for cardiorespiratory fitness and systolic blood pressure, which that cohort did
gain, rather than for HRV.

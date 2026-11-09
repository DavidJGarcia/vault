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

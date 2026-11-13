# Week 4: Paired and independent t-tests

Now we finally get to the question the whole study was built for: does music do anything?

## The question

Does music listening improve motor symptoms (MDS-UPDRS Part III) more than audiobook listening?

## Before you start

Imagine two ways of running this study. In the first, every patient gets both music and audiobooks. In the second, half the patients only get music and the other half only get audiobooks. Which one would you trust more with 80 patients, and why?

## Open in JASP

- `pd-music-crossover/derivatives/jasp-ready/cleaned/clinical_wide_by_condition.csv`
- `pd-music-crossover/derivatives/jasp-ready/cleaned/clinical_wide_by_session.csv`

In `clinical_wide_by_condition.csv`, `updrs3_music` is the score after the music period, whichever period that was for that person.

## What to look at

- Compare `updrs3_music` with `updrs3_audiobook` within the same patients (paired t-test). How big is the difference, and how big is the effect? Plot the means of both conditions with error bars.
- Now pretend you ran an ordinary two-group trial and stopped after the first period. In `clinical_wide_by_session.csv`, compare `updrs3_period1` between the two `sequence` groups (independent t-test).
- Do the two analyses agree? Compare the estimated difference, its standard error and the p value.
- Do `updrs3_music` and `updrs3_audiobook` correlate? How strongly?
- Repeat the paired test for `mdbf_gs` (good mood), `phq9` (depression) and `gad7` (anxiety). Which direction does each effect go?
- What are the assumptions of the paired t-test? Are they met? What do you do if they are violated?
- What are the assumptions of the independent t-test, and how do you check them? What do you do if one is violated?

## Discuss

- Write down the null hypothesis (H0) for the paired test. What does the p value tell you about H0, and what does it not tell you?
- How do you interpret the difference between the paired and the independent analysis? How does the correlation you found fit in?
- What does Cohen's d mean in the paired test? Is the effect small, medium or large? Is d the same as in the independent test?
- What is statistical power? Which of your two analyses had more power, and why? What would happen to the power of each with 20 patients instead of 80?
- What would a Type I error be in this study? And a Type II error?
- Do all outcomes favour music? How do you interpret any that do not?

## If you finish early

Back to week 2. Compare `phq9_baseline` between the patients who came back for follow-up and those who did not (`completed_followup`, independent t-test). How many patients are in each group? Are the assumptions met? If not, what do you do?

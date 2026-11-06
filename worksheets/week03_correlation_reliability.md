# Week 3: Correlation

Our first real analysis: a correlation.

## The question

Do patients with more non-motor symptoms sleep less?

## Before you start

Sleep was asked at every visit: "how many hours did you sleep last night?" How well do you think one night of sleep represents how someone usually sleeps? Think of your own last week.

## Open in JASP

`pd-music-crossover/derivatives/jasp-ready/cleaned/clinical_wide_by_session.csv`

Look up `nmsquest_total` and the four `sleep_` columns in `data_dictionary.csv`.

## What to look at

- Does `nmsquest_total` correlate with sleep? Correlate it with each of the four sleep nights separately. Look at the scatterplots, with a regression line and its confidence band, not only the numbers.
- Do the four sleep nights correlate with each other? How strongly?
- If you can, compute each patient's mean of the first three nights. Does it correlate with `nmsquest_total`? Why only the first three nights?
- Do `phq9_baseline`, `gad7_baseline` and `nmsquest_total` correlate with each other?
- Compare Pearson's r, Spearman's rho and Kendall's tau. Do they differ?

## Discuss

- How do you interpret the four single-night correlations? Are they the same every night?
- What do the correlations between the sleep nights tell you about one night of sleep as a measure of someone's usual sleep?
- How do you interpret the result for the mean of several nights, compared with the single nights?
- How do you interpret the pattern of correlations between depression, anxiety and non-motor symptoms?
- When would you choose Spearman's rho or Kendall's tau instead of Pearson's r? Which kind of variables does each need?
- Is this week's question answered with a correlational or an experimental design? What can you conclude about cause and effect, and what not?

## If you finish early

A colleague used only the baseline night to answer this week's question. What would you tell them?

Then open `pd-music-crossover/derivatives/jasp-ready/cleaned/tapping_wide_by_session.csv`. Does `updrs3_baseline` correlate with `tap_sd_90bpm_baseline` (both are in `data_dictionary.csv`)? What about `disease_duration_years` and `moca_total`? How strong are these correlations compared with the sleep correlations, and how do you interpret the difference?

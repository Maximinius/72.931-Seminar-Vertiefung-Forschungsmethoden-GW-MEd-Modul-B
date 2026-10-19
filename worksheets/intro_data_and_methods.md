## Overview of the semester

First of all, welcome to the seminar where we delve into research methods. This is an intensive course, and we have lots to do. The structure of the course is such that we will solve a bunch of worksheets together which all centre on a fictional dataset. Each worksheet will focus on a different aspect of research methods, and we will start with the very basics and very quickly ramp up to do some cool stuff with numbers. You can see the planned course outline (subject to change, of course) in the table below.

| Method | The question it answers | Example from this study | Week |
|---|---|---|---|
| Descriptives and plots | What do the data look like, and are they plausible? | Are all values plausible? | 1 |
| Dealing with missing data | Who is missing, and does it matter? | The patients who skipped follow-up | 2 |
| Correlation | Do two measures go together? | Non-motor symptoms and sleep | 3 |
| Paired t-test | Does the same person score differently in two conditions? | Music vs audiobook in each patient | 4 |
| Independent t-test | Do two groups of different people differ? | music_first vs audiobook_first after period 1 | 4 |
| Multiple regression | How does an outcome change with one predictor, holding others fixed? | TMT-B by age, holding MoCA fixed | 5, 6 |
| Logistic regression | What predicts a yes or no outcome? | Who comes back for follow-up | 6 |
| One-way ANOVA | Do several groups differ? | Motor scores by hospital | 7 |
| ANCOVA | Do groups differ once a covariate (such as baseline) is accounted for? | Mood after period 1, adjusted for depression and anxiety | 8 |
| Repeated measures ANOVA | Does an outcome change across several conditions in the same people? | Tapping by tempo and condition | 9 |
| Linear mixed model | Same as above, but with missing visits, several levels (patients in hospitals) and covariates | Motor scores by condition, patients and hospitals | 10 |
| Crossover analysis (mixed model) | Does the order of treatments matter, and did one linger into the next? | Does it matter whether music or audiobook came first? | 11 |


# First look at the data

Your dataset for the whole semester is organised in BIDS, a standard folder layout with plain text tables and a small codebook file next to every table. I've invented a brand new, totally fictional study about patients with Parkinson's Disease undergoing a music therapy intervention. We're going to use this mammoth of a dataset to explore all the different research methods we come across in health science. We're going to work through one worksheet per week, and every week we're going to do a different analysis and discuss different points that you may learn from the data. Since I generated it using code, you might find some weird stuff in there, and there might be a lot more to discuss than any of us suspect at the moment. What we're learning is how to talk to the data and interpret whatever truths it may tell us.

## What "study" does the data come from?

Eighty people with Parkinson's disease from six hospitals took part in a randomised crossover trial. Everyone had four weeks of daily music listening and four weeks of daily audiobook listening, in random order, with a two-week break in between. Half started with music (`music_first`), half with audiobooks (`audiobook_first`).

## An overview of the data

Let's now look at the data itself. Before you open it in JASP, take a look at the study design. What data format do you expect to end up with at the end of such a study if you were to organise it yourself?

| Visit | Week | Before the visit |
|---|---|---|
| baseline | 0 | nothing |
| period1 | 4 | first listening period |
| period2 | 10 | two-week break, then second listening period |
| followup | 18 | eight weeks without listening |

| Measure | What it captures | Measured at |
|---|---|---|
| MDS-UPDRS Part III (`updrs3`) | motor symptoms, rated by a clinician (higher = worse) | every visit |
| Trail Making Test A and B (`tmt_a`, `tmt_b`) | processing speed and mental flexibility, in seconds (higher = slower) | every visit |
| PHQ-9 (`phq9`), GAD-7 (`gad7`) | depression and anxiety (higher = worse) | every visit |
| MDBF (`mdbf_gs`, `mdbf_wm`, `mdbf_ru`) | good mood, alertness, calmness (higher = better) | every visit |
| Beat tapping at 60, 90, 120 bpm | how far taps fall from the beat, in ms (higher = worse) | every visit |
| Sleep (`sleep`) | hours slept the night before | every visit |
| MoCA, NMS-Quest | cognitive screening, number of non-motor symptoms | baseline only |



## Open in JASP

- `pd-music-crossover/participants.tsv` (raw BIDS)
- `pd-music-crossover/sub-001/ses-baseline/beh/sub-001_ses-baseline_task-tapping_beh.tsv` (raw BIDS)
- `pd-music-crossover/derivatives/jasp-ready/as_collected/clinical_wide_by_session.csv`
- `pd-music-crossover/derivatives/jasp-ready/as_collected/clinical_long.csv`

Read `pd-music-crossover/README.md` first. Open the `.json` files in any text editor.

## What to look at

- In `participants.tsv`: how many patients, from which hospitals, in which sequence? Is the sequence balanced within each hospital? Use `participants.json` to find out what each column means.
- In the tapping file: what does a single row describe? How many rows does one session have, and why that number? What does a negative asynchrony mean? The answer is in `task-tapping_beh.json`.
- In `sub-001/sub-001_sessions.tsv`: what happened at each visit?
- Compare `clinical_wide_by_session.csv` and `clinical_long.csv`. How many rows does each have? Is that what you expected from 80 patients and 4 visits?
- Find one variable in `derivatives/jasp-ready/data_dictionary.csv` and trace it back to the raw file it came from in `phenotype/`.
- Plot the mean disease duration for each hospital, with error bars.
- Decide for every variable in `participants.tsv` and in `clinical_wide_by_session.csv` whether it is nominal, ordinal, interval or ratio. JASP labels every column as nominal, ordinal or scale. Does JASP agree with you?
- Which measures were taken repeatedly over time, and which only once?

## Discuss

- Why does every `.tsv` file have a `.json` file next to it? What would you lose without it?
- Why are the raw files never edited, and everything processed kept in `derivatives/`?
- Which table would you need for a question about change over time? Which for a question comparing music with audiobooks?
- Look at the methods table. Which methods compare the same people with themselves, and which compare different people? Why might that matter?
- What kind of research design is this study: experimental, quasi-experimental, correlational or longitudinal? Can one study be more than one of these?
- The study started from an expectation that music helps, and then collected data to test it. Is that an inductive or a deductive approach? What would the other approach look like with this dataset?

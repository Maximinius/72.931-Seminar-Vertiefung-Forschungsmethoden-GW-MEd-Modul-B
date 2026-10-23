# Week 1: Checking the data

Before we analyse anything, we need to know whether we can trust the numbers.

## The question

Are there impossible or implausible values in the data as they were entered, and would they change any conclusion?

## Before you start

Open a few of the `.json` codebooks. For three measures of your choice, write down the smallest and the largest value that is actually possible.

## Open in JASP

- `pd-music-crossover/derivatives/jasp-ready/as_collected/clinical_wide_by_session.csv`
- `pd-music-crossover/derivatives/jasp-ready/as_collected/tapping_wide_by_condition.csv`
- `pd-music-crossover/phenotype/phq9.tsv` (raw item scores)

## What to look at

- Which descriptive statistics would tell you whether a value is impossible? Check every variable.
- Which plots would show you values that sit far away from all the others? Make them for every variable.
- Look up what TMT-A and TMT-B measure. What relationship would you expect between them? Plot TMT-A against TMT-B within each session, with a regression line and its confidence band. Does every patient fit your expectation?
- Are all the raw item scores in `phenotype/phq9.tsv` possible?
- Do the tapping values look plausible for every patient?
- Missing values: who is missing what?

Write a short cleaning log: participant, variable, value, why it is a problem, what you would do. Then open the same table in `cleaned/` instead of `as_collected/`. Do your findings match?

## Discuss

- For each problem you found: how do you interpret it? Could it be a real but unusual patient? How can you tell?
- Who should decide what gets removed, and when should that decision be made?
- Compare the means in `as_collected/` and `cleaned/`. Do they differ? How much does each problem matter, and how would you judge that?
- What is an outlier? Which of the values you found are outliers, and which are errors? How could a single outlier change a mean, a standard deviation or a correlation?

## If you finish early

Did you find any problem in the raw item data that you could not see in the totals? What does that mean for working with totals?

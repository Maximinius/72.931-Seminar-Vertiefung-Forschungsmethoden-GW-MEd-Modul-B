# Week 5: Regression

This week we try to predict how long patients need for the Trail Making Test.

## The question

Does TMT-B time change with age, for patients with the same cognitive screening score (MoCA)? If so, by how much per year?

## Before you start

TMT-B is a timed test: patients connect numbers and letters in alternating order, and the time in seconds is recorded. What would you expect the distribution of a time like this to look like?

## Open in JASP

- `pd-music-crossover/derivatives/jasp-ready/cleaned/clinical_wide_by_session.csv`
- later: `pd-music-crossover/derivatives/jasp-ready/as_collected/clinical_wide_by_session.csv`

## What to look at

- Is `tmt_b_baseline` normally distributed? How can you check?
- Correlate `age` with `tmt_b_baseline`. Then run a simple linear regression of `tmt_b_baseline` on `age`. Note the slope and R squared. Plot TMT-B against age, with the regression line and its confidence band.
- Then add `moca_total`. What happens to the age slope?
- Look at the coefficients with their confidence intervals, the standardised coefficients and R squared.
- Write down the regression equation of the model with age and MoCA. Use it to calculate the predicted TMT-B for a 60-year-old and for an 80-year-old, both with a MoCA of 26.
- Does the model fit all patients equally well? Does any single patient have a large influence on the result? How can you tell?
- Now run the same two-predictor model on the `as_collected` version of the table. Compare the age slope, its p value and R squared.
- If `tmt_b_baseline` is not normally distributed, what could you do about it? Try it, and rerun the two-predictor model. What changes?

## Discuss

- What does the correlation between age and TMT-B tell you, and what does the regression tell you? Which one lets you predict a patient's score?
- In plain words, what does the age slope mean in the model with MoCA? How is it different from the slope without MoCA?
- What does R squared mean in plain words?
- Which predictor is stronger, age or MoCA? How can you compare them when they are measured in different units?
- What did you do about the distribution of TMT-B, why does it help, and how does it change the meaning of the age slope?
- Compare R squared and the age slope between `cleaned` and `as_collected`. What changed? How do you interpret that?
- If you found an influential patient: would you have noticed them from the regression results alone? What else could have caught them?

## If you finish early

What is regression to the mean? Where might it show up in a trial with baseline measurements?

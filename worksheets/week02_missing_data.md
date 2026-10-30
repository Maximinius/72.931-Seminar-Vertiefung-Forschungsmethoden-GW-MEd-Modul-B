# Week 2: Dealing with missing data

Last week we hunted for values that shouldn't be there. This week it's the opposite: values that should be there but aren't.

## The question

Who did not come back for the follow-up visit, and can we still trust what the follow-up data tell us?

## Before you start

Eight weeks after the last listening period, everyone was invited back for a follow-up visit. What reasons could someone with Parkinson's disease have for not coming back? Would any of those reasons have something to do with how they were doing?

## Open in JASP

`pd-music-crossover/derivatives/jasp-ready/cleaned/clinical_wide_by_session.csv`

## What to look at

- How many values are missing for each variable at each visit? Which visit has the most missing values?
- Who did not come back (`completed_followup`)? Which hospitals and which sequence do they come from?
- Compare the patients who came back with those who did not, at baseline: `phq9_baseline`, `gad7_baseline`, `mdbf_gs_baseline` and `updrs3_baseline`. Plot the baseline means of both groups with error bars.
- Suppose you only analyse patients with complete data. What is the baseline PHQ-9 mean of the patients who came back? And of everyone? Do they differ?
- Look at the PHQ-9 mean at follow-up. Which patients does that mean describe?

## Discuss

- What do "missing completely at random", "missing at random" and "missing not at random" mean? Which one describes the follow-up dropout? What evidence do you have, and what can you never check?
- If the patients who did not come back differed from those who did, in which direction would that push the follow-up means? What would that do to a conclusion about the follow-up?
- Would it be a good idea to simply delete every patient with a missing value? What would you lose?
- What would you write in the limitations section about follow-up?

## If you finish early

Are all missing values in this table dropouts? Look for missing values at the other visits. Where do they come from?

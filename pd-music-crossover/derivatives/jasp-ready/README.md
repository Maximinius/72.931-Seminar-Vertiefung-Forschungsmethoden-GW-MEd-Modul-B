# JASP-ready tables

These tables were made from the raw BIDS data in the folder above. Every table opens directly in JASP and needs no filtering. Missing values are empty cells.

## Two versions of every table

- `as_collected/`: the data exactly as they were entered, aggregated but not checked.
- `cleaned/`: the same tables after data checks. Impossible values were set to missing, and data from task sessions that were clearly invalid were removed.

Comparing the two is part of the job. If an analysis gives a different answer in `as_collected/` and `cleaned/`, find out why.

## The tables

| File | One row per | Use it for |
|---|---|---|
| `clinical_long.csv` | participant and session | plots over time, mixed models |
| `clinical_wide_by_session.csv` | participant, columns in time order | repeated measures over time, baseline comparisons |
| `clinical_wide_by_condition.csv` | participant, columns by condition | music versus audiobook comparisons |
| `tapping_long.csv` | participant, session and tempo | mixed models of tapping |
| `tapping_wide_by_session.csv` | participant, columns in time order | repeated measures over time |
| `tapping_wide_by_condition.csv` | participant, columns by condition | music versus audiobook comparisons |

Wide tables name their columns `measure_level`. In `clinical_wide_by_session.csv`, `phq9_period1` is the PHQ-9 total at the period 1 session. In `clinical_wide_by_condition.csv`, `phq9_music` is the PHQ-9 total after the music period, whichever period that was for that person.

`data_dictionary.csv` lists every column of every table.

## What was done to the raw data

1. Questionnaire totals were computed from the items in `phenotype/`. For the MDBF, negatively poled items were reversed first. If any item was missing, the total is missing.
2. For tapping, beats 1 to 5 of each block (the synchronisation-in phase) were dropped. Missed taps were ignored. For each block, the mean absolute asynchrony, the SD of the asynchrony and the mean signed asynchrony were computed.
3. Participant information from `participants.tsv` was added to every table. The clinical tables also contain the MoCA and NMS-Quest totals. The tapping wide tables also contain the MoCA total and the baseline MDS-UPDRS III score (`updrs3_baseline`), so tapping can be related to motor severity without combining tables.
4. The clinical wide tables contain `completed_followup` (`yes` or `no`): whether the patient came to the follow-up session.
5. The tables were reshaped to long and wide formats.

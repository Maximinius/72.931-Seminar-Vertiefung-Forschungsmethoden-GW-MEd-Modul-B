# PD-MUSIC: music versus audiobook listening in Parkinson's disease

**This is a simulated teaching dataset. No real patients took part, and the results must not be cited as evidence.**

## The study

Eighty people with Parkinson's disease (PD) were recruited from six hospitals: Charite (Berlin), Beelitz, UKE (Hamburg), Leipzig, Naumburg and Haukeland (Bergen, Norway). Each person took part in a randomised crossover trial with two 4-week listening interventions:

- **Music:** 30 minutes of music listening per day
- **Audiobook:** 30 minutes of audiobook listening per day (the control condition)

Every participant received both interventions. Half the participants at each hospital started with music, and the other half started with the audiobook (see `sequence` in `participants.tsv`).

| Week | Session | What happened before it |
|---|---|---|
| 0 | `ses-baseline` | nothing, first visit |
| 4 | `ses-period1` | 4 weeks of the first intervention |
| 10 | `ses-period2` | 2 weeks without listening, then 4 weeks of the second intervention |
| 18 | `ses-followup` | 8 weeks without any intervention |

At every session, patients completed:

- MDS-UPDRS Part III (motor symptoms, clinician-rated)
- Trail Making Test A and B (processing speed and cognitive flexibility)
- PHQ-9 (depression) and GAD-7 (anxiety)
- MDBF (mood: good versus bad, alert versus tired, calm versus restless)
- A beat-tapping task at three tempi (60, 90 and 120 beats per minute)
- A question about how long they slept the night before

At baseline only, they also completed the MoCA (cognitive screening) and the NMS-Quest (non-motor symptoms). Demographics, disease duration, Hoehn and Yahr stage and daily levodopa dose are in `participants.tsv`.

## How the folder is organised (BIDS)

This dataset follows the Brain Imaging Data Structure (BIDS), a standard way to organise research data so that anyone can find everything without asking.

```
pd-music-crossover/
  dataset_description.json      what this dataset is
  README.md                     this file
  participants.tsv / .json      one row per person, plus a codebook
  task-tapping_beh.json         codebook for the tapping files
  phenotype/                    questionnaires and clinical scores, item by item
  sub-001/
    sub-001_sessions.tsv / .json  one row per visit: date, condition, sleep
    ses-baseline/beh/           raw tapping data, one row per beat
    ses-period1/beh/
    ...
  derivatives/jasp-ready/       processed tables you can open directly in JASP
```

Rules worth knowing:

- `.tsv` files are tables separated by tabs. Every `.tsv` file has a `.json` file that explains its columns. Always read the `.json` file first.
- Missing values are written as `n/a`. In JASP, check that `n/a` is in the list of missing value codes (Preferences, Data).
- The raw data are never edited. Everything processed lives in `derivatives/`.
- Some participants have no `ses-followup` folder. That is not an error.

## Where to start

Open `participants.tsv` in JASP. Then open one participant's tapping file, for example `sub-001/ses-baseline/beh/sub-001_ses-baseline_task-tapping_beh.tsv`, and try to work out what a single row means. After that, look at `derivatives/jasp-ready/README.md`.

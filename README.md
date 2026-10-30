# Practical seminar worksheets: PD-MUSIC

All worksheets use one dataset, `pd-music-crossover/`: 80 people with Parkinson's disease from six hospitals who listened to music for four weeks and to audiobooks for four weeks, in random order. The dataset is simulated. Its results must not be cited as evidence.

Every session asks one research question and names the table to open in JASP. The worksheets tell you what to look at, not where to click. You will never need a filter: every table is already shaped for the analysis.

All JASP-ready tables live in `pd-music-crossover/derivatives/jasp-ready/`, in two versions:

- `as_collected/`: the data as they were entered
- `cleaned/`: the same data after checking

Use `cleaned/` unless the worksheet says otherwise.

| Session | Date | Question | Table | Method |
|---|---|---|---|---|
| Intro | 19 Oct | What was measured, on whom and when? | `as_collected/clinical_long.csv`, `as_collected/clinical_wide_by_session.csv` | The study, BIDS, codebooks, long vs wide, scales of measurement, research designs |
| 1 | 26 Oct | Are there impossible values, and do they matter? | `as_collected/clinical_wide_by_session.csv` | Descriptives, plots, data checking, outliers |
| 2 | 02 Nov | Who is missing, and does it matter? | `cleaned/clinical_wide_by_session.csv` | Missing data |

## Before the first session

- Install JASP (jasp-stats.org). Enable the Mixed Models module, which you will need later.
- JASP needs to know that `n/a` means missing. Find out where JASP keeps its missing value codes and check that `n/a` is one of them. The raw BIDS files use `n/a`. The JASP-ready tables use empty cells, which JASP reads as missing anyway.

The next worksheet appears on Friday 06 November at 08:00.

## Getting each week's materials

New worksheets and data appear here a few days before each session. You never need a terminal.

**Option A: GitHub Desktop (recommended, once set up it is one click per week)**

1. Install GitHub Desktop (desktop.github.com). You do not need a GitHub account to download.
2. File, Clone repository, URL tab, paste this page's address, choose a folder, click Clone.
3. Every week: open GitHub Desktop, click **Fetch origin**, then **Pull origin**.

**Option B: download a zip**

On this page, click the green **Code** button, then **Download ZIP**, and unzip it. Do this again each week. Keep your own files somewhere else, or they will end up in an old copy.

**Where to save your work**

Save your JASP files in `my_work/`. That folder is never overwritten, so pulling the next week is always safe. Do not edit the files in `pd-music-crossover/`. If you change one by accident and GitHub Desktop complains when you pull, right-click the file under Changes and choose Discard changes.

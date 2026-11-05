# Task 1: Data Cleaning and Preprocessing (Netflix Titles)

Elevate Labs Data Analyst Internship, Task 1.

## Objective
Clean and prepare a raw dataset containing nulls, duplicates and inconsistent formats using Python (pandas).

## Dataset
[Netflix Movies and TV Shows](https://www.kaggle.com/datasets/shivamb/netflix-shows) (Kaggle)
Raw shape: 8,807 rows x 12 columns

## Issues Found
- Missing values: `director` ([ ]), `cast` ([ ]), `country` ([ ]), `date_added` (10), `rating` (7)
- Duplicate rows: [ ] full-row duplicates, [ ] duplicate `show_id`
- 3 rows had duration stored in the `rating` column (Louis C.K. titles)
- `rating` used two labels for the same meaning (`NR` and `UR`)
- `date_added` was stored as text (e.g. "September 25, 2021")
- `duration` mixed minutes (movies) and seasons (TV shows) in one text column

## Steps Taken
1. Inspected shape, data types, missing values and duplicates
2. Stripped extra whitespace from all text columns
3. Moved the 3 misplaced duration values from `rating` to `duration`
4. Merged `NR` and `UR` into "Not Rated" and filled the 7 missing ratings with "Not Rated"
5. Filled missing `director`, `cast` and `country` with "Unknown" instead of dropping rows
6. Converted `date_added` to datetime; [describe what you did with the 10 missing dates]
7. Split `duration` into `duration_value` (number) and `duration_unit` (min / Season(s))
8. Saved the cleaned file with dates in dd-mm-yyyy format

## Result
| | Before | After |
|---|---|---|
| Rows | 8,807 | [ ] |
| Columns | 12 | 15 |
| Missing values | [ ] | 0 |

## Screenshots
**Initial inspection**
![Inspection](screenshots/01_inspection.png)

**Hidden issues found**
![Hidden issues](screenshots/02_hidden_issues.png)

**Fixes applied**
![Fixes](screenshots/03_fixes.png)

**Final check**
![Final check](screenshots/04_final_check.png)

## Files
- `data/netflix_titles.csv`: original data
- `data/cleaned_netflix_titles.csv`: cleaned data
- `data_cleaning.ipynb`: full cleaning code
- `screenshots/`: output at each step

#

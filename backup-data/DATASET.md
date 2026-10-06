# Backup dataset: Netflix titles

**File:** `netflix_backup.csv` (450 rows, 12 columns)

**Source:** "Netflix Movies and TV Shows" on Kaggle (`netflix_titles.csv`, 8,807 titles, snapshot through 2021).
**License:** listed as CC0 (public domain) as far as I know, but check the license on the dataset's Kaggle page before you publish, and credit the original author either way.

## How it was made

A random sample (seed 7) from the full file: 300 movies and 150 TV shows. Only titles with a cast, country, genre list, date added, rating, and duration were kept, so those columns have no blanks. `director` is blank for 141 rows, because most TV shows don't list one.

## Columns

| Column | What it is |
|---|---|
| `show_id` | Netflix's ID, like `s123` |
| `type` | `Movie` or `TV Show` |
| `title` | The title |
| `director` | Director(s), comma-separated. Often blank for TV shows |
| `cast` | Actors, comma-separated |
| `country` | Production countries, comma-separated |
| `date_added` | When it was added to Netflix, like `September 25, 2021` |
| `release_year` | Year it was released |
| `rating` | Age rating, like `TV-MA` or `PG-13` |
| `duration` | Movies: `90 min`. TV shows: `2 Seasons` |
| `listed_in` | Genres, comma-separated |
| `description` | One-sentence summary |

## Things to know

- `cast`, `country`, `listed_in`, and sometimes `director` hold several values in one cell. Split them (`.str.split(", ")`, then `.explode()` in pandas) before counting or linking.
- `duration` mixes minutes and seasons, so split movies and TV shows before analyzing it.
- It's a sample, so small differences may just be chance.
- Good column pairs for a graph: `country` and `listed_in`. Actor-to-title links are sparse in a sample this size.

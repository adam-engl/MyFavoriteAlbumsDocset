## Global Variables<!-- {docsify-ignore} -->

### `album_data`

The main data frame containing all album information loaded from CSV.

**Type:** Data frame
**Source:** `data/album-rankings.csv`
**Available in:** All modules

### `all_bands`

Alphabetically sorted vector of all unique artist names in the dataset.

**Type:** Character vector
**Source:** `albums_by_band.R`
**Usage:**

```r
selectInput("band_name", "Choose artist:", all_bands)
```

### `all_years`

Sorted vector of all unique years in the dataset.

**Type:** Numeric vector
**Source:** `albums_by_year.R`
**Usage:**

```r
selectInput("year", "Choose a year:", all_years)
```

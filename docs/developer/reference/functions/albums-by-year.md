### albums_by_year.R

#### `year_albums(year.var)`

Returns all albums from a specific year, ordered by ranking.

**Parameters:**

- `year.var` (numeric): The year to filter by

**Returns:**

- Data frame with columns: Ranking, Album, Artist

**Example:**

```r
year_albums(2022)
# Returns:
#   Ranking                    Album                  Artist
# 1       1          Asphalt Meadows      Death Cab for Cutie
# 2       2        A Bit of Previous       Belle and Sebastian
# 3       3   Expert in a Dying Field              The Beths
```

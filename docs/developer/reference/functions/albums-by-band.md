### albums_by_band.R

#### `albums_by_bands(band.var)`

Returns all albums by a specified artist, ordered by year.

**Parameters:**

- `band.var` (string): The artist name to filter by

**Returns:**

- Data frame with columns: Album, Year, Rating

**Example:**

```r
albums_by_bands("Radiohead")
# Returns:
#                Album  Year Rating
# 1        Pablo Honey  1993      8
# 2     My Iron Lung    1994      8
# 3        The Bends    1995     10
```

#### `band_mean_rating(band.var)`

Calculates and prints the average rating for all albums by an artist.

**Parameters:**

- `band.var` (string): The artist name

**Returns:**

- Prints formatted average rating string

**Example:**

```r
band_mean_rating("Belle and Sebastian")
# Prints: "Average Rating: 9.25"
```

#### `band_album_count(band.var)`

Counts and prints the number of ranked albums for an artist.

**Parameters:**

- `band.var` (string): The artist name

**Returns:**

- Prints formatted count string

**Example:**

```r
band_album_count("The Decemberists")
# Prints: "Number of Albums Ranked: 12"
```

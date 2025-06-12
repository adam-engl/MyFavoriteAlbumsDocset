### vinyl.R<!-- {docsify-ignore} -->

#### `missing_vinyl()`

Returns highly-rated albums (rating ≥ 9) not owned on vinyl.

**Parameters:**

- None

**Returns:**

- Data frame with columns: Album, Artist, Rating (ordered by rating descending)

**Example:**

```r
missing_vinyl()
# Returns albums rated 9+ without vinyl ownership
```

#### `year_most_vinyl()`

Returns years sorted by number of vinyl albums owned.

**Parameters:**

- None

**Returns:**

- Data frame with columns: Year, n (count of vinyl albums)

**Example:**

```r
year_most_vinyl()
# Returns:
#   Year  n
# 1 2022 12
# 2 2021 11
# 3 2023  9
```

### number_one_albums.R<!-- {docsify-ignore} -->

#### `number_one_album(var.startyear, var.endyear)`

Returns the #1 ranked album for each year in the specified range.

**Parameters:**

- `var.startyear` (numeric): Starting year of range
- `var.endyear` (numeric): Ending year of range

**Returns:**

- Data frame with columns: Year, Album, Artist

**Example:**

```r
number_one_album(2020, 2022)
# Returns:
#   Year                Album                Artist
# 1 2020            St. Cloud           Waxahatchee
# 2 2021                 Sour        Olivia Rodrigo
# 3 2022      Asphalt Meadows  Death Cab for Cutie
```

### compare_bands.R<!-- {docsify-ignore} -->

#### `band_album_comparison_chart(var.artist1, var.artist2)`

Creates a line chart comparing two artists' album ratings over time.

**Parameters:**

- `var.artist1` (string): First artist name
- `var.artist2` (string): Second artist name

**Returns:**

- ggplot2 chart object with red line for artist1, blue line for artist2

**Example:**

```r
chart <- band_album_comparison_chart("Radiohead", "Arcade Fire")
print(chart)
# Displays comparison chart with:
# - X-axis: Years (1993-2024)
# - Y-axis: Rating (0-10)
# - Red line: Radiohead albums
# - Blue line: Arcade Fire albums
```

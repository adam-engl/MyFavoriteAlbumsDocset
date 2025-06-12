# MyFavoriteAlbums Developer Reference Guide

## Overview

This reference documents all functions available in the MyFavoriteAlbums R application. Functions are organized by module file for easy navigation.

---

## Function Reference by Module

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

---

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

---

### number_one_albums.R

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

---

### vinyl.R

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

---

### compare_bands.R

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

---

## Global Variables

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

---

## UI Output Functions

These functions are used in `app_server.R` to render data for display:

### `renderTable()`

Renders data frames as HTML tables in the UI.

**Common usage:**

```r
output$album_table <- renderTable({
    return(albums_by_bands(input$band_name))
})
```

### `renderText()`

Renders text output in the UI.

**Common usage:**

```r
output$avg_rating <- renderText({
    return(band_mean_rating(input$band_name))
})
```

### `renderPlot()`

Renders ggplot2 charts in the UI.

**Common usage:**

```r
output$compare_bands <- renderPlot({
    return(band_album_comparison_chart(input$band_name_1, input$band_name_2))
})
```

---

## Package Dependencies

### Required Packages

- **shiny**: Web application framework
- **dplyr**: Data manipulation
- **ggplot2**: Data visualization
- **DT**: Interactive data tables

### Loading Packages

```r
library(shiny)
library(dplyr)
library(ggplot2)
library(DT)
```

---

## Common Patterns

### Data Filtering Pattern

```r
# Filter by single criterion
filter(album_data, Artist == "Radiohead")

# Filter by multiple criteria
filter(album_data, Year >= 2020, Rating >= 9)

# Filter and select columns
select(filter(album_data, Vinyl == "v"), Album, Artist, Year)
```

### Data Ordering Pattern

```r
# Order by single column
album_data[order(album_data$Year),]

# Order by multiple columns
album_data[order(album_data$Year, album_data$Ranking),]

# Reverse order
album_data[order(-album_data$Rating),]
```

### Reactive Pattern in Shiny

```r
observeEvent(input$action_button, {
    # Code executes when button is clicked
    output$result <- renderTable({
        # Process and return data
    })
})
```

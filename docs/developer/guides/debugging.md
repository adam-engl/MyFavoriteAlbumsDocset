## Debugging the Application<!-- {docsify-ignore} -->

**Prerequisites:**

- Completed development environment setup.
- Understanding of the codebase structure.
- Familiarity with R programming.

### Common Issues and Solutions

#### Data Processing Errors

If a function isn't returning expected results:

```r
# Source the file with the function
source("albums_by_band.R")

# Call the function with test parameters
result <- albums_by_bands("Radiohead")

# Examine the result
print(result)
str(result)
```

#### Tracking Function Execution

If you need to understand how a function is processing data, add print statements:

```r
albums_by_bands <- function(band.var){
  print(paste("Filtering for band:", band.var))
  band_albums <- select(filter(album_data[order(album_data$Year),], Artist==band.var), Album, Year, Rating)
  print(paste("Found", nrow(band_albums), "albums"))
  return(band_albums)
}
```

#### Reactive Programming Issues

If the Shiny app isn't responding to user inputs as expected, add debugging output:

```r
# In app_server.R
observeEvent(input$action_button,{
  print("Submit button clicked")
  print(paste("Selected artist:", input$band_name))

  output$album_table <- renderTable({
    result <- albums_by_band(input$band_name)
    print("Table data generated")
    return(result)
  })

  # Rest of the code...
})
```

Check the R console for these messages when running the app.

#### CSV File Loading Issues

If the application can't find or read the data file:

```r
# Check if the file exists
file.exists("data/album-rankings.csv")

# Preview the file content
head(read.csv("data/album-rankings.csv"))
```

#### Interactive Debugging

For complex issues, use `browser()` to enter interactive debugging mode:

```r
top_decade_ratings <- function() {
  browser()  # This will pause execution and open interactive debugging
  album_data$Decade <- floor(album_data$Year / 10) * 10
  # Rest of the function...
}
```

When `browser()` activates:

- Examine variables in the environment
- Step through code execution
- Continue execution with 'c'
- Quit debugging with 'Q'

### Common Error Checklist

- **Missing or incorrectly named columns in the CSV**
- **Typos in function or variable names**
- **Missing dependencies or libraries**
- **Incorrect data types** (e.g., treating numbers as strings)

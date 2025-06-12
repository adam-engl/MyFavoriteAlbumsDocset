# MyFavoriteAlbums: Developer Guide

This guide is designed for developers who want to work with, modify, or extend the MyFavoriteAlbums codebase. It assumes basic programming knowledge and provides task-oriented instructions for common development activities.

## Table of Contents

1. [Setting Up Your Development Environment](#setting-up-your-development-environment)
2. [Understanding the Codebase Structure](#understanding-the-codebase-structure)
3. [Using Existing Functions](#using-existing-functions)
4. [Adding a New Analysis Feature](#adding-a-new-analysis-feature)
5. [Debugging the Application](#debugging-the-application)
6. [Deploying the Application](#deploying-the-application)

## Setting Up Your Development Environment

**Audience:** Developers with some programming experience who want to work with the MyFavoriteAlbums codebase

**Prerequisites:**

- Basic familiarity with programming concepts
- System with administrator access to install software

**Steps:**

1. Install R on your system:

   a. Go to https://cran.r-project.org/.

   b. Select your operating system (Windows, macOS, or Linux).

   c. Download and install the latest version of R.

2. Install RStudio Desktop:

   a. Go to https://posit.co/download/rstudio-desktop/.

   b. Download and install the appropriate version for your operating system.

3. After installation is complete, launch RStudio.

4. Install the required R packages by running the following commands in the RStudio console:

   ```r
   install.packages("shiny")
   install.packages("dplyr")
   install.packages("ggplot2")
   install.packages("DT")
   ```

   > Wait for each package to download and install before proceeding.

5. Clone or download the MyFavoriteAlbums repository:

   - If using Git: `git clone https://github.com/UW-Example-Student/MyFavoriteAlbums`.
   - If downloading manually: Extract the ZIP file to your preferred location.

6. In RStudio, select _File_ → _Open Project_ and navigate to the MyFavoriteAlbums directory.

   > Alternatively, select _File_ → _Open File_ and navigate to the app.R file.

7. Verify your setup by running the application:

   a. In RStudio, with app.R open, click the _Run App_ button in the top-right corner of the editor.

   > The Shiny application should launch in a new window or in your web browser.

Your development environment is now ready to work with MyFavoriteAlbums.

<!-- TODO: Move to concept docs -->

## Understanding the Codebase Structure

**Audience:** Developers who want to understand how the MyFavoriteAlbums code is organized

**Prerequisites:**

- Completed development environment setup
- Basic knowledge of R programming

**Steps:**

1. Open RStudio and navigate to the MyFavoriteAlbums project.

2. Open the main app.R file to understand the application's entry point:

   ```r
   file.edit("app.R")
   ```

3. Examine the structure of app.R:

   - The file loads necessary libraries
   - Sources all component files using the `source()` function
   - Creates a Shiny application using `shinyApp()`

4. Identify the key component files:

   - `app_ui.R`: Defines the user interface structure
   - `app_server.R`: Contains the server logic that responds to user inputs
   - `albums_by_band.R`: Functions for artist-based analysis
   - `albums_by_year.R`: Functions for year-based analysis
   - `number_one_albums.R`: Functions for analyzing top-ranked albums
   - `vinyl.R`: Functions for vinyl collection analysis
   - `compare_bands.R`: Functions for comparing artists
   - `data/album-rankings.csv`: The data file

5. Open the UI file to understand the interface structure:
   ```r
   file.edit("app_ui.R")
   ```
6. Note the key UI components:

   - A `fluidPage` that contains all UI elements
   - A `tabsetPanel` that creates the tabbed interface
   - Individual `tabPanel` elements for each analysis section
   - Input controls (sliders, dropdowns, buttons)
   - Output placeholders (`tableOutput`, `plotOutput`)

7. Open the server file to understand the application logic:

   ```r
   file.edit("app_server.R")
   ```

8. Note the server function structure:
   - Output renderers that populate UI elements with data
   - Event observers that respond to user actions
   - Function calls that process data
9. Open one of the analysis module files to understand the function design:

   ```r
   file.edit("albums_by_band.R")
   ```

10. Note that each module typically:
    - Loads the data from CSV
    - Defines helper variables (like lists of all bands)
    - Contains functions that filter and transform the data
    - Returns processed data for display

## Testing/Modifying Existing Functions

**Audience:** Developers who want to explore and use the existing functions in MyFavoriteAlbums

**Prerequisites:**

- Completed development environment setup
- Understanding of the codebase structure

**Steps:**

1. Open RStudio and navigate to the MyFavoriteAlbums project.

2. Load all functions into your R environment by running:

   ```r
   source("albums_by_band.R")
   source("albums_by_year.R")
   source("number_one_albums.R")
   source("vinyl.R")
   source("compare_bands.R")
   ```

3. Test the artist analysis function in the console:

   ```r
   # View albums by a specific artist
   albums_by_band("Radiohead")

   # Get the average rating for an artist
   band_mean_rating("Radiohead")

   # Count albums by an artist
   band_album_count("Radiohead")
   ```

4. Test the year analysis function:

   ```r
   # View albums from a specific year
   year_albums(2022)
   ```

5. Test the number one albums function:

   ```r
   # View top albums from a range of years
   number_one_album(2015, 2022)
   ```

6. Test the vinyl collection analysis functions:

   ```r
   # View highly-rated albums you don't own on vinyl
   missing_vinyl()

   # See which years have the most vinyl in your collection
   year_most_vinyl()
   ```

7. Test the band comparison visualization function:

   ```r
   # Compare two artists' ratings over time
   comparison_chart <- band_album_comparison_chart("Radiohead", "Arcade Fire")
   print(comparison_chart)
   ```

8. To modify function behavior for testing, you can edit the function directly in RStudio:

   a. Open the file containing the function you want to modify:

   ```r
   file.edit("albums_by_band.R")
   ```

   b. Make your changes to the function in the editor window.

   c. Save the file (Ctrl+S or Cmd+S).

   d. Re-source the file to load your changes:

   ```r
   source("albums_by_band.R")
   ```

   e. Test the modified function:

   ```r
   albums_by_bands("Dom Dolla")
   ```

   > **Note:** After testing, you may want to revert your changes to restore the original functionality.

## Adding a New Analysis Feature

**Audience:** Developers who want to extend MyFavoriteAlbums with new functionality

**Prerequisites:**

- Completed development environment setup
- Understanding of existing functions and structure
- Familiarity with R and Shiny programming

**Steps:**

1. Determine what new analysis feature you want to add. For this example, we'll add a feature to find the decade with the highest average album rating.

2. Create a new R file for your feature:

   - In RStudio, select _File_ → _New File_ → _R Script_
   - Save the file as `albums_by_decade.R`

3. Add the necessary libraries and load the data in your new file:

   ```r
   library(dplyr)

   # Grab the music data
   album_data <- read.csv("data/album-rankings.csv")
   ```

4. Write a function to calculate the average rating by decade:

   ```r
   top_decade_ratings <- function() {
     # Add a decade column
     album_data$Decade <- floor(album_data$Year / 10) * 10

     # Group by decade and calculate average rating
     decade_ratings <- album_data %>%
       group_by(Decade) %>%
       summarize(AvgRating = mean(Rating),
                 NumAlbums = n()) %>%
       arrange(desc(AvgRating))

     return(decade_ratings)
   }
   ```

5. Save your file.

6. Update `app.R` to source your new file by adding this line after the other source() calls:

   ```r
   source("albums_by_decade.R")
   ```

7. Modify `app_ui.R` to add a new tab. Locate the `tabsetPanel` section and add a new tab:

   ```r
   tabPanel("Decades",
            htmlOutput("text_decade"),
            tableOutput("decade_table"))
   ```

8. Update `app_server.R` to handle the new tab. Add the following inside the server function:

   ```r
   # Decade tab
   output$text_decade <- renderUI({
     HTML("<h2>Average Album Ratings by Decade</h2><br>")
   })

   output$decade_table <- renderTable({
     return(top_decade_ratings())
   })
   ```

9. Save all modified files.

10. Run the application by clicking the _Run App_ button in RStudio.

11. Test your new feature by clicking on the _Decades_ tab in the interface.

12. If needed, refine your function and UI to improve the presentation:
    - Add more columns to the analysis
    - Improve formatting
    - Add user controls like filters or sorting options



## Debugging the Application

**Audience:** Developers who need to troubleshoot issues in the MyFavoriteAlbums application

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

## Deploying the Application

**Audience:** Developers who want to share their MyFavoriteAlbums application with others

**Prerequisites:**

- Completed and tested MyFavoriteAlbums application
- [shinyapps.io](https://www.shinyapps.io/) account (for shinyapps.io deployment)

**Steps:**

1. Create a free account on shinyapps.io:

   a. Go to https://www.shinyapps.io/

   b. Sign up for a free account

2. Navigate back to RStudio and install the rsconnect package in the console:

   ```r
   install.packages("rsconnect")
   ```

3. Configure your account in RStudio:

   a. Click on _Tools_ → _Global Options_ → _Publishing_.

   b. Click _Connect_.

   c. Select _shinyapps.io_.

   d. Follow the instructions to authorize RStudio.

4. Ensure your data file is correctly located in the project:

   - The CSV file should be in the `data` directory
   - The path in your code should be relative: `data/album-rankings.csv`

5. Open the main app.R file in RStudio.

6. Click the _Publish_ button in the top-right corner of the editor.

7. In the dialog that appears:

   a. Select all files in your project (app.R, app_ui.R, app_server.R, etc.).

   b. Make sure to include the data directory.

   c. Provide a name for your application.

   d. Click _Publish_.

   > **Note:** RStudio will package and upload your application to shinyapps.io. When the upload is complete, your browser will open showing your deployed application.

8. Share the URL with others to give them access to your application.

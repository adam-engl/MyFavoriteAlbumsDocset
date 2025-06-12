## Adding a New Analysis Feature <!-- {docsify-ignore} -->

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

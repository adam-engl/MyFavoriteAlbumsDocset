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

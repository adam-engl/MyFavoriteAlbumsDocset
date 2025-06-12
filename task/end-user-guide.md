# MyFavoriteAlbums: End User Guide

This guide is designed for music enthusiasts who want to analyze their album rankings and collection data using the MyFavoriteAlbums application. No programming knowledge is required to follow these instructions.

## Table of Contents

1. [Formatting Your Album Rankings Data](#formatting-your-album-rankings-data)
2. [Navigating the Web Interface](#navigating-the-web-interface)
3. [Finding Your Top Albums By Year](#finding-your-top-albums-by-year)
4. [Analyzing Artist Discographies](#analyzing-artist-discographies)
5. [Comparing Artists](#comparing-artists)
6. [Exploring Your Vinyl Collection](#exploring-your-vinyl-collection)
7. [Viewing Number One Albums](#viewing-number-one-albums)

## Formatting Your Album Rankings Data

Before you can analyze your album rankings, you need to prepare your data in the correct format.

**Audience:** Music enthusiasts with basic spreadsheet knowledge

**Prerequisites:**

- Spreadsheet software (Microsoft Excel, Google Sheets, etc.)
- A list of your favorite albums with rankings
- (Optional) R and RStudio installed if you want to run the application locally
- (Optional) Basic knowledge of R and RStudio

**Steps:**

1. Open your spreadsheet software and create a new blank CSV spreadsheet.

2. Add the following column headers in row 1:

   - Year
   - Ranking
   - Album
   - Artist
   - Rating
   - Vinyl
   - EP
   - Live

3. Enter your album data under the appropriate columns:

   - **`Year`**: Enter the release year as a four-digit number (e.g., 2023)
   - **`Ranking`**: Enter the position within that release year (e.g., 1 for your top album of that year)
   - **`Album`**: Enter the album title
   - **`Artist`**: Enter the band or musician name
   - **`Rating`**: Enter your numerical score on a 0-10 scale
   - **`Vinyl`**: Enter "v" if you own this on vinyl, leave blank if not
   - **`EP`**: Enter "EP" if this is an extended play, leave blank if not
   - **`Live`**: Enter "Live" if this is a live recording, leave blank if not

4. Save your file as `album-rankings.csv` in CSV format.

   > **Note:** Make sure to use the exact filename `album-rankings.csv` as the application is configured to look for this specific filename.

   Your data is now ready to be used with MyFavoriteAlbums.

5. To see your data in the MyFavoriteAlbums application:

   - If you're using the public demo, you cannot upload your own data (the demo uses sample data)
   - To use your own data, you need to download and run the R code locally:
     - Download the MyFavoriteAlbums code from the [repository](https://github.com/UW-Example-Student/MyFavoriteAlbums)
     - Place your `album-rankings.csv` file in the `data` folder
     - Run the application using R and RStudio
     - Your personal album data will now appear in the application

   Your data is now ready to be used with MyFavoriteAlbums.

Example of correctly formatted data:

```csv
Year,Ranking,Album,Artist,Rating,Vinyl,EP,Live
1984,1,Hatful of Hollow,The Smiths,10,v,,
2025,1,Too Big for B-Side,Mau P,9,,EP,
2025,2,Need You Tonight EP,Max Styler,9,v,EP,
```

## Navigating the Web Interface

**Audience:** Music enthusiasts using the MyFavoriteAlbums application

**Prerequisites:**

- Access to the MyFavoriteAlbums web interface
- Your album rankings data uploaded to the application

**Steps:**

1. Open your web browser and navigate to the MyFavoriteAlbums web interface.

   > If you're using the public demo, go to https://cholstro.shinyapps.io/shiny-music/

2. Wait for the interface to load.

   > The interface displays the title "My Favorite Albums" at the top and a tabbed interface below.

3. Identify the five main tabs at the top of the interface:

   - _Number One Albums_
   - _Bands and Artists_
   - _Top Albums by Year_
   - _Vinyl_
   - _Band Comparison_

   > **Note:** The interface automatically begins on the "Number One Albums" tab when you first load the page.

4. Click on any tab to navigate to the corresponding section.

   > **Interface elements:** Each tab contains specific controls relevant to that analysis section:
   >
   > - Sliders allow you to select year ranges
   > - Dropdown menus let you choose specific artists or years
   > - Submit buttons apply your selections
   > - Tables and charts display the analysis results

5. To return to a different analysis section at any time, simply click on the corresponding tab at the top of the interface.

## Finding Your Top Albums By Year

**Audience:** Music enthusiasts who want to see their top-ranked albums for specific years

**Prerequisites:**

- Access to the MyFavoriteAlbums web interface
- Your album rankings data uploaded to the application

**Steps:**

1. From the main interface, click on the _Top Albums by Year_ tab.

2. Locate the _Choose a year:_ dropdown menu.

3. Click on the dropdown menu to reveal a list of years from your album rankings data.

4. Select a specific year from the dropdown list.

   > The years shown are based on the data in your CSV file.

5. Click the _Submit_ button to apply your selection.

6. Review the displayed table showing all albums from the selected year, sorted by your rankings.

   > The table includes the following columns: Ranking, Album, and Artist.

7. To view a different year, return to step 3 and select a new year from the dropdown.

## Analyzing Artist Discographies

**Audience:** Music enthusiasts who want to examine all albums by a specific artist

**Prerequisites:**

- Access to the MyFavoriteAlbums web interface
- Your album rankings data uploaded to the application

**Steps:**

1. From the main interface, click on the _Bands and Artists_ tab.

2. Locate the _Choose a band or artist:_ dropdown menu.

3. Click on the dropdown menu to reveal an alphabetical list of all artists in your collection.

4. Select an artist from the dropdown list.

5. Click the _Submit_ button to apply your selection.

6. Review the displayed information:

   - A table showing all albums by the selected artist, including the year and your rating
   - Text showing the total number of albums ranked for this artist
   - Text showing the average rating across all albums by this artist

7. To analyze a different artist, repeat steps 3-5 with a new selection.

## Comparing Artists

**Audience:** Music enthusiasts who want to compare ratings between two artists

**Prerequisites:**

- Access to the MyFavoriteAlbums web interface
- Your album rankings data uploaded to the application

**Steps:**

1. From the main interface, click on the _Band Comparison_ tab.

2. Locate the _First band or artist:_ dropdown menu.

3. Select the first artist you want to compare.

4. Locate the _Second band or artist:_ dropdown menu.

5. Select the second artist you want to compare.

   > The comparison updates automatically without needing to click a submit button.

6. Examine the line chart that appears:

   - The horizontal x-axis represents years
   - The vertical y-axis represents your ratings (0-10)
   - The red line shows ratings for the first artist
   - The blue line shows ratings for the second artist
   - Each point represents an individual album

7. Look for patterns in your ratings:

   - Which artist consistently receives higher ratings?
   - How have your ratings for each artist changed over time?
   - Are there years where one artist significantly outperformed the other?

8. To compare different artists, simply select new options from either dropdown menu.

## Exploring Your Vinyl Collection

**Audience:** Music enthusiasts who want to analyze their vinyl collection

**Prerequisites:**

- Access to the MyFavoriteAlbums web interface
- Your album rankings data uploaded to the application with vinyl information

**Steps:**

1. From the main interface, click on the _Vinyl_ tab.

2. Review the two main sections that appear:

   - _"Top-rated vinyl that I don't own"_
   - _"Years for which I own the most vinyl"_

3. In the first section, review the table of highly-rated albums (rating 9 or above) that you don't own on vinyl.

   > The "Top-rated vinyl that I don't own" table can help you identify potential vinyl purchases to prioritize.

4. In the second section, examine the table showing which years have the most representation in your vinyl collection.

   > The "Years for which I own the most vinyl" table helps you understand the temporal distribution of your collection.

5. Look for patterns in your vinyl collection:

   - Are there specific eras you collect more heavily?
   - Are there highly-rated albums you might want to add to your collection?

   > **Note:** The information on this tab updates automatically based on your data file, so no user input is required.

## Viewing Number One Albums

**Audience:** Music enthusiasts who want to see their top albums across multiple years

**Prerequisites:**

- Access to the MyFavoriteAlbums web interface
- Your album rankings data uploaded to the application

**Steps:**

1. From the main interface, click on the _Number One Albums_ tab (this is typically the default tab when opening the application).

2. Locate the _Choose the Years_ slider near the top of the page.

3. Adjust the slider to select your desired year range:

   - Click and drag the left handle to set the starting year
   - Click and drag the right handle to set the ending year

   > **Note:** The table below automatically updates to show your #1 ranked album for each year in the selected range as you adjust the slider.

4. Review the table, which contains the following columns:

   - Year
   - Album
   - Artist

   > This view allows you to quickly see how your top preferences have evolved over time.

5. To change the year range, simply adjust the slider again.

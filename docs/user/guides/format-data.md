## Formatting Your Album Rankings Data<!-- {docsify-ignore} -->

Before you can analyze your album rankings, you need to prepare your data in the correct format.

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

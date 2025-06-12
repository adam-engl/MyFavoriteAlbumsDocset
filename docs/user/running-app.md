## The Tools and Environment

MyFavoriteAlbums operates within a specific technical environment:

### Required Software

The application is built on:

- **R**: A powerful data analysis system
- **Shiny**: A framework for creating interactive web applications
- **Various R packages**: Specialized tools for data manipulation and visualization

## Understanding the Application's Organization

The MyFavoriteAlbums interface is organized into five thematic tabs, each providing a different analytical perspective:

### 1. Number One Albums

This section focuses on your highest-ranked albums across different years, allowing you to see how your top preferences have evolved over time.

### 2. Bands and Artists

This artist-centric view gathers all albums by a single artist, showing their presence in your collection and your overall evaluation of their work.

### 3. Top Albums by Year

This chronological perspective shows all ranked albums from a specific year, providing a snapshot of your musical preferences at that point in time.

### 4. Vinyl

This collection-focused section analyzes your vinyl ownership, highlighting highly-rated albums you don't own and the years most represented in your collection.

### 5. Band Comparison

This comparative view places two artists side by side, visualizing how their ratings in your collection compare across time.

## Formatting Your Album Rankings Data

To see your data in the MyFavoriteAlbums application:

- If you're using the public demo, you cannot upload your own data (the demo uses sample data)
- To use your own data, you need to download and run the R code locally:
  - Download the MyFavoriteAlbums code from the [repository](https://github.com/UW-Example-Student/MyFavoriteAlbums)
  - Place your `album-rankings.csv` file in the `data` folder
  - Run the application using R and RStudio
  - Your personal album data will now appear in the application

Your data is now ready to be used with MyFavoriteAlbums.

> Note: To see an in-depth guide on how to format your data, refer to the [Format Your Data](guides/format-data.md) section.

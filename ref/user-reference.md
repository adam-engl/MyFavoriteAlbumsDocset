# MyFavoriteAlbums User Reference Guide

## CSV Data Schema Reference

### Overview

This reference describes each field in the album-rankings.csv file required by MyFavoriteAlbums.

### File Format

- **File Type:** CSV (Comma Separated Values)
- **Encoding:** UTF-8
- **Header Row:** Required
- **File Name:** Must be exactly `album-rankings.csv`

### Field Definitions

| Field       | Type   | Required | Description                                                                         | Example         |
| ----------- | ------ | -------- | ----------------------------------------------------------------------------------- | --------------- |
| **Year**    | Number | Yes      | The year the album was released. Must be a 4-digit year.                            | 2023            |
| **Ranking** | Number | Yes      | The album's rank within its release year. Must start at 1 for each year.            | 1               |
| **Album**   | Text   | Yes      | The full album title. Include punctuation and capitalization as shown on the album. | "OK Computer"   |
| **Artist**  | Text   | Yes      | The band or musician name. Use consistent spelling throughout.                      | "Radiohead"     |
| **Rating**  | Number | Yes      | Your rating for the album on a 0-10 scale. Can include decimals.                    | 9.5             |
| **Vinyl**   | Text   | No       | Enter "v" if you own this album on vinyl. Leave blank otherwise.                    | "v" or blank    |
| **EP**      | Text   | No       | Enter "EP" if this is an extended play release. Leave blank otherwise.              | "EP" or blank   |
| **Live**    | Text   | No       | Enter "Live" if this is a live recording. Leave blank otherwise.                    | "Live" or blank |

### Data Rules

#### Year

- Must be between 1900 and current year
- Each year can have multiple albums
- Years don't need to be consecutive

#### Ranking

- Must start at 1 for each year
- Should be consecutive (1, 2, 3...) within each year
- No duplicate rankings within the same year

#### Artist Names

- Be consistent with artist names (e.g., always use "The Beatles" not sometimes "Beatles")
- Include "The" if it's part of the official name
- Use "&" or "and" consistently for collaborations

#### Ratings

- Scale is 0-10, where 10 is best
- Decimals are allowed (e.g., 8.5)
- Ratings are independent of rankings

### Example Data

```csv
Year,Ranking,Album,Artist,Rating,Vinyl,EP,Live
2023,1,Guts,Olivia Rodrigo,9,v,,
1984,1,Hatful of Hollow,The Smiths,10,v,,
2025,1,Too Big for B-Side,Mau P,9,,EP,
2025,2,Need You Tonight EP,Max Styler,9,v,EP,
```

### Common Mistakes to Avoid

- Don't use quotes around text fields unless they contain commas
- Don't skip the Ranking field or leave it blank
- Don't use text like "none" in the Vinyl field - leave it blank
- Ensure Year is a number, not text like "2023-2024"

---

## Frequently Asked Questions

### Getting Started

**Q: What file format does MyFavoriteAlbums accept?**  
A: The application only accepts CSV (Comma Separated Values) files. The file must be named exactly `album-rankings.csv`.

**Q: Can I import data from Spotify or Apple Music?**  
A: No, MyFavoriteAlbums cannot directly import from music streaming services. You need to manually create your CSV file with your album rankings.

**Q: Do I need to rank albums for every year?**  
A: No, you can skip years. Only include years where you have albums to rank.

### Data Entry

**Q: Can I have the same album appear in multiple years?**  
A: No, each album should only appear once in your data, in its original release year.

**Q: What if two albums have the same rating?**  
A: That's fine! Ratings and rankings are independent. You might rate two albums 9/10 but rank one as #2 and another as #3 for their respective years.

**Q: How do I handle compilation albums or greatest hits?**  
A: Treat them like any other album, using the year they were released as a compilation.

**Q: Can I change rankings after I've created my file?**  
A: Yes, simply edit your CSV file and reload it. The application will use the updated data.

### Using the Application

**Q: Why don't I see all my artists in the dropdown menu?**  
A: The dropdown only shows artists that appear in your CSV file. Check your spelling and make sure the data uploaded correctly.

**Q: Can I compare more than two artists at once?**  
A: No, the Band Comparison feature only supports comparing two artists at a time.

**Q: Why does the vinyl analysis show albums I own?**  
A: The "missing vinyl" table only shows albums rated 9 or higher that don't have "v" in the Vinyl column. Check your data entry.

### Troubleshooting

**Q: The application shows a blank screen or error. What should I do?**  
A: Check that:

1. Your file is named exactly `album-rankings.csv`
2. Your CSV has all required columns with exact spelling
3. There are no empty rows in your data
4. Rankings start at 1 for each year

**Q: Some of my data isn't showing up correctly. How do I fix it?**  
A: Common issues include:

- Extra spaces in artist names (e.g., "The Beatles " vs "The Beatles")
- Inconsistent artist naming across entries
- Missing required fields like Year or Ranking
- Text in number fields (Year, Ranking, Rating must be numbers)

**Q: Can I use special characters in album or artist names?**  
A: Yes, but be careful with commas. If an album title contains a comma, make sure your CSV properly handles it (usually by enclosing the field in quotes).

### Data Management

**Q: How many albums can I include?**  
A: There's no hard limit, but very large datasets (thousands of albums) may cause slower performance.

**Q: Can I share my rankings with friends?**  
A: You can share your CSV file with others. They can use it with their own instance of MyFavoriteAlbums.

**Q: Is my data stored online?**  
A: No, MyFavoriteAlbums only uses the data during your session. Your rankings remain private unless you choose to share your CSV file.

### Advanced Features

**Q: Can I add custom fields to track more information?**  
A: The application only recognizes the standard fields. Additional columns in your CSV will be ignored.

**Q: Can I export visualizations or reports?**  
A: You can take screenshots of charts and tables, but there's no built-in export feature.

**Q: Can I filter by genres or decades?**  
A: The application doesn't support genre filtering, but you can use the year-based features to explore by decade.

---

## UI Controls Quick Reference

### Number One Albums Tab

- **Year Slider**: Drag handles to select year range
- **Table**: Shows top album for each year automatically

### Bands and Artists Tab

- **Artist Dropdown**: Select from alphabetical list
- **Submit Button**: Click to view artist's albums
- **Results**: Table of albums, total count, average rating

### Top Albums by Year Tab

- **Year Dropdown**: Select specific year
- **Submit Button**: Click to view year's albums
- **Results**: Ranked list of albums for that year

### Vinyl Tab

- **No controls**: Automatically shows missing vinyl and vinyl by year
- **Missing Vinyl**: Albums rated 9+ you don't own
- **Years Table**: Which years have most vinyl in collection

### Band Comparison Tab

- **Two Dropdowns**: Select two artists to compare
- **Chart**: Updates automatically, no button needed
- **Red Line**: First artist's ratings over time
- **Blue Line**: Second artist's ratings over time

---

## Error Messages Guide

| Error                       | Cause                                  | Solution                                    |
| --------------------------- | -------------------------------------- | ------------------------------------------- |
| "File not found"            | CSV file missing or misnamed           | Ensure file is named `album-rankings.csv`   |
| "Unexpected columns"        | Missing required columns               | Check all column headers match exactly      |
| "No data to display"        | Empty CSV or filter returns no results | Verify CSV contains data and check filters  |
| "Invalid year"              | Non-numeric year values                | Ensure all years are 4-digit numbers        |
| "NA introduced by coercion" | Text in number fields                  | Check Rating, Year, and Ranking are numbers |

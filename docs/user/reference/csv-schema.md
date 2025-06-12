## CSV Data Schema Reference <!-- {docsify-ignore-all} -->

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

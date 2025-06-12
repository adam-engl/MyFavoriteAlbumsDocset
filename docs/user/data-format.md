### Data Format

Your music information is stored in a CSV (Comma Separated Values) file, which is a simple text file that can be opened in Excel or any text editor. Each row represents one album, and the columns are:

- **Year**: The release year (e.g., 2024)
- **Ranking**: The album's position that year (1, 2, 3, etc.)
- **Album**: The album title
- **Artist**: The band or musician name
- **Rating**: Your score from 0-10
- **Vinyl**: "v" if you own it on vinyl, blank if not
- **EP**: "EP" if it's an extended play, blank if not
- **Live**: "Live" if it's a live recording, blank if not

For example, your CSV file might look like:

```csv
Year,Ranking,Album,Artist,Rating,Vinyl,EP,Live
2023,1,Guts,Olivia Rodrigo,9,v,,
1984,1,Hatful of Hollow,The Smiths,10,v,,
2025,1,Too Big for B-Side,Mau P,9,,EP,
2025,2,Need You Tonight EP,Max Styler,9,v,EP,
```

## Underlying Data Model

To fully understand MyFavoriteAlbums, it's helpful to understand how your music information is organized:

Each album in your collection is represented as a single record with multiple attributes:

- **Identification**: Album title and artist name
- **Temporal**: Release year
- **Evaluation**: Your ranking and rating
- **Collection**: Vinyl ownership, EP status, live status

This comprehensive record allows for rich analysis across multiple dimensions.

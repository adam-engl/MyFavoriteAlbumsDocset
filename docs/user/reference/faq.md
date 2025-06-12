## Frequently Asked Questions <!-- {docsify-ignore-all} -->

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

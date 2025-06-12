## Error Messages Guide <!-- {docsify-ignore-all} -->

| Error                       | Cause                                  | Solution                                    |
| --------------------------- | -------------------------------------- | ------------------------------------------- |
| "File not found"            | CSV file missing or misnamed           | Ensure file is named `album-rankings.csv`   |
| "Unexpected columns"        | Missing required columns               | Check all column headers match exactly      |
| "No data to display"        | Empty CSV or filter returns no results | Verify CSV contains data and check filters  |
| "Invalid year"              | Non-numeric year values                | Ensure all years are 4-digit numbers        |
| "NA introduced by coercion" | Text in number fields                  | Check Rating, Year, and Ranking are numbers |

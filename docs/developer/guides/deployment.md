## Deploying the Application<!-- {docsify-ignore} -->

**Prerequisites:**

- Completed and tested MyFavoriteAlbums application
- [shinyapps.io](https://www.shinyapps.io/) account (for shinyapps.io deployment)

**Steps:**

1. Create a free account on shinyapps.io:

   a. Go to https://www.shinyapps.io/

   b. Sign up for a free account

2. Navigate back to RStudio and install the rsconnect package in the console:

   ```r
   install.packages("rsconnect")
   ```

3. Configure your account in RStudio:

   a. Click on _Tools_ → _Global Options_ → _Publishing_.

   b. Click _Connect_.

   c. Select _shinyapps.io_.

   d. Follow the instructions to authorize RStudio.

4. Ensure your data file is correctly located in the project:

   - The CSV file should be in the `data` directory
   - The path in your code should be relative: `data/album-rankings.csv`

5. Open the main app.R file in RStudio.

6. Click the _Publish_ button in the top-right corner of the editor.

7. In the dialog that appears:

   a. Select all files in your project (app.R, app_ui.R, app_server.R, etc.).

   b. Make sure to include the data directory.

   c. Provide a name for your application.

   d. Click _Publish_.

   > **Note:** RStudio will package and upload your application to shinyapps.io. When the upload is complete, your browser will open showing your deployed application.

8. Share the URL with others to give them access to your application.

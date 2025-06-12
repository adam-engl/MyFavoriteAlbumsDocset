## Setting Up Your Development Environment

**Audience:** Developers with some programming experience who want to work with the MyFavoriteAlbums codebase

**Prerequisites:**

- Basic familiarity with programming concepts
- System with administrator access to install software

**Steps:**

1. Install R on your system:

   a. Go to https://cran.r-project.org/.

   b. Select your operating system (Windows, macOS, or Linux).

   c. Download and install the latest version of R.

2. Install RStudio Desktop:

   a. Go to https://posit.co/download/rstudio-desktop/.

   b. Download and install the appropriate version for your operating system.

3. After installation is complete, launch RStudio.

4. Install the required R packages by running the following commands in the RStudio console:

   ```r
   install.packages("shiny")
   install.packages("dplyr")
   install.packages("ggplot2")
   install.packages("DT")
   ```

   > Wait for each package to download and install before proceeding.

5. Clone or download the MyFavoriteAlbums repository:

   - If using Git: `git clone https://github.com/UW-Example-Student/MyFavoriteAlbums`.
   - If downloading manually: Extract the ZIP file to your preferred location.

6. In RStudio, select _File_ → _Open Project_ and navigate to the MyFavoriteAlbums directory.

   > Alternatively, select _File_ → _Open File_ and navigate to the app.R file.

7. Verify your setup by running the application:

   a. In RStudio, with app.R open, click the _Run App_ button in the top-right corner of the editor.

   > The Shiny application should launch in a new window or in your web browser.

Your development environment is now ready to work with MyFavoriteAlbums.

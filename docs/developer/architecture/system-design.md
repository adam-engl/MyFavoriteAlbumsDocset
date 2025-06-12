## System Architecture

MyFavoriteAlbums follows a modular architecture with three distinct layers:

### 1. Data Layer <!-- {docsify-ignore} -->

At the foundation is a single CSV data store containing album information in a denormalized format. This approach prioritizes simplicity and ease of analysis over normalization, allowing for straightforward filtering operations without complex joins.

_Note: This design choice is a trade-off common in data architecture. In relational database design, data would be normalized into separate tables (e.g., Albums, Artists, Years) to reduce redundancy. However, the denormalized approach used here simplifies data access and analysis operations at the cost of some data duplication._

### 2. Analysis Layer <!-- {docsify-ignore} -->

The middle layer consists of R functions organized into thematic modules, each handling a specific analysis domain:

- Artist-centric analysis (albums_by_band.R)
- Year-based analysis (albums_by_year.R)
- Collection analysis (vinyl.R)
- Comparative analysis (compare_bands.R)
- Ranking analysis (number_one_albums.R)

These functions transform the raw data into meaningful information through filtering, aggregation, and calculation operations.

### 3. Presentation Layer <!-- {docsify-ignore} -->

The top layer is a Shiny web application that provides interactive access to the analysis functions. It follows the standard Shiny pattern of separated UI and server components:

- The main application entry point (app.R)
- The UI component (app_ui.R) defines the visual structure and input controls
- The server component (app_server.R) handles the logic that connects user inputs to analysis functions

## Component Relationships

Understanding how components interact is crucial to comprehending the system:

### Module Dependencies <!-- {docsify-ignore} -->

```
app.R
 ├── app_ui.R (defines the user interface structure)
 ├── app_server.R (defines the application logic)
 ├── albums_by_band.R (artist analysis functions)
 ├── albums_by_year.R (year analysis functions)
 ├── number_one_albums.R (ranking analysis functions)
 ├── vinyl.R (collection analysis functions)
 └── compare_bands.R (comparative analysis functions)
```

Each module accesses the central data source but operates independently within its domain.

### Data Flow <!-- {docsify-ignore} -->

1. Raw data is loaded from CSV into memory.
2. Analysis functions filter and transform this data.
3. The Shiny server connects user inputs to analysis functions.
4. Results flow back to the UI for presentation.

## Technical Environment

MyFavoriteAlbums exists within an ecosystem of tools and technologies:

### R Ecosystem <!-- {docsify-ignore} -->

The application leverages several key components of the R ecosystem:

- Base R for data structures and core functionality
- dplyr for data manipulation and transformation
- ggplot2 for visualization construction
- Shiny for interactive web application capabilities

### Application Structure <!-- {docsify-ignore} -->

The application structure follows conventional patterns:

- A main entry point (app.R)
- Separated UI and server components
- Modular function libraries
- A centralized data source

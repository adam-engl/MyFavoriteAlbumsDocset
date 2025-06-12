# Doc Plan: My Favorite Albums Data Analysis Software

## Executive Summary

My Favorite Albums is an R-based data analysis software that allows users to track, analyze, and visualize annual rankings of favorite music albums. The software consists of a Shiny web application with a tabbed interface that displays album data in various views, including rankings by year, artist information, and vinyl collection analysis. Users can filter data, compare bands, and explore top-rated albums across multiple years.

This docset aims to provide comprehensive guidance for both developers who want to understand and extend the codebase, and end users who want to use the application to analyze their own music collections. For developers, it will explain the code structure, data models, and how to modify or add new functionality. For end users, it will provide instructions on data formatting, interface navigation, and performing common analysis tasks.

The scope of this documentation includes conceptual overviews, task-oriented instructions, and reference documentation for all existing features of My Favorite Albums. It will not cover Shiny app deployment to production environments, advanced R programming concepts beyond what's used in the application, or database administration.

## Audiences

This documentation set targets two primary audiences:

**Developers**: These are individuals with some programming experience who want to understand the codebase, use the functions in the software, and potentially extend its functionality. They likely have basic knowledge of R programming but may not be familiar with Shiny web applications or data analysis libraries like dplyr. They need detailed information about code organization, function descriptions, and implementation examples to effectively modify or enhance the software.

**End Users**: These are music enthusiasts who want to use the software to analyze their album collections. Their technical expertise varies—they may have basic familiarity with data formats like CSV but little to no programming experience. They need clear instructions on how to format their music data, navigate the interface, and interpret the various analyses and visualizations presented by the application.

Content for these audiences will be separated, with developer documentation focusing on code examples and technical implementation details, while end-user documentation will emphasize data preparation, UI navigation, and interpretation of results. Each document will clearly indicate its intended audience to help users quickly find relevant information.

## Proposed Documentation Set

### Conceptual Topics for Developers

- **My Favorite Albums Architecture Overview**: Explains the overall structure of the application, including the relationship between app.R, app_ui.R, and app_server.R, and how these components work together in the Shiny framework.
- **Data Model**: Describes the structure of the album ranking data, including the CSV schema and how it's processed in the application.
- **Function Modules Overview**: Introduces the organization of code into separate R files (albums_by_band.R, albums_by_year.R, etc.) and how they provide functionality for different tabs.
- **UI Components and Layout**: Explains the tabbed interface structure and how UI elements are generated and updated dynamically.
- **Reactivity in My Favorite Albums**: Describes how the application handles user input and updates outputs reactively.

### Task Topics for Developers

- **Setting Up the Development Environment**: Instructions for installing R, RStudio, and required packages.
- **Understanding the Data Pipeline**: How data flows from the CSV through filtering functions to UI elements.
- **Implementing a New Analysis Tab**: Step-by-step guide to adding a new tab with custom functionality.
- **Creating Custom Visualizations**: How to add new chart types using ggplot2.
- **Adding Data Import/Export Features**: Guidelines for extending the application to support additional data formats.
- **Debugging Shiny Reactivity Issues**: Troubleshooting techniques for common reactivity problems.

### Reference Topics for Developers

- **Function Reference**: Comprehensive documentation of all functions in the application, including parameters and return values.
- **UI Component Reference**: Details on the UI components and their properties.
- **CSV Data Schema Reference**: Complete specification of the CSV format with field definitions.
- **Package Dependencies**: List of all required R packages with version information.
- **Common Code Patterns**: Examples of frequently used patterns in the codebase.

### Conceptual Topics for End Users

- **Introduction to My Favorite Albums**: Overview of what the software does and its key features.
- **Understanding the Five Tabs**: Description of Number One Albums, Bands and Artists, Top Albums by Year, Vinyl, and Band Comparison tabs.
- **Album Ranking Concepts**: Explanation of the rating system and how rankings work.
- **Data Organization**: How album data is structured and relationships between artists, albums, and years.

### Task Topics for End Users

- **Preparing Your Album Rankings Data**: How to format your own album rankings in CSV format.
- **Navigating the User Interface**: How to move between tabs and use various controls.
- **Finding Number One Albums by Year Range**: Using the slider to see top albums across years.
- **Exploring an Artist's Discography**: How to select and view information about specific bands.
- **Comparing Bands Over Time**: Instructions for using the band comparison chart.
- **Analyzing Your Vinyl Collection**: How to use the vinyl analysis features.
- **Finding Top Albums for a Specific Year**: Using the year selection feature.

### Reference Topics for End Users

- **CSV Field Definitions**: Description of each field in the albums-rankings.csv file.
- **UI Controls Reference**: Quick reference for all buttons, sliders, and selectors in the interface.
- **Troubleshooting**: Solutions to common user problems.
- **FAQs**: Answers to frequently asked questions about data formatting and analysis.
- **Glossary**: Definitions of music and software terminology.

## Deliverables and Schedule

| Date           | Document                                     | Writer | Reviewer | Dependencies                |
| -------------- | -------------------------------------------- | ------ | -------- | --------------------------- |
| April 30, 2025 | First draft of developer conceptual docs     | Adam   | Chris    | Initial code review         |
| April 30, 2025 | First draft of end user conceptual docs      | Adam   | Chris    | Software testing            |
| May 4, 2025    | Final draft of developer conceptual docs     | Adam   | Chris    | Feedback on first draft     |
| May 4, 2025    | Final draft of end user conceptual docs      | Adam   | Chris    | Feedback on first draft     |
| May 9, 2025    | First draft of developer task docs           | Adam   | Chris    | Completed conceptual docs   |
| May 9, 2025    | First draft of end user task docs            | Adam   | Chris    | Completed conceptual docs   |
| May 16, 2025   | Final draft of developer task docs           | Adam   | Chris    | Feedback on first draft     |
| May 16, 2025   | Final draft of end user task docs            | Adam   | Chris    | Feedback on first draft     |
| May 20, 2025   | First draft of reference docs                | Adam   | Chris    | Completed task docs         |
| May 27, 2025   | Final draft of reference docs                | Adam   | Chris    | Feedback on first draft     |
| June 4, 2025   | Initial doc set organization and preparation | Adam   | Chris    | All completed documents     |
| June 11, 2025  | Final doc set publishing and reflection      | Adam   | Chris    | Completed documentation set |

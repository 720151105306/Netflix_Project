# Netflix Dashboard -- Power BI Project

## Project Overview

This project presents an interactive **Power BI dashboard** built using
the *Netflix Movies and TV Shows* dataset. The dashboard provides
insights into Netflix's content library through visual analysis of
genres, ratings, release trends, and country-wise distribution.

The goal of this project is to help users understand how Netflix's
content has grown over time, what types of titles are most common
(Movies vs TV Shows), and how ratings and countries contribute to
Netflix's overall catalog. This dashboard serves as a strong portfolio
addition for data analytics and BI learners.

## Build the Dashboard --- Step by Step

### 1. Get the Data

-   Download the **Netflix Movies and TV Shows** dataset from Kaggle (or
    any reliable source).

### 2. Create a New Power BI File

-   Open **Power BI Desktop**.
-   Go to **Get Data → Text/CSV**.
-   Load the Netflix CSV file.

### 3. Clean & Transform (Power Query)

-   Remove empty rows and unnecessary columns.
-   Convert **Date Added** to Date format.
-   Split multi-value fields like **Country** and **Cast** into rows
    (optional).
-   Trim text, remove duplicates.
-   Fill missing values for **Release Year**.
-   Click **Close & Apply**.

### 4. Data Model

-   Verify table relationships (usually only one table required).

### 5. Add Key DAX Measures

``` dax
1. Total Shows
Total Shows = COUNTROWS('Netflix')
2. Total Movies
Total Movies = CALCULATE(COUNTROWS('Netflix'), 'Netflix'[type] = "Movie")
3. Total TV Shows
Total TV Shows = CALCULATE(COUNTROWS('Netflix'), 'Netflix'[type] = "TV Show")
4. Titles Added by Year
Titles Added = COUNT('Netflix'[show_id])

```

### 7. Design Visuals

These visuals below represent the actual charts included in your PBIX file:

 -   KPI Cards:Total Titles,Total Movies,Total TV Shows,Total Countries
 -   Donut Chart – Movies vs TV Shows
        Shows the percentage split of Movie and TV Show titles.
 -   Bar Chart – Genre-wise Content Count
        Displays top genres like:
 -   Column Chart – Rating Distribution
       Shows count of titles under ratings:
 -   Map Visual – Titles by Country
       A world map showing which countries produce the most Netflix content.
 -   Line Chart – Titles Added by Year
       Trend of how many titles Netflix added each year.
 -   licers / Filters
        dashboard includes slicers for:Type (Movie / TV Show), 

### 8. Interactivity & Formatting

-   Add cross-filtering.
-   Sync slicers.
-   Add tooltips.
-   Use consistent colors, titles, and formatting.

### 9. Performance & Validation

-   Validate slicer functionality.
-   Remove unused columns.
-   Disable Auto Date/Time if unnecessary.

### 10. Export & Documentation

-   Save file as **Netflix_Dashboard.pbix**.
-   Capture dashboard screenshots.
-   Prepare README and other files.


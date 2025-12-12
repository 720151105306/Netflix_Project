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
-   Create lookup tables (Ratings, Country) if needed.

### 5. Create Calculated Columns / Extracts

``` dax
YearAdded = YEAR('Netflix'[Date Added])
```

### 6. Add Key DAX Measures

``` dax
Total Titles = COUNTROWS('Netflix')
Movies Count = CALCULATE([Total Titles], 'Netflix'[Type] = "Movie")
TV Shows Count = CALCULATE([Total Titles], 'Netflix'[Type] = "TV Show")
Titles by Rating = COUNT('Netflix'[Rating])
```

### 7. Design Visuals

-   **Slicers:** YearAdded, Country, Type, Rating\
-   **Cards:** Total Titles, Movies Count, TV Shows Count\
-   **Donut / Bar Chart:** Type vs Rating\
-   **Line Chart:** Year-wise trend\
-   **Map:** Country distribution\
-   **Bar Chart:** Top genres/directors\
-   **Table:** Title, Type, Release Year, Rating, Country

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

## Prepare Repository Files

-   **README.md**
-   **Netflix_Dashboard.pbix**
-   **/screenshots** (dashboard images)
-   **/data** (optional sample CSV or Kaggle link)
-   **DAX_examples.md**
-   **LICENSE**

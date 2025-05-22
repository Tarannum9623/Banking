# Geospatial Analysis of Air Pollution, Population Density, and Literacy Patterns in India

## Overview
This repository contains a comprehensive report and supporting files for the study **"Geospatial Analysis of Air Pollution, Population Density, and Literacy Patterns in India"** by Tarannum (Enrol. No. 24565018). The project investigates the interplay between air quality, population density, and literacy rates across Indian districts using geospatial techniques, correlation analysis, and comparative visualizations.

---

## Process flow:
1.  **Load and Initial Inspection:** The 'India_indicators.csv' dataset is loaded into a pandas DataFrame `df`. Initial rows (`df.head()`) and information (`df.info()`) are displayed to understand the structure and data types. The first row is removed as it appears to be header information.
2.  **Data Cleaning (Air Quality Columns):** The columns 'Air_quality_min', 'Air_quality_mean', and 'Air_quality_range' are identified as relevant for air quality analysis. These columns are converted to numeric type using `pd.to_numeric`, with `errors='coerce'` to turn non-numeric values into `NaN`. Rows with `NaN` values in these crucial columns are dropped using `dropna` to ensure reliable numerical analysis.
3.  **Descriptive Statistics:** Basic descriptive statistics (count, mean, std, min, max, quartiles) are calculated and printed for the cleaned air quality columns to get an overall sense of the air quality distributions.
4.  **Analysis by State:** The data is grouped by 'STATE', and the mean, median, and standard deviation of the air quality metrics are calculated for each state. The results are sorted by the mean 'Air_quality_mean' to easily identify states with the highest and lowest average air quality.
5.  **Analysis by District:** The data is grouped by 'DISTRICT', and the mean of 'Air_quality_mean' is calculated. The top 10 and bottom 10 districts based on mean air quality are identified and printed to pinpoint districts with extreme air quality levels.
6.  **Missing Value Check:** After cleaning, a check for remaining missing values in the key columns is performed and printed.
7.  **Value Counts:** The number of entries per 'STATE' is counted and printed to understand the data distribution across states. For 'DISTRICT', the unique count is printed. If the number of unique districts is not excessively large (threshold set at 50), the value counts for districts are also printed.
8.  **Visualization:**
    *   Histograms are generated for 'Air_quality_min', 'Air_quality_mean', and 'Air_quality_range' to visualize their distributions. KDE (Kernel Density Estimate) lines are added to show the estimated probability density function.
    *   A bar plot is created to visualize the mean 'Air_quality_mean' for each state, sorted in descending order to easily compare states.
    *   Bar plots are generated for the top 10 and bottom 10 districts based on mean air quality.
    *   A bar plot is generated to show the number of entries per state, provided the number of unique states is within a reasonable limit.
9.  **Demographic Distribution Maps:** The `plot_map` function is reused to visualize the spatial distribution of various demographic indicators across all cities, including:
    *   Male population
    *   Female population
    *   Total population aged 0-6 years
    *   Male population aged 0-6 years
    *   Female population aged 0-6 years
    *   Total literates
    *   Male literates
    *   Female literates
    Marker sizes are scaled appropriately for each indicator.
10. **Effective Literacy Rate and Graduates by State:** The average effective literacy rate (total, male, female) and average number of graduates (total, male, female) are calculated for each state by averaging across cities within that state. Horizontal bar plots are generated to compare these average rates/counts across states, allowing comparison of literacy and graduation levels between genders within states and across different states.
11. **Interactive Folium Maps:** Folium is used to create interactive maps. Markers are placed on the map for cities that meet specific criteria:
    *   Cities in Uttar Pradesh.
    *   Cities with total graduates above 100,000.
    *   Cities with total effective literacy rate above 90.
    *   Cities with female literates above 160,000.
    *   Cities with male literates above 160,000.
    *   Cities with total literates above the mean.
    *   Cities with total population aged 0-6 years above 50,000.
    *   Cities with male population aged 0-6 years above 50,000.
    *   Cities with female population aged 0-6 years above 50,000.
    *   Cities with total population above 2,000,000.
    *   Cities with male population above 2,000,000.
    *   Cities with female population above 2,000,000.
    *   Cities with female graduates above 200,000.
    *   Cities with male graduates above 200,000.
    *   Cities with child sex ratio above 950.
    *   Cities with sex ratio above 980.


---

## Dataset Used
The analysis relies on district-level data from the **India Indicators** dataset, which includes:
- **Dataset Link**: [Insert link to the dataset here if publicly available; otherwise, describe how to access it.].

## Key Findings
1. **Population-Pollution Relationship**:  
   - Strong positive correlation between population density and AQI.  
   - Top 5 most polluted districts house **8.7% of India’s population**.

2. **Literacy-Pollution Paradox**:  
   - Urban districts in the top literacy quartile show **34% higher AQI**.  
   - Possible drivers: Concentration of educational infrastructure and higher vehicle ownership.

3. **Gender Dimensions**:  
   - Pollution hotspots exhibit a **43% smaller literacy gender gap** (Table 1).  
   - Female literacy is more sensitive to pollution effects, likely mediated by urban employment opportunities.

---

## Acknowledgments
The author thanks **Prof. Abhishek Samantray (DAL-588 Instructor)** for providing data and guidance.

---

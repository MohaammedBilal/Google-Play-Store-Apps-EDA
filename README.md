# Google Playstore Apps Exploratory Data Analysis (EDA)

This repository contains an exploratory data analysis (EDA) of the Google Playstore Apps dataset. The goal of this project is to understand app characteristics, popularity, and trends through data cleaning, transformation, and visualization.

## Table of Contents:

- [About the Data]
- [Task](#task)
- [Libraries Used](#libraries-used)
- [Data Loading and Inspection](#data-loading-and-inspection)
- [Data Preprocessing and Univariate Analysis](#data-preprocessing-and-univariate-analysis)
- [Key Questions and Analysis](#key-questions-and-analysis)
- [Conclusion](#conclusion)

## About the Data

The dataset contains detailed information about over 600,000 Android applications listed on the Google Play Store.

- **Total Records:** 600K+ apps
- **Source:** [Google Play Store Apps Dataset on Kaggle](https://www.kaggle.com/datasets/gauthamp10/google-playstore-apps)

## Task

The task was to perform a detailed Exploratory Data Analysis (EDA) on this dataset to understand the data, identify and fix issues like missing values and inconsistent formats, and uncover important patterns and insights through analysis and visualization.

## Libraries Used

- `pandas` for data manipulation and analysis
- `numpy` for numerical operations
- `matplotlib.pyplot` for basic plotting
- `seaborn` for enhanced data visualizations
- `warnings` to ignore unnecessary warnings

## Data Loading and Inspection

The dataset was loaded into a pandas DataFrame. Initial inspection revealed:

- The dataset has 2,312,944 rows and 24 columns.
- Columns include 'App Name', 'Category', 'Rating', 'Installs', 'Size', 'Price', and more.
- Several columns had missing values, notably 'Developer Website', 'Privacy Policy', 'Released', 'Rating', and 'Rating Count'.
- No duplicate rows were found.

## Data Preprocessing and Univariate Analysis

The following data preprocessing steps were performed:

- **Handling Missing Values:**
    - Dropped columns deemed irrelevant for the analysis ('Developer Website', 'Privacy Policy', 'Developer Id', 'Developer Email', 'Released').
    - Imputed missing 'Rating' and 'Rating Count' with 0 where one or both were missing or zero.
    - Imputed missing 'Currency' with 'USD' (most frequent).
    - Imputed missing 'Minimum Android' with '4.1 and up' (most frequent).
    - Dropped rows with missing 'App Name'.
    - Converted 'Size' to numeric (MB), handling 'Varies with device' and different units (M, k), and imputed missing values with the median size. A new column 'Size_in_Bytes' was added.
    - Imputed missing 'Installs' and 'Minimum Installs' based on the 'Maximum Installs' value.
- **Data Type Conversion:**
    - 'Last Updated' and 'Scraped Time' columns were converted to datetime objects.
- **Univariate Analysis:**
    - Visualized the distribution of 'Rating', 'Size_in_M', and 'Content Rating'.

## Key Questions and Analysis

Several questions were explored through data analysis and visualization:

1.  **Which apps have the highest number of installs overall?**
    - Identified the top apps based on 'Maximum Installs', showing popular Google system apps dominating.
2.  **How do free vs paid apps compare in terms of total installs?**
    - Visualized that free apps have significantly higher total installs compared to paid apps.
3.  **Is there a correlation between price and number of installs?**
    - Calculated a negligible correlation coefficient for all apps and visualized with scatter plots.
4.  **What are the Top 5 Paid Apps based with highest ratings?**
    - Listed the top 5 paid apps based on their 'Rating'.
5.  **Which categories tend to have the highest-rated apps?**
    - Identified categories with the highest maximum ratings (many categories have apps with a 5.0 rating).
6.  **Distribution of apps percentage with content Rating**
    - Showed the percentage distribution of apps across different content ratings, with 'Everyone' being the dominant category.
7.  **What percentage of apps are ad-supported or offer in-app purchases?**
    - Calculated and displayed the percentage of apps with these monetization strategies.
    - Visualized the distribution across 'Only Ad Supported', 'Only In App Purchases', 'Both', and 'Neither'.
8.  **Is there a relationship between rating and app size?**
    - Calculated a weak positive correlation and visualized with a scatter plot, showing no strong linear relationship.
9.  **How Numeric Attributes Influence Each Other?**
    - Calculated and visualized the correlation matrix for numeric columns, highlighting relationships like the strong correlation between 'Minimum Installs' and 'Maximum Installs'.
10. **How does the average app size vary across different categories?**
    - Calculated and visualized the average app size for each category, showing variations across different app types.
11. **What is the average rating for apps in different categories?**
    - Calculated and visualized the average app rating for each category, revealing differences in average ratings across categories.
12. **What is the correlation between rating count and the number of installs?**
    - Calculated a moderate positive correlation and visualized with a scatter plot (using log scales), indicating that apps with more installs tend to have more ratings.

## Conclusion

This EDA provided valuable insights into the Google Playstore app landscape. We cleaned and transformed the data, handled missing values, and explored relationships between various app attributes. The analysis highlighted the dominance of free apps in terms of installs, the distribution of content ratings and monetization strategies, and the relationships between factors like rating, size, and installs.

This analysis serves as a foundation for further investigation, such as building predictive models or exploring specific category trends in more detail.

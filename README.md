# Netflix Movies and TV Shows Data Analysis

## Project Overview
This project aims to analyze a dataset containing information about Netflix movies and TV shows. The dataset includes various details such as the title, director, cast, country, date added, release year, rating, and duration of each movie or TV show.

## Initial Impressions of the Data
The dataset contains 8807 rows and 12 columns. Out of these 12 columns, one is of `int64` data type and the rest are of `object` type. Upon examining the first 10 rows of the data, it is evident that there are some missing values.

## Data Details
The dataset has missing values in several columns:
- `director`: 2634 missing values
- `cast`: 825 missing values
- `country`: 831 missing values
- `date_added`: 10 missing values
- `rating`: 4 missing values
- `duration`: 3 missing values

## Release Year Summary
The dataset contains information on movies released between the years 1925 and 2021. Here is a summary of the `release_year` column:
- **Count:** The dataset includes 8807 movies.
- **Mean:** The average release year of the movies is approximately 2014.
- **Standard Deviation:** The standard deviation is 8.82, indicating the variability in the release years of the movies.
- **Minimum:** The earliest movie in the dataset was released in 1925.
- **25th Percentile (Q1):** 25% of the movies were released before 2013.
- **Median (Q2):** 50% of the movies were released before 2017.
- **75th Percentile (Q3):** 75% of the movies were released before 2019.
- **Maximum:** The most recent movie in the dataset was released in 2021.

From this summary, we can observe that the majority of the movies in the dataset are relatively recent, with 50% of them released in or after 2017. A significant portion of the dataset consists of movies released in the last decade, with 75% being released in or after 2013 and 25% being released in or after 2019.

## Next Steps
The next version of the analysis will involve removing null values based on the columns rather than on the entire dataset. This approach will help in preserving more data and providing a more accurate analysis.

## Repository Contents
- `Netflix.ipynb`: The Jupyter Notebook containing the initial data analysis.
- `README.md`: This file, providing an overview of the project.

## Acknowledgements
This project utilizes data from Kaggle, which provides a comprehensive view of the movies and TV shows available on their platform.

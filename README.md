# NBA-Data-Analysis-in-R
Exploratory NBA Data Analysis in R

R Bootcamp: Group 19

Authors:
Jan-Hendrik van Lengerich - email jan-hendrik.vanlengerich@stud.hslu.ch
Perez Olusese email - perez.olusese@stud.hslu.ch

# Project Title
Dribbling Through Data: Unveiling NBA Secrets with R

# Introduction
Open the Rmarkdown file in the zipped folder to be able to access the above named project. 

The project is about analysing NBA and city data using Rmarkdown. After learning how to use the R programming language we are required to use the various R functionalties to complete a data analysis and submit the report.

# Contents:

1. ReadMe
2. Rmd-file: R_Bootcamp_Group_19_NBA_2024_final.Rmd
3. CSV-file for NBA stats: NBA_Team_Stats_Cities.csv
4. CSV-file for city data: US_Cities.csv 
5. Image created by DALL-E as title image: NBA_data_analysis_DALL-E.jpg
6. HTML output file (main output file)
7. PDF file containing HTML output (see important note below)

# Data collection

The data we used for this analysis is in the zip folder provided as we submit the assignment. We used two datasets namely:

1. US_Cities.csv 
2. NBA_Team_Stats_Cities.csv

These two primary datasets serve as the basis for our analysis. The first data set, 'NBA_Team_Stats_Cities.csv', provides a comprehensive overview of various NBA teams' performance metrics across different seasons. 
The second data set, 'US_Cities.csv', contains demographic and geographic information about US cities, which are used to contextualize the NBA teams' data based on their location. It enhances the analysis by linking team performance or player efficiency to factors inherent to their home cities.

We applied the following packages:
require(dplyr)
require(tidyr)
require(tinytex)
library(lubridate)
library(ggplot2)
library(reshape2)
library(knitr)
library(kableExtra)
library(tidyverse)
library(summarytools)
library(tseries)
library(forecast)
library(broom)
library(leaflet)

Important steps to replicate the analysis:

- Set the working directory
- Read the respective data sets

# For the US cities data set data preparations:

1. The last two columns of the data set are removed because they are unnecessary for the analysis. This is done by sub-setting all columns except for the last two. 

2. We de-duplicate the city data. This is primarily done to ensure the right cities are linked to the NBA data set because the cities data set may contain multiple entries for each city (possibly representing different administrative divisions). Hence, we group the data by city names, and for each group, it keeps only the first occurrence. This effectively retains the entry for the largest city when cities have the same name.

3. We rename the city column for consistency and to match the naming convention of the NBA data set.

4. Drop last two columns of US cities data

5. De-duplicate us_cities by City, keeping only the first occurrence (largest cities)

6. Match column names

# For the NBA teams dataset:

1. Split the 'Fgm.a', 'X3gm.a', and 'Ftm.a' columns into two separate columns each. These columns contain concatenated data for made and attempted field goals, three-pointers, and free throws, respectively. The separate() function is used to divide these into individual columns for the number of successful attempts ('Fgm', '3gm', 'Ftm') and the total attempts ('Fga', '3ga', 'Fta').

2. Rename the percentage columns for field goals, three-pointers, and free throws from 'Pct', 'Pct.1', and 'Pct.2' to 'Fg.Pct', '3g.Pct', and 'Ft.Pct', respectively, to provide a clearer description of what these percentages represent.

3. Split the 'Fgm.a', 'X3gm.a', and 'Ftm.a' columns

# Joining the data sets

After joining the data sets we proceed with the analysis which is documented in the Rmd file.

Run the code on the descriptive statistics to display the code. The plots will reveal several insights into the nature of the variables under construction.

# Statistical Methods

We employ various statistical methods, such as descriptive stats, correlation stats, regression stats, visual smoothing, ARIMA etc. They are all described in the R code.

# Acknowledgements

Our data and sources are from the following sites.

 - NBA facts and details: https://www.nba.com, https://en.wikipedia.org/wiki/National_Basketball_Association
 - Kaggle datasets for our data - https://www.kaggle.com/datasets

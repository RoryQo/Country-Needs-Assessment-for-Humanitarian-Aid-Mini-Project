# <div align="center">Country Aid Mini Project</div>

## Table of Contents
1. [Overview](#overview)
2. [Results and Conclusions](#results-and-conclusions)
3. [Data](#data)
4. [Methodology/Usage](#methodology/usage)

## Overview
HELP International is a humanitarian non-governmental organization (NGO) committed to alleviating poverty and providing essential relief during disasters and natural calamities. With approximately $10 million raised, the organization aims to strategically allocate these funds to maximize impact in the most vulnerable regions.

This project seeks to categorize countries based on various socio-economic and health indicators, identifying those in greatest need of humanitarian assistance.

## Results and Conclusions
After analyzing the correlation matrix, we found significant relationships among the data, prompting us to proceed with Principal Component Analysis (PCA). The PCA identified several key factors that are crucial in categorizing country development, including **child mortality**, **income**, **life expectancy**, and **health expenditure**.

We created clusters from the PCA results, determining that three clusters is the optimal number. Notably, Partitioning Around Medoids (PAM) clustering outperformed K-means clustering due to its resilience to outliers.

The analysis revealed that Cluster 1 consists of countries that are consistently worse off than those in other clusters. This cluster, comprising 51 countries, represents the primary targets for HELP's initiatives (full list available on the last page of the output pdf). 

Visualizations comparing these key factors—**child mortality**, **income**, **life expectancy**, and **health expenditure**—clearly illustrate the disparities across the clusters. These visualizations were instrumental in determining that Cluster 1 needs the most help, as they show:
- **Child Mortality**: The highest rates of child mortality are found in Cluster 1, highlighting a critical area for intervention.
- **Income**: There is a stark contrast in income levels across clusters, with Cluster 1 having the lowest average income.
- **Life Expectancy**: Life expectancy is significantly lower in Cluster 1 compared to the other clusters, underscoring urgent health needs.
- **Health Expenditure**: The analysis indicates that lower health expenditure correlates with higher child mortality rates in the focus cluster.

These findings underscore the urgent need for targeted interventions in countries identified within Cluster 1.

## Data
- **country**: Name of the country
- **child_mort**: Deaths of children under 5 years of age per 1,000 live births
- **exports**: Exports of goods and services per capita, expressed as a percentage of GDP per capita
- **health**: Total health spending per capita, expressed as a percentage of GDP per capita
- **imports**: Imports of goods and services per capita, expressed as a percentage of GDP per capita
- **income**: Net income per person
- **inflation**: Measurement of the annual growth rate of Total GDP
- **life_expec**: Average number of years a newborn child would live if current mortality patterns persist
- **total_fer**: Average number of children that would be born to each woman if current age-fertility rates remain constant
- **gdpp**: GDP per capita, calculated as Total GDP divided by total population

## Methodology/Usage
To utilize the R code for this project, ensure you have the required packages installed. You can then read the data file, conduct exploratory data analysis, visualize with PCA, and perform clustering to assess the countries' needs.

The workflow includes:
1. Loading necessary libraries (like tidyverse, factoextra, etc.).
2. Reading the dataset.
3. Exploring key predictors through correlation analysis.
4. Visualizing the data with PCA and determining the optimal number of clusters.
5. Applying clustering methods and visualizing the results.
6. Summarizing the countries in the focus cluster for further action.

By following these steps, you can replicate the analysis and determine which countries require urgent humanitarian assistance.

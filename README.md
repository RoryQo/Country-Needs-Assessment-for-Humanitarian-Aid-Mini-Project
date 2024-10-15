# <div align="center">Country Aid Mini Project</div>

## Table of Contents
1. [Overview](#overview)
2. [Project Objectives](#project-objectives)
3. [Results and Conclusions](#results-and-conclusions)
4. [Data Description](#data-description) 
5. [Methodology](#methodology)
6. [Usage Instructions](#usage-instructions)
7. [Visualizations](#visualizations)
8. [Future Work](#future-work)
9. [Contributions](#contributions)
10. [License](#license)

## Overview
HELP International is a humanitarian non-governmental organization (NGO) dedicated to alleviating poverty and providing essential relief during disasters and natural calamities. With approximately $10 million raised, the organization aims to strategically allocate these funds to maximize impact in the most vulnerable regions.

This project categorizes countries based on various socio-economic and health indicators, identifying those in greatest need of humanitarian assistance.

## Project Objectives
- Analyze socio-economic and health data to identify countries requiring urgent aid.
- Use statistical methods, including PCA and clustering, to categorize countries.
- Provide visualizations to communicate findings effectively.

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



## Data Description
The dataset includes the following variables:

- **country**: Name of the country
- **child_mort**: Deaths of children under 5 years of age per 1,000 live births
- **exports**: Exports of goods and services per capita, expressed as a percentage of GDP per capita
- **health**: Total health spending per capita, expressed as a percentage of GDP per capita
- **imports**: Imports of goods and services per capita, expressed as a percentage of GDP per capita
- **income**: Net income per person
- **inflation**: Annual growth rate of Total GDP
- **life_expec**: Average number of years a newborn child would live if current mortality patterns persist
- **total_fer**: Average number of children born to each woman if current age-fertility rates remain constant
- **gdpp**: GDP per capita, calculated as Total GDP divided by total population

## Methodology
1. **Data Preprocessing**: Load the necessary libraries and read the dataset.
2. **Exploratory Data Analysis**: Conduct correlation analysis to identify key predictors.
3. **Principal Component Analysis (PCA)**: Visualize and reduce dimensions of the dataset.
```
country_pc = country %>% 
  select(-country) %>% 
  prcomp(scale = TRUE)

country_pc$x %>% 
  as_tibble() %>%
  select(PC1, PC2) %>% 
  ggplot(aes(x = PC1, y = PC2)) +
  geom_point()
```
5. **Clustering**: Apply K-means and PAM clustering methods to categorize countries.
```
km_mod = kmeans(country_s, centers = 3)
pam_mod = pam(country_s, 3)
```
6. **Statistical Analysis**: Assess significant differences among clusters.

## Usage Instructions
To utilize the R code for this project, follow these steps:

1. Ensure the required packages are installed (e.g., `tidyverse`, `factoextra`, `cluster`).
2. Read the dataset into your R environment.
3. Run the analysis scripts sequentially to replicate the findings.
4. Review the generated visualizations for insights on country categorization.

## Visualizations
The project includes various visualizations to represent data insights, such as:

- Correlation matrices showing relationships among key indicators.
- PCA plots illustrating the portion of variance explained based on principal components.
![Graph 2](https://raw.githubusercontent.com/RoryQo/R-Country-Needs-Assessment-for-Humanitarian-Aid-Mini-Project/main/Graph2.jpg)
- Cluster visualizations comparing characteristics of different groups.
![Graph 1](https://raw.githubusercontent.com/RoryQo/R-Country-Needs-Assessment-for-Humanitarian-Aid-Mini-Project/main/Graph1.jpg)
## Future Work
- Explore additional clustering methods and evaluate their effectiveness.
- Conduct deeper statistical analysis on the socio-economic indicators.
- Expand the dataset to include more countries or additional variables.

## Contributions
Contributions to the project are welcome! Please feel free to submit issues or pull requests.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

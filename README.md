<h1 align="center">Country-Needs-Assessment-for-Humanitarian-Aid-Mini-Project</h1>

<br>


###  Table of Contents
<div align="center">
    <table style="border:none;">
        <tr>
            <td style="border:none;">
                <ol>
                    <li><a href="#context">Context</a></li>
                    <li><a href="#results">Results</a></li>
                </ol>
            </td>
            <td style="border:none;">
                <ol start="3">
                    <li><a href="#data">Data</a></li>
                    <li><a href="#usage">Usage</a></li>
                </ol>
            </td>
        </tr>
    </table>
</div>

### Context
HELP International is an international humanitarian Non-Governmental Organization (NGO) committed to fighting poverty and providing people in underdeveloped countries with basic amenities and relief during disasters and natural calamities.

HELP International has successfully raised around $10 million. Now, the organization needs to decide how to use these funds strategically and effectively. Our task is to categorize countries using various socio-economic and health factors that determine overall development. This will help identify which countries HELP should focus on the most.

### Results
After analyzing the correlation matrix, we found that the data is highly correlated, prompting us to proceed with Principal Component Analysis (PCA). We then created clusters from the PCA results to determine the countries HELP should prioritize. Our analysis indicates that three clusters is the optimal number. Additionally, we observed that Partitioning Around Medoids (PAM) clustering outperformed K-means clustering, as it is more resilient to outliers.

Following the separation of countries into clusters, we developed data visualizations that factor in cluster membership and some key contributors from the PCA, such as child mortality, income, and life expectancy. These visualizations reveal that Cluster 1 is consistently (and statistically significantly) worse off than the other two clusters. The countries in Cluster 1 are the primary targets for HELP’s initiatives. This cluster consists of 51 countries, and a full list is provided on the last page.

### Data
- **`country`**: Name of the country
- **`child_mort`**: Deaths of children under 5 years of age per 1,000 live births
- **`exports`**: Exports of goods and services per capita, expressed as a percentage of GDP per capita
- **`health`**: Total health spending per capita, expressed as a percentage of GDP per capita
- **`imports`**: Imports of goods and services per capita, expressed as a percentage of GDP per capita
- **`income`**: Net income per person
- **`inflation`**: Measurement of the annual growth rate of Total GDP
- **`life_expec`**: Average number of years a newborn child would live if current mortality patterns persist
- **`total_fer`**: Average number of children that would be born to each woman if current age-fertility rates remain constant
- **`gdpp`**: GDP per capita, calculated as Total GDP divided by total population

### Usage
To utilize the R code for this project, ensure you have the required packages installed. You can then read the data file, conduct exploratory data analysis, visualize with PCA, and perform clustering to assess the countries' needs. 

The workflow includes:
1. Loading necessary libraries (like `tidyverse`, `factoextra`, etc.).
2. Reading the dataset.
3. Exploring key predictors through correlation analysis.
4. Visualizing the data with PCA and determining the optimal number of clusters.
5. Applying clustering methods and visualizing the results.
6. Summarizing the countries in the focus cluster for further action.

By following these steps, you can replicate the analysis and determine which countries require urgent humanitarian assistance.


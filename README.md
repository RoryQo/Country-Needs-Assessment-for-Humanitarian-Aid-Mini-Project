# Country-Socioeconomic-Aid-Mini-Project
#### Context
HELP International is an international humanitarian Non-Governmental Organization (NGO) that is committed to fighting poverty and providing the people of backward countries with basic amenities and relief during the time of disasters and natural calamities.

HELP International have been able to raise around $10 million. Now HELP international needs to decide how to use this money strategically and effectively. Hence, our job is to categorize the countries using some socio-economic and health factors that determine the overall development of the country. Then we can suggest the countries which HELP needs to focus on the most.
#### Results

  After visualizing, we can see the data is highly correlated.  Since we have highly correlated data we will continue with Principal component analysis.  From our PCA it appears that life expectancy, child mortality, income, and gdp per capita are among the highest contributors in explaining the variance between countries.  We will create clusters from the PCA to determine the countries HELP should focus on.  From our plot, we can see that 3 is the optimal amount of clusters, and from these clusters, we can see that the PAM clustering is superior to k means clustering, as it is more resilient to the outliers.

+ After only 5 components we reach target proportion explained, after 6 it begins to level off and look like additional components wont add that much explanatory power
#### Data
+ `country` : Name of the country
+ `child_mort` : Death of children under 5 years of age per 1000 live births
+ `exports` : Exports of goods and services per capita. Given as percentage of the GDP per capita
+ `health` : Total health spending per capita. Given as percentage of GDP per capita
+ `imports` : Imports of goods and services per capita. Given as percentage of the GDP per capita
+ `Income` : Net income per person
+ `Inflation` : The measurement of the annual growth rate of the Total GDP
+ `life_expec` : The average number of years a new born child would live if the current mortality patterns are to remain the same
+ `total_fer` : The number of children that would be born to each woman if the current age-fertility rates remain the same
+ `gdpp` : The GDP per capita. Calculated as the Total GDP divided by the total population

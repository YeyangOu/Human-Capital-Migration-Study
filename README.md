## Introduction
This is a personal research project created to study and investigate the migration patterns of different countries in the world with heavy emphasis on developing country. In this project, we investigate the emigrant population to total population ratio, net population change, outbound mobility ratio of 202 different countries, territories, and regions in the world and compare them to the country's GDP per capita to study different countries migration and human capital flight patterns.

Another version of this project is also published on Kaggle: https://www.kaggle.com/datasets/daviddave7100/immigrations-and-emigrations-statistics

## Context of the Research
Immigration and emigration have been a fundamental aspect of human civilization since the beginning of history, shaping societies across the world and influences the cultures, economies, and political landscapes of different countries. People move across different countries for better opportunities, safer environments, more stable political climate, and etc.

According to statistics from World Population Review, countries with the highest amount of emigrants (former residences living abroad) in 2020 are India, Mexico, Russia, China, Syria, Bangladesh, and Pakistan. In particular, both India and China are well known for their influential and diverse overseas communities living abroad. The large presence of Indian and Chinese diasporas communities across the world, especially in North America, created the impressions that large amount of Indian and Chinese are leave their home country, resulting in Human Capital Flight.

However, these studies rarely takes in account of the total population of a country. In fact, when combined, China and India accounts for more than one-third of the world's population. Similarly, many other countries in the list of highest number of emigrants were also home to a large population, such as Bangladesh and Pakistan. The absence of this important factor could create a misleading and inaccurate image of human migration patterns.

Hence in this dataset, we compared the number of immigrants (former residents living internationally) and compare it to the total population of the country to determine the immigrant to total population ratio. Moreover, we also calculated the net change in population of a country from human migration and also compared it to total population of the country. These values would more accurately reflect the human capital migration patterns of different countries.

Another datasets we gathered is the Outbound mobility ratio, which measures the Number of students from a given country studying abroad, expressed as a percentage of total tertiary enrolment in that country, this statistics could in theory reflects the Intellectual Human Capital Migration of a nation.

Lastly, we would also be comparing the GDP per capital of a nation with its emigration to population ratio and Outbound mobility ratio to investigate for any correlation.

## Descriptions of the Datasets
The dataset contains a list of 202 different countries & regions in the world with their total population, number of immigrants, number of emigrants, net change in population from migration, net population change to total population ratio, emigrants to total population ratio and etc.

### Columns
- **Country**: This column lists out the name of the 202 different countries & regions in the world. (Categorical)
- **Population**: Population of the country in 2020. (Numerical)
- **Number of Immigrants**: Number of immigrants living in the country in 2020. (Numerical)
- **Number of Emigrants**: Number of emigrants(former residents living internationally) from the country as of 2020. (Numerical)
- **Emigrants to Population Ratio**: Calculated with (Number of Emigrants/Population)*100. (Numerical)
- **Immigrants to Population Ratio**: Calculated with (Number of Immigrants/Population)*100. (Numerical)
- **Net Population Change of a Country**: Calculated with (Number of Immigrants - Number of Emigrants). (Numerical)
- **Net Population Change to Total Population Ratio**: Calculated with (Number of Immigrants - Number of Emigrants)/Population*100 (Numerical)
- **Outbound mobility ratio**: Number of students from a given country studying abroad, expressed as a percentage of total tertiary enrolment in that country (Numerical)
- **GDP Per Capita**: a country's economic output per person, calculated by dividing the country's gross domestic product (GDP) by its population (Numerical)

## Conclusion and Analysis
Upon comparing the data, we arrive at a few interesting conclusions:

### Emigrants to Population Ratio (EoPR)
The Emigrant to Population Ratio (EoPR) indicates the percentage of people from a country who has emigrated or are living abroad. Although there are more factors to consider, the EoPR can be used as a basic references to measure the human capital flight of a nation.

Countries/regions with some of the highest EoPR includes Tonga, Palestine, Saint Kitts and Nevis, Puerto Rico, Monaco, Dominica, Cook Islands, Bosnia and Herzegovina, and Albania.

Countries/regions with the lowest EoPR to population includes Papua New Guinea, North Korea, Oman, Tanzania, Madagascar, Japan, Maldives, Ethiopia, Nigeria, and China.

China has a EoPR of 0.73%, which is among the top 10 countries with the lowest EoPR. This means the number of Chinese immigrants living abroad are only equivalent to 0.73% of China's total population. As the now second most populous country in the world, it is no surprise China export more immigrants than many other nations. Nevertheless, the percentage of Chinese immigrant who decided to go abroad is rather small compared to many other nations. Similarly, India only has a EoPR of 1.29%, which is lower than most European, South American, and Asian nations. India is the top 25 countries with the lowest EoPR. The results from comparing number of emigrants from a country with the total population of the country showcases the importance of using per capita as an indicator when analyzing datas.

#### Visualization of Emigrants to Population Ratio (EoPR)
Below is a visualization of Emigrants to Population Ratio of different country on a map created using Tableau. Countries with a higher EoPR would appear more red while countries with a lower EoPR would appear more blue.

For a more detailed visualizations in Tableau, visit this link below: https://public.tableau.com/shared/4D8F3N8P9?:display_count=n&:origin=viz_share_link

### Net Population Change to Total Population Ratio (NPTPR)
The Net Population Change to Total Population Ratio (NPTPR) is calculated with the formula (Number of Immigrants - Number of Emigrants)/Population*100 (Numerical).

The introduction of this ratio is to better measures net human capital change of a country from migrations. The EoPR introduced early only takes in account of people who emigrate out of a country but it didn't consider immigrants who came to the country. The NPTPR would better model the human capital shifts of nations in the world.

In theory, a higher NPTPR indicates a nation is experience a net human capital gain from migrations while a lower NPTPR could mean a country is going through a net human capital flight.

Countries and regions with the highest NPTPR are the United Arab Emirates, Vatican City, Qatar, Kuwait, Andorra, Liechtenstein, Bahrain, Guam, Oman, Macau, Saudi Arabia, Singapore, and Luxembourg. Canada, the United States, Australia, the UK, western European countries, and countries on the Arabian Peninsula are popular destinations for immigrants around the world, which explains why they have high NPTPR.

Territories and nations with the lowest NPTPR are Albania, Syria, Grenada, Bosnia and Herzegovina, Guyana, Puerto Rico, Samoa, Tonga, Palestine, Saint Kitts and Nevis, and Dominica.

#### Visualization of Net Population Change to Total Population Ratio (NPTPR)
In this visualization, countries with a higher NPTPR would appear more blue while countries with a lower NPTPR would appear more red.

Link to a More Detailed Version: https://public.tableau.com/shared/9MWBNBTXB?:display_count=n&:origin=viz_share_link

### Investigating Relationship between NPTPR and GDP per Capital Value
One interesting trends with the NPTPR is that nations and territories with a higher GDP per capita tends to have higher NPTPR while those with a lower GDP per capita have a lower NPTPR. We would be investigating for a correlation between these two.

For this, I plotted the NPTPR as the X axis against the GDP per capita of different nations as the Y axis within Python in Jupyter Notebook. The plotted datasets look like this:

There is a weak linear relationship between the two values. This makes sense since countries with a higher GDP per capita tends to attract talents from nations with a lower GDP per capita. By determining the slope and y-intercept of the fitted line, we can arrive at this linear regression model:

Y = 20642.5 + 455.3X

Using statsmodels.api.OLS to evaluate the datasets, we can conlude the Pearson correlation coefficient r≈ 0.437, indicating a moderate linear relationship between them. Moreover, in order to perform linear regression on the datasets, the datasets must satisfy the following 4 assumptions.

1. The average value of the errors are 0.
2. The variance of the errors are constant.
3. The errors are random samples from the normal distribution of zero mean and variance.
4. The errors are independent.

When plotting the regression line, residual verse covariates plot, residual verse fitted_y value plot, and the QQplot, the results from these plots violate 3 of the assumptions above.

Although the datasets display a slight linear patterns, a linear model in the form Y = 20642.5 + 455.3X isn't the most ideal model. For future improvement, one can perform transformations onto the model to create a more fitting model.

The codes and details of these works above can be found in my notebook titled Correlation Between GDP Per Capita and NPTPR posted on Kaggle: https://www.kaggle.com/code/daviddave7100/correlation-between-gdp-per-capita-and-nptpr

### Outbound Mobility Ratio
The previous two ratios, the NPTPR and EoPR, only focuses on the number of immigrants or emigrants of a nation. They don't take in consideration of the education levels or skill gaps of these immigrants. The Outbound Mobility Ratio measures the number of students from a given country studying abroad, expressed as a percentage of total tertiary enrolment in that country.

Our hypothesis is that this ratio could indicate the intellectual human capital flight for developing nations since many international from developing countries studying at developed countries tend to migrate to their country of study. However, the value of outbound mobility ratio won't fully reflect intellectual human capital flight of some countries since richer nations would have more resources and opportunities to send their students abroad.

Countries and regions with the highest Outbound Mobility Ratio are Andorra, Luxembourg, San Marino, Liechtenstein, Turkmenistan, Seychelles, Tonga, Monaco, and Cyprus.

Countries and regions with the lowest Outbound Mobility Ratio are Brazil, Cuba, Japan, Australia, Philippines, Dominican Republic, Mexico, Turkey, United States, and Argentina.

Not all countries have their Outbound Mobility Ratio calculated so there are a lists of countries with their Outbound Mobility Ratio being 0.

#### Visualization of Outbound Mobility Ratio
In this visualization, countries with a higher Outbound Mobility Ratio would appear more red while countries with a lower NPTPR would appear more blue.

Link to a more detailed version: https://public.tableau.com/views/HumanCapitalMigrationStudy/OutboundMobilityRatio?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link

## Citations
- Population by Country - 2020. https://www.kaggle.com/datasets/tanuprabhu/population-by-country-2020/data.
- Top 10 Countries with the Highest Number of Foreign-Born Residents (Immigrants) - United Nations 2020: (n.d.). https://worldpopulationreview.com/country-rankings/immigration-by-country.
- Share of students studying abroad, 2020. https://ourworldindata.org/grapher/share-of-students-studying-abroad?tab=table&time=2020
- GDP per capita, 2020. https://ourworldindata.org/grapher/gdp-per-capita-maddison?time=2020

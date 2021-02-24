# Analysis of the Effectiveness of Face-Coverings on the Death Rate of COVID-19 Using Machine Learning
<img src="https://github.com/alilafzi/corona/blob/main/images/1.png"> <br>
## Project Goal:
The recent outbreak of the COVID-19 shocked humanity leading to the death of millions of people worldwide. To stave off the spread of the virus, the authorities in the US, employed different strategies including the mask mandate (MM) order issued by the states' governors. Although most of the previous studies pointed in the direction that MM can be effective in hindering the spread of viral infections, the effectiveness of MM in reducing the degree of exposure to the virus and, consequently, death rates remains indeterminate. Indeed, the extent to which the degree of exposure to COVID-19 takes part in the lethality of the virus remains unclear. In the current work, we defined a parameter called the average death ratio as the monthly average of the ratio of the number of daily deaths to the total number of daily cases. We utilized survey data provided by New York Times to quantify people's abidance to the MM order. Additionally, we implicitly addressed the extent to which people abide by the MM order that may depend on some parameters like population, income, and political inclination. Using different machine learning classification algorithms we investigated how the decrease or increase in death ratio for the counties in the US West Coast correlates with the input parameters. Our results showed a promising score as high as 0.94 with algorithms like XGBoost, Random Forest, and Naive Bayes. To verify the model, the best performing algorithms were then utilized to analyze other states (Arizona, New Jersey, New York and Texas) as test cases. The findings show an acceptable trend, further confirming usability of the chosen features for prediction of similar cases. 

## Data Description:
We defined the parameter of interest as the average ratio of the number of deaths to the total number of cases, referred to as the death ratio, which can be interpreted as a measure of the severity of the disease. The effective date of the executive orders by the governors, requiring mask mandate at all the counties in the three West Coast states of California, Oregon and Washington has been identified, which is publicly available. We used the average death ratio one month before and after the order to study the mortality rate. The rationale behind this selection is to minimize the effects of other factors that might play role in changing the COVID-19 data. The raw dataset for the daily cases and deaths for all the US counties over time is extracted from the USAFACTS website, where county-level data is confirmed by the state and local agencies directly. After obtaining the daily values of death and case numbers for a month before and after the MM order, we divided the monthly average number of deaths by the monthly average number of cases for each county. Then we found the difference between the death ratio for one month before and after the MM order. Finally, we categorized the variation based on its sign to quantify whether the death ratio increases, decreases, or no change occurs. Out of the 130 samples, 47, 30, and 53 of them belong to the "decrease", "increase", and "no change" classes, respectively. We dropped the "no change" data as they all correspond to small counties, where there were zero reported COVID-19 cases and deaths, leaving 77 counties in total. Consequently, the two categories of increase (denoted by class 0) and decrease (shown by class 1) are remained for the prediction task. In below histogram, we showed the output classes of the data is not biased: <br>
<img src="https://github.com/alilafzi/corona/blob/main/images/BarGraph_Histogram.png" height = 400 width = 400> <br>
Histogram of change in death ratio for the three states <br>

Since it is not known exactly what percentage of population follows the MM order and use face coverings, it is necessary to come up with features that can capture how likely is
an individual to follow the recommended practice. For bridging this gap, four main features are chosen as primary indicators which are listed below:<br>
<ul> <b> 1. County Population: </b> Population in each county is obtained from the most recent surveys for the year 2019. </ul>
<ul> <b> 2. Median Household Income: </b> The income level is the median household in each county in the years 2015-2019.</ul>
<ul> <b> 3. Political Inclination: </b> The data for the political inclination is constructed based on the 2020 US presidential election results</ul>
<ul> <b> 4. Mask Usage based on New York Times Survey: </b> The mask usage from 7/2/2020 to 7/14/2020</ul>
<br>

## Data Resources
<ul> <b> Source 1:</b> USCensus, “United states census bureau.” https://www.census.gov </ul>
<ul> <b> Source 2:</b>  N. Y. Times, “Mask-wearing survey data.” https://github.com/nytimes/covid-19-data/tree/master/mask-use.</ul>
<ul> <b> Source 3:</b> USAFACTS, “Usa coronavirus cases and deaths.” https://usafacts.org/visualizations/coronavirus-covid-19-spread-map/state/oregon. </ul>
<ul> <b> Source 4:</b> POLITICO, “Us 2020 presidential election results.” https://www.politico.com/2020-election/results/president/.</ul>
<br>

## Results:
1. To have an initial assessment of the variation of percent change in the death ratio, we plotted the percent death ratio as functions of population, median income, and percent of the population that frequently uses mask, which has a relatively high correlation coefficient. There is no detectable pattern between parameters of interest and death ratio.<br>
<img src="https://github.com/alilafzi/corona/blob/main/images/all_scatter_2.png" width = 700 height = 800> <br>
2. 
<img src="https://github.com/alilafzi/corona/blob/main/images/BarGraph_Income.png" height = 400 width = 500> <br>
<img src="https://github.com/alilafzi/corona/blob/main/images/BarGraph_Political.png" height = 400 width = 500> <br>
<img src="https://github.com/alilafzi/corona/blob/main/images/BarGraph_Population.png" height = 400 width = 500> <br>
## Conclusion:
In this body of work, we have analyzed the effect of mask covering on the intensity of spread of the COVID-19 virus by considering the death ratio at the county level to be the
primary indicator. To bridge the gap between level of adherence to mask mandate, four main features are used as input data, population, income, political inclination, and the results of the survey on mask usage from New York Times. The change in the death ratio is used as the metric to quantify the effectiveness of face-coverings on the COVID-19 spread. After extracting and refining the data-set from reliable sources, we analyzed the information using 9 different algorithms. Among all the methods used, Random Forest, XGBoost, and Naive Bayes had the best performance with a classification accuracy of 94%. The high performing algorithms, with the computed hyper-parameters, are then used to process four additional states, Arizona, New Jersey, New York, and Texas entirely used as test data set. The acceptable accuracy results for the large test case, further verifies legibility of the chosen features as influential criteria for modeling purposes. The obtained hyper-parameters for these models (except for Naive Bayes) can now be used to predict future conditions of the spread of the virus. It is shown that, in most of the counties, there exist a connection between adherence to the mask mandate and change in death ratio. The findings of this work emphasizes importance of immediate legislative action on well-being of societies. It is hoped that the findings of this work, highlight importance of socioeconomic and political settings on behavior of different communities, which as portrayed could be complex and counter-intuitive. For instance, if the mask mandate had been issued earlier, with better implementation procedures along with effective incentives targetted at specific communities, more people would be encouraged to abide by the issued ordinance, and consequently, fewer individuals and families would have become the victim of the pandemic.

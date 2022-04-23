# DSAIMiniProject: Predicting Substance Abuse 

Group Members: Anushri Iyer, Sreeja Tar, Joel Tan

## Dataset


**Source:** [Substance Abuse & Mental Health Data Archive](https://www.datafiles.samhsa.gov/dataset/national-survey-drug-use-and-health-2020-nsduh-2020-ds0001)

The source provides statistical information on the abuse and dependence of illicit drugs and substances in the US along with relevant categories such as demographics, income and mental health.


## Motivation 
Substance abuse—involving drugs, alcohol have long led to concerning social conditions such as familial and financial problems, loss of productivity, domestic violence, child abuse, and crime. Social attitudes and legal responses to the consumption of alcohol and illicit drugs make substance abuse one of the most complex public health issues [(Healthy People)](https://www.healthypeople.gov/2020/leading-health-indicators/2020-lhi-topics/Substance-Abuse).
Another rising concern in the US is Mental Health. It is #3 in the World Mental Health Ranking[(Source)](https://www.usnews.com/news/best-countries/articles/2016-09-14/the-10-most-depressed-countries). 

In fact, according to statistics  [(Source)](https://www.cdc.gov/mentalhealth/learn/index.htm):

- 1 in 5 Americans will experience a mental illness in a given year 
- 1 in 5 children, either currently or at some point during their life, have had a seriously debilitating mental illness. 

With this in mind, our group started considering the relationship between mental health and substance abuse while questioning what are some variables that could potentially affect an issue as grave as substance abuse. We believe that identifying certain variables that could help predict the subsceptibility to drug/substance abuse is useful for different stakeholders such as the government, non-profit organisations and the local community. 

Studies have shown rhat the annual cost of substance abuse to the Nation was $510.8 billion in 1999 (Harwood, 2000). 

More specifically:

- Alcohol abuse cost the Nation $191.6 billion
- Tobacco use cost the Nation $167.8 billion 
- Drug abuse cost the Nation $151.4 billion

Therefore, the results of this study can inspire government programmes, awareness campaigns and reliefs for the identified group that is most likely to abuse different types of substances. Given the high costs of substance abuse to the nation, we believe that our information can help inform effective decision-making for a responsible American drug-use society of the future.

**Main Question**: _How do different variables affect one’s susceptibility to substance abuse?_


## Exploratory Data Analysis:
The code in this notebook is used to explore the correlation between psychchological distress, age, race, working circumstances and financial backgrounds and susceptibility to substance abuse. We derived the following information:

***PSYCHOLOGICAL DISTRESS:***

The variable **K6SCYR** was used as an indicator for psychological distress. This variable is assigned scores with values ranging from 0 to 24 indicating the level of psychological distress during the worst month of the past year, that was not the past 30 days. This score variable is based on a series of six questions asking respondents how frequently they experienced the following symptoms of psychological distress:
1. feeling nervous
2. feeling hopeless
3. feeling fidgety
4. feeling so sad or depressed that nothing could cheer you up
5. feeling that everything was an effort
6. feeling down on yourself, no good or worthless

The coding format for each of these symptoms is as follows:
0. none of the time and other responses
1. a little of the time
2. some of the time
3. most of the time
4. all of the time

These values were summed up to get the total K6 score. People with **higher K6 scores** i.e., **worse mental health conditions** were found to be **more prone to substance abuse** as compared to people with lower levels of psychological distress.

***AGE:***

The variable **CATAG7** was used to determine the correlation between age and substance abuse tendencies. The age categories are as follows:
1. 12-13 years old
2. 14-15 years old
3. 16-17 years old
4. 18-20 years old
5. 21-25 years old
6. 26-34 years old
7. 35 years old and older

We derived the following information :
1. **12-15 year olds** are much **less prone to substance abuse**.
2. Respondents **aged 16 and older** are **more likely to be susceptible to substance abuse**.

Specific types of substance abuse showed the following trends:
*   Hallucinogen abuse is the highest among 16-25 year olds.
*   Heroin abuse is the highest among 26+ year olds.
*   Marijuana abuse is the highest among 16-34 year olds.
*   Sedatives abuse is the highest among 21+ year olds.
*   Stimulant abuse is the highest among 16-34 year olds.
*   Pain reliever abuse is the highest among 16+ year olds.
*   Cocaine abuse is the highest among 18-34 year olds.
*   Alcohol abuse is the highest among 21+ year olds.

***RACE:***

The variable **NEWRACE2** was used to determine the correlation between age and substance abuse tendencies. The race categories are as follows:
1. Non-Hispanic White
2. Non-Hispanic Black/African American
3. Non-Hispanic Native American/ AK Native
4. Non-Hispanic Native HI/ Other Pacific Islanders
5. Non-Hispanic Asian
6. Non-Hispanic more than one race
7. Hispanic

We derived the following information:
1. **Hispanic** people are the **least prone to substance abuse**.
2. All other races are almost equally likely to use hallucinogens, marijuana, stimulants and cocaine.
3. Abuse of other substances is **most prevalent among non-Hispanic white and black people**.

***WORKING CIRCUMSTANCES:***

The variable **WRKSTATWK2** had nine categories indicating employment status of the respondents. With no clear correlation between working circumstances and substance abuse, this variable was **disregarded as a valid predictor** and has not been used in any further predictions.

***FINANCIAL BACKGROUND:***

The variable **POVERTY3** was used for correlating financial status and substance abuse tendencies. This variable was created for each individual based on their poverty threshold (determined by their age, family size, the number of children in the household, and total family income). The poverty levels are categorised as follows:
1. Living in poverty
2. Income upto 2 x Federal Poverty Threshold
3. Income more than 2 x Federal Poverty Threshold

Abuse of **four out of the eight substances** considered seems to be prevalent among **people living in poverty**. Abuse of **seven of the eight substances** considered seems to be prevalent among people with incomes above the poverty threshold. We can conclude that substance abuse is **fairly distributed among all income categories**. While initiatives to prevent substance abuse in general may not find this variable particularly useful, programmes targeted at substance abuse awareness and treatment of specific narcotics may choose to target specific income groups based on their deviation towards certain narcotics.


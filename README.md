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

Studies have shown that the annual cost of substance abuse to the Nation was $510.8 billion in 1999 (Harwood, 2000). 

More specifically:

- Alcohol abuse cost the Nation $191.6 billion
- Tobacco use cost the Nation $167.8 billion 
- Drug abuse cost the Nation $151.4 billion

Therefore, the results of this study can inspire government programmes, awareness campaigns and reliefs for the identified group that is most likely to abuse different types of substances. Given the high costs of substance abuse to the nation, we believe that our information can help inform effective decision-making for a responsible American drug-use society of the future.

**Main Question**: _How do different variables affect one’s susceptibility to substance abuse?_


## Exploratory Data Analysis:
The code in this notebook is used to explore the correlation between psychological distress, age, race, working circumstances and financial backgrounds and susceptibility to substance abuse. We derived the following information:

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

## Machine Learning
We tried out the following three models:
1. Simple Decision Tree
2. Logistic Regression
3. Naive Bayes Classifier

**SIMPLE DECISION TREE:**

1. *Binary Classification Decision Tree*:

This model predicted susceptibility to substance abuse (**binary target variable ILLYR**) with a classification **accuracy of 65.57%** on the test data. The variables utilised *in decreasing order of importance* are: **K6SCYR (psychological distress)**, **CATAG7 (age)**, **INCOME (income)** and **POVERTY3 (poverty level)**. Race was not deemed as a valid demographic indicator by this model.

2. *Multi-Class Classification Decision Tree*:

This model predicted susceptibility to specific types of substance abuse (**target variable TYPE with nine categories**) with a classification **accuracy of 64.46%** on the test data. The variables utilised *in decreasing order of importance* are: **K6SCYR (psychological distress)**, **CATAG7 (age)**, **POVERTY3 (poverty level)** and **INCOME (income)**. Race was not deemed as a valid demographic indicator by this model.

**LOGISTIC REGRESSION:**

Our Logistic Regression model worked with an **accuracy of 62%** on our test dataset. While this accuracy is not too impressive, it is not too useless either.  

*   From our exploratory data analysis (EDA), we had found substance abuse tendencies to be comparable among respondents with incomes across all categories. Consistently, this regression model **rejected income and poverty levels** as valid factors to indicate tendencies towards substance abuse.
*   The model **rejected the youngest age category (12-13 years old)** in its computations as this age category has a few to no substance abusers. This is consistent with our post-EDA derivations.
*   The model **rejected most of the race categories** in its computations, leading to the conclusion that ***race is not one of the top indicators*** to determine susceptibility to substance abuse. This is mostly consistent with what we concluded from our EDA, as abuse of 4 of the 8 individual substances considered, was equally prevalent among all races. 
*   The model also **rejected the K6 scores lower than 15**, clearly indicating that higher K6 scores, i.e., ***worse mental conditions and higher psychological distress indicate higher susceptibility to substance abuse***.

**Limitation**: Since logistic regression can only be used to predict a binary target variable (such as ILLYR), we were not able to use this model for individual substance abuse analysis.

**NAIVE BAYES CLASSIFIER:**

Utilising the four factors chosen earlier namely **age** (CATAG7), **race** (NEWRACE2), **income and poverty levels** (INCOME and POVERTY3, respectively) and **psychological distress** (K6SCYR), we obtained a Naive Bayes Classifier model which predicts susceptibility to substance abuse (**binary variable ILLYR**) with an **accuracy of approximately 63.6%**.

As opposed to Logistic Regression, the Categorical Naive Bayes Classifier can be used to predict a non-binary categorical variable, i.e., a categorical variable with more than 2 levels. Therefore, we implemented this model on the **target variable TYPE which has nine categories** indicating the 8 different types of illicit drugs we have studied in this project and one category for non-drug abusers. This model utilised the following predicting factors *in decreasing order of importance*: **psychological distress** (K6SCYR), **income** (INCOME), **age** (CATAG7), **poverty levels** (POVERTY3) and **race** (NEWRACE2). The model predicted susceptibility to **specific types of substance abuse** upto an accuracy of **64.6%**.

## Conclusion/Solution

**CONCLUSION**:
1. All machine learning models consider **Psychological distress**, **Income** and **Age** to be the *top 3 factors* in determining the susceptibility to substance abuse.
2. All machine learning models **reject race as a valid factor** while predicting the likehihood of substance abuse.
3. **Alcohol**, **marijuana** and **hallucinogens** were found to be the *top 3 most abused substances*.
4. Based on the classification accuracy of the  machine learning models, the simple decision tree was the most accurate for binary classification i.e predicting the likelihood of substance abuse (Yes/No) and Naive Bayes Classifier was the most accurate in also determining the chance of a specific subtance being misused.

**SOLUTIONS:**
- Based on our study, initiatives to combat substance abuse can target specific groups such as **mental health patients** and **young adults**.
- Possible investment areas include **substance abuse awareness and education programmes in secondary schools and universities**.
- Such programmes can be more urgently implemented in **states with a larger young adult population**, i.e., a population with a lower median age, for example, Utah, Texas, North Dakota, Nebraska, Idaho, California and Oklahoma.
- Such programmes can also focus states with a population where the **prevalence of metal illness and mental health issues is higher** and **access to mental healthcare services is lower**, for example, Colorado, Utah, Wyoming, Alabama.

**FURTHER CONSIDERATIONS**: 

Our study focused on looking at the relationship between some overarcing variables and substance abuse through different models. Further studies in this field can implement the models we found the most effective to examine other variables and factors that can help narrow down the target segments, thereby increasing effectiveness of solutions to prevent substance abuse. Examples of these variables include access to education, susceptibility to substance abuse based on different types of mental illnesses, etc.

## References
Li, S. (2019, February 27). Building a logistic regression in Python, step by step. Medium. Retrieved April 22, 2022, from https://towardsdatascience.com/building-a-logistic-regression-in-python-step-by-step-becd4d56c9c8#:~:text=Logistic%20Regression%20is%20a%20Machine,%2C%20failure%2C%20etc 

Shin, T. (2020, June 6). A mathematical explanation of naive bayes in 5 minutes. Medium. Retrieved April 22, 2022, from https://towardsdatascience.com/a-mathematical-explanation-of-naive-bayes-in-5-minutes-44adebcdb5f8 

Dobilas, S. (2022, February 12). Naive Bayes classifier - how to successfully use it in python? Medium. Retrieved April 22, 2022, from https://towardsdatascience.com/naive-bayes-classifier-how-to-successfully-use-it-in-python-ecf76a995069 

## Individual Contributions:
Joel Tan: Data cleaning and final presentation (slides and video)

Iyer Anushri: Exploratory data analysis (EDA)

Tar Sreeja: Machine learning models

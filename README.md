
### Link to Data Story :  
https://gianniii.github.io/adaProjectADAMsLEG/

# Mental health during lockdowns through the eyes of Wikipedia

### Abstract:

Covid pandemic had great impact on our lives. Due to the lockdowns, many people were forced to cut many of their social bounds. We expect this to have an impact on their mental health. As the basis of our analysis we use a time series dataset containing pageviews of selected Wikipedia articles in different languages related to mental health. Our first goal is to investigate if there was a change in pageviews of the selected Wikipedia articles during the covid lockdown period compared to the periods before and after, which we will answer by means of statistical analysis, namely ANOVA and Scheffé Test. Secondly we will try to explain readership of mental-health-related articles with mobility data using regression. We use mobility reports from Apple and Google. Lastly, we compare the effects on mental health in different countries using the Wikipedia articles readership and COVIDiSTRESS dataset using again ANOVA and Scheffé Test.

### Research Questions:

* Have lockdowns affected mental health awareness in different countries? If so, in what way and on what mental health issues?
* Does mobility affect mental health interests on Wikipedia?
* What are the differences in effects of lockdowns on mobility in different countries and how do these effects translate to the mental health status of their citizens?

### Proposed additional datasets:

* [Wikipedia:Pageview statistics](https://pageviews.wmcloud.org/?project=en.wikipedia.org&platform=all-access&agent=user&redirects=0&range=latest-20&pages=Cat|Dog) - is a tool available for Wikipedia pages, which allows us to see how many people have visited an article during a given time period. Using this tool, we have collected pageviews statistics of Wikipedia pages that are associated with mental disorders.
* [COVIDiSTRESS](https://www.nature.com/articles/s41597-020-00784-9#Sec7) - is a dataset issued from a global survey on psychological and behavioral consequences of the COVID19 outbreak. This survey recruited  a total of 173426 participants from 179 countries on six continents, between March 30th and May 30th 2020 (with a supplementary data collection on June 17th). It caught our attention because of the measurements it had, most importantly the perceived stress (PSS) and  perceived loneliness (SLON). They quantify those two mental health problems with a total of 13 questions (10 for stress and 3 for loneliness) in their survey. Each question was measured with an ordinal variable 5 point likert Scale ( 1 = never, 5 = very often). The dataset was separated in 3 subsets, for each time the answers were collected: April 17th, Mai 30th and June 17th. We took an already “cleaned” dataset, which had 125’360 people who met their inclusion criteria.
* [Apple mobility report (newer version)](https://github.com/ActiveConclusion/COVID19_mobility/blob/master/apple_reports/applemobilitytrends.csv): This dataset is a newer version of the provided Apple mobility report, the provided dataset captures the first lockdown, but we would like to analyze periods after the initial lockdown as well.
* [Google Trends](https://trends.google.com/trends/?geo=US) -  We can use google trends API to get the weekly  ‘interest’ in certain keywords over the previous 5 year period. This data is clean and allows us to see the variations in interest on google to certain words. We can use this data to backup the wikipedia pageview statistics.

### Methods

We treat this analysis as an observational study. We decided to consider 5 mental disorders: anxiety, depression, loneliness, insomnia, and physiological stress. We will investigate the research questions for 4 countries: Italy, the Netherlands, Sweden, and Poland. We chose these countries for several reasons. Their national language is not spoken in other countries, which allows us to assign a Wikipedia article to the given country based on its language. Secondly, these countries experienced different forms of lockdowns, which we expect to have a different impact on both mental health awareness and mobility. Italy had a very strict lockdown, while Sweden had none at all. The Netherlands and Poland lie somewhere in the middle. We will use the data from 3 periods: before, during and after lockdown.
 
##### Question 1:

For this question we will use two datasets: Wikipedia:Pageview statistics. For each period and disease, we will use the number of Wikipedia page views about this disease in the given language. Thus, for each day we will have 5 numbers that describe the distribution of the number of page views. We will investigate both the changes in the raw viewership in comparison to changes in Stem.Medicine & Health from aggregated topics dataset and distribution of viewership between the diseases. To analyze this question, we will use several approaches:

A similar approach as in the [relevant paper](https://arxiv.org/pdf/2005.08505.pdf). The article examined how the COVID-19 lockdown, along with the severe mobility restrictions, affected access to information on Wikipedia and people's information-seeking patterns. The research questions are similar to ours, so we will use ideas "Difference-in-differences regression" (Sec. 3.2) and "Distances From Normality" (Sec. 3.3) from the article in our research.

##### Question 2:
 
For this question we will use regression to explain the wikipedia pageviews. As features we will use different types of mobility from Google and Apple datasets.

##### Question 3:
 
To investigate this question, we will proceed as in question 1, however using the COVIDiSTRESS’ perceived stress average (PSS10_avg) and perceived loneliness average (SLON3_avg). We will also look at the two pageviews of the respective mental health issues during COVIDiSTRESS’ survey period (i.e from March 30 to June 17), as well as the mobility data from Google and Apples during the same period. We will use an ANOVA test followed by a Post-Hoc comparison such as a Scheffé Test in order to look for a statistical difference.

### Proposed timeline:
* 10.12.22: Draft analysis
* 17.12.22: Final analysis
* 20.12.22: Conclusion + story + website
* 23.12.22: Finalization

### Organization within the team:
* Lubor:
  + Aggregated time-series, topics linked, interventions
  + Analysis of Q2
* Gianni:
  + Google trends, Google and Apple mobility reports
  + Analysis of Q2
  + website
* Mekhron:
  + Wikipedia Pageviews dataset on mental health issues
  + Analysis of Q1
* Eliser:
  + COVIDistress dataset
  + Analysis of Q3
* All Members: 
  + First handling + check viability
  + Help with analysis of other questions when needed
  + Conclusion
  + Story
  + Finalization


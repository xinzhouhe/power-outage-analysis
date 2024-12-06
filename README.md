---
title: "Power Outage Analysis"
layout: spec
---

# Power Outage Analysis
## Introduction
We are given a comprehensive dataset about the power outages that occured in the United States from the year of 2000 and up until the year of 2016, the table below is the detailed description for some columns that we were investigating or haven investigated on, throughout this analysis study, each column represents a feature of the dataset.

### Power Outage Data Legends and Attributes

{% include table.md %}

**Note:** “NA” in the data file indicates data not available.

While there are many columns in the dataset, we aim to primarily focus on the columns that would align with our research interest regarding the question of how do socio-economic factors and historical reliability metrics influence the resilience of power systems in different regions, and can we predict areas with high risk of prolonged outages?

We initially planned to investigate the correlation between the scio-econmic factors and the duration of the power outage, it was estimated that the region with weaker economies, or with a lower economical contribution by the utility sector may have experienced the longer power outage duration. However, after various investigations against the columns related to the socio-economical factors such as the real GSP, the GSP contributed by the utility sector, we did not obtain any applausible findings that could suggest the pattern of our initial assumption. Furthermore, we could not summarize if there is some pattern behind these features.

Therefore, we have made some analysis regarding some other features in the dataset and made the visualization to identify if there exists any interest correlation between the features that we are analyzing. After making several different analysis, we found it could be interesting to study the correlation between the frequency of the power outage incidents and the duration of a particular outage happened at a particular month of a year.

## Data Cleaning and Exploratory Data Analysis
### Data Fetching and Cleaning
Before we could start our data analysis, we need to read the data from the given excel sheet, parse it into a Pandas data frame, and then clean as necessary. For the sake of data completeness, we would not drop any data beforehand, and in case of the N/A values, we will use the specific situation to determine if the dropping is needed, or we can simply call fillna(0), or otherwise use any other applicable method to make up the N/A value.

### Data Visualization
#### Real GSP Contributed by the Utility Industry vs. the Duration of the Power Outage
At the begining, we started the data analysis by investigating the correlation between the duration of outages and the real GSP contributed by the utility industry in the state/region, using the box graph as the visualization.
<iframe
  src="assets/outage_utilgsp.html"
  width="800"
  height="600"
  frameborder="0"
></iframe>
It was thought that the larger real GSP contributed by the utility industry in the state/region, the shorter an outage will last. However, according to the graph, it does not show such a pattern, it seems like the real GSP contributed by the utility industry does not give a reliable indicator on how long the power outage would last.

#### State utility sector’s income as a percentage of total U.S. utility sector income (%) vs. the Duration of the Power Outage
Then we moved onto the analysis of the correlation between the state utility sector’s income as a percentage of total U.S. utility sector income (%) and the duration of the power outage, the rationale would be if the percentage value is larger, it indicates the larger the state utilities compared to the rest of the country. Therefore, for a state with a larger utility industry, it might be able to handle the power outage more efficient than those with the smaller ones.
<iframe
  src="assets/outage_util_state_average.html"
  width="800"
  height="600"
  frameborder="0"
></iframe>
Regarding the visualization, our assumption did not hold as there is little correlation between these two features. Therefore, we had moved onto the other features still related to the scio-economical factors.

#### Residential Electricity Price vs. the Duration of the Power Outage
As one of our last a few attempt on finding the relationship between the scio-economical related feature and the duration of a power outage, we have investigated the correlation between the residential electricity price and the duration of the power outage. Our assumption before the investigation would be if a region sets a higher electricity price, they may experience a shorter power outage, if there is one. This rationale is if users are paying a higher price then the utility industry should enjoy more funding available to them for the emergency response.
<iframe
  src="assets/res_price_vs_outage.html"
  width="800"
  height="600"
  frameborder="0"
></iframe>

However, after observing the visualization, there was no sufficient evidence to back our assumption. Although it is shown that the highest pricing category does show the shortest outage, it could be the reason that there were too little utilities charging that unusually high price, and effectively making this category an outlier, which does not affect the overall pattern.

## Framing a Prediction Problem
After the series of analysis, we believe that the finding of the potential correlation between the frequency of the power outage of a particular month in a year and the duration of the power outage at the same time, through observing using the 2D and 3D heatmap, it worth the further studying and the construction of the prediction model. Therefore, we propose the prediction problem as predicting the duration of the power outage based on how frequent the outage outage have occured in the particular month.

That has being said, at the testing stage, our prediction model would have the following features known, which are the month 

## Baseline Model
## Final Model

## Acknowledgments
This project report authored by <a href='https://xinzhouhe.github.io/'>Daniel X. He</a> and <a href='https://www.linkedin.com/in/mboze/'>Michael D. Boze</a> as part of <a href='https://practicaldsc.org/'>EECS 398-003 Practical Data Science</a> portfolio homework by <a href='https://rampure.org/'>Professor Suraj Rampure</a> at the University of Michigan College of Engineering.

Dataset provided by <a href='https://engineering.purdue.edu/LASCI/research-data/outages'>Laboratory for Advancing Sustainable Critical Infrastructure</a> at Purdue University.
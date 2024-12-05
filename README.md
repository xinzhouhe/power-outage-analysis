---
title: "Power Outage Analysis"
layout: spec
---

# Power Outage Analysis
## Introduction
We are given a comprehensive dataset about the power outages that occured in the United States from the year of 2000 and up until the year of 2016, the table below is the detailed description for each column that represents the attributes of the dataset.

### Power Outage Data Legends and Attributes

{% include table.md %}

**Note:** “NA” in the data file indicates data not available.

While there are many columns in the dataset, we aim to primarily focus on the columns that would align with our research interest regarding the question of how do socio-economic factors and historical reliability metrics influence the resilience of power systems in different regions, and can we predict areas with high risk of prolonged outages?

We initially planned to investigate the correlation between the scio-econmic factors and the duration of the power outage, it was estimated that the region with weaker economies, or with a lower economical contribution by the utility sector may have experienced the longer power outage duration. However, we have investigated the columns related to the socio-economical factors such as the real GSP, the GSP contributed by the utility sector.

## Data Cleaning and Exploratory Data Analysis
We will start the data analysis by investigating the trend of the number of outages has occured over years,
<iframe
  src="assets/outage_util_state_average.html"
  width="800"
  height="600"
  frameborder="0"
></iframe>

## Framing a Prediction Problem
## Baseline Model
## Final Model

## Acknowledgments
This project report authored by <a href='https://xinzhouhe.github.io/'>Daniel X. He</a> and <a href='https://www.linkedin.com/in/mboze/'>Michael D. Boze</a> as part of <a href='https://practicaldsc.org/'>EECS 398-003 Practical Data Science</a> portfolio homework by <a href='https://rampure.org/'>Professor Suraj Rampure</a> at the University of Michigan College of Engineering.

Dataset provided by <a href='https://engineering.purdue.edu/LASCI/research-data/outages'>Laboratory for Advancing Sustainable Critical Infrastructure</a> at Purdue University.
---
title: "Power Outage Analysis"
---

## Introduction
We are given a comprehensive dataset about the power outages that occured in the United States from the year of 2000 and up until the year of 2016, the table below is the detailed description for each column that represents the attributes of the dataset.

### Power Outage Data Legends and Attributes
| Variable Types                     | Variable Names           | Description                                                                                                             |
|------------------------------------|--------------------------|-------------------------------------------------------------------------------------------------------------------------|
| **GENERAL INFORMATION**            |                          |                                                                                                                         |
| Time of the outage event           | YEAR                     | Indicates the year when the outage event occurred                                                                       |
|                                    | MONTH                    | Indicates the month when the outage event occurred                                                                      |
| Geographic areas                   | U.S._STATE               | Represents all the states in the continental U.S.                                                                       |
|                                    | POSTAL.CODE              | Represents the postal code of the U.S. states                                                                           |
|                                    | NERC.REGION              | The North American Electric Reliability Corporation (NERC) regions involved in the outage event                         |
| **REGIONAL CLIMATE INFORMATION**   |                          |                                                                                                                         |
| U.S. Climate regions               | CLIMATE.REGION           | U.S. Climate regions as specified by National Centers for Environmental Information (nine climatically consistent regions in continental U.S.) |
| El Niño/La Niña                    | ANOMALY.LEVEL            | The oceanic El Niño/La Niña (ONI) index referring to cold and warm episodes by season                                   |
|                                    | CLIMATE.CATEGORY        | Climate episodes corresponding to the years: "Warm," "Cold," or "Normal" based on Oceanic Niño Index (ONI)              |
| **OUTAGE EVENTS INFORMATION**      |                          |                                                                                                                         |
| Event start and end information    | OUTAGE.START.DATE        | The day of the year when the outage event started (as reported by the Utility)                                          |
|                                    | OUTAGE.START.TIME        | The time of day when the outage event started (as reported by the Utility)                                              |
|                                    | OUTAGE.RESTORATION.DATE  | The day of the year when power was restored (as reported by the Utility)                                                |
|                                    | OUTAGE.RESTORATION.TIME  | The time of day when power was restored (as reported by the Utility)                                                    |
| Cause of the event                 | CAUSE.CATEGORY           | Categories of events causing major power outages                                                                        |
|                                    | CAUSE.CATEGORY.DETAIL    | Detailed description of event categories causing major power outages                                                    |
|                                    | HURRICANE.NAMES          | If outage due to hurricane, the hurricane name is given                                                                 |
| Extent of outages                  | OUTAGE.DURATION          | Duration of outage events (in minutes)                                                                                  |
|                                    | DEMAND.LOSS.MW           | Amount of peak demand lost during an outage event (in Megawatt)                                                         |
|                                    | CUSTOMERS.AFFECTED       | Number of customers affected by the power outage event                                                                  |
| **REGIONAL ELECTRICITY CONSUMPTION INFORMATION** |              |                                                                                                                         |
| Electricity price                  | RES.PRICE                | Monthly electricity price in the residential sector (cents/kilowatt-hour)                                               |
|                                    | COM.PRICE                | Monthly electricity price in the commercial sector (cents/kilowatt-hour)                                                |
|                                    | IND.PRICE                | Monthly electricity price in the industrial sector (cents/kilowatt-hour)                                                |
|                                    | TOTAL.PRICE              | Average monthly electricity price in the U.S. state (cents/kilowatt-hour)                                               |
| Electricity consumption            | RES.SALES                | Electricity consumption in the residential sector (megawatt-hour)                                                       |
|                                    | COM.SALES                | Electricity consumption in the commercial sector (megawatt-hour)                                                        |
|                                    | IND.SALES                | Electricity consumption in the industrial sector (megawatt-hour)                                                        |
|                                    | TOTAL.SALES              | Total electricity consumption in the U.S. state (megawatt-hour)                                                         |
|                                    | RES.PERCEN               | Percentage of residential electricity consumption compared to total state consumption (%)                               |
|                                    | COM.PERCEN               | Percentage of commercial electricity consumption compared to total state consumption (%)                                |
|                                    | IND.PERCEN               | Percentage of industrial electricity consumption compared to total state consumption (%)                                |
| Customers served                   | RES.CUSTOMERS            | Annual number of customers in the residential electricity sector of the U.S. state                                      |
|                                    | COM.CUSTOMERS            | Annual number of customers in the commercial electricity sector of the U.S. state                                       |
|                                    | IND.CUSTOMERS            | Annual number of customers in the industrial electricity sector of the U.S. state                                       |
|                                    | TOTAL.CUSTOMERS          | Annual number of total customers served in the U.S. state                                                               |
|                                    | RES.CUST.PCT             | Percent of residential customers served in the U.S. state (%)                                                           |
|                                    | COM.CUST.PCT             | Percent of commercial customers served in the U.S. state (%)                                                            |
|                                    | IND.CUST.PCT             | Percent of industrial customers served in the U.S. state (%)                                                            |
| **REGIONAL ECONOMIC CHARACTERISTICS** |                         |                                                                                                                         |
| Economic outputs                   | PC.REALGSP.STATE         | Per capita real gross state product (GSP) in the U.S. state (2009 chained U.S. dollars)                                 |
|                                    | PC.REALGSP.USA           | Per capita real GSP in the U.S. (2009 chained U.S. dollars)                                                             |
|                                    | PC.REALGSP.REL           | Relative per capita real GSP compared to total per capita real GDP of the U.S. (fraction of per capita State and US GDP)|
|                                    | PC.REALGSP.CHANGE        | Percentage change of per capita real GSP from the previous year (%)                                                     |
|                                    | UTIL.REALGSP             | Real GSP contributed by the Utility industry (2009 chained U.S. dollars)                                               |
|                                    | TOTAL.REALGSP            | Real GSP contributed by all industries (2009 chained U.S. dollars)                                                     |
|                                    | UTIL.CONTRI              | Utility industry's contribution to total GSP in the State (percent of total real GDP)                                  |
|                                    | PI.UTIL.OFUSA            | State utility sector's income as a percentage of total U.S. utility sector income (%)                                   |
| **REGIONAL LAND-USE CHARACTERISTICS** |                         |                                                                                                                         |
| Population                         | POPULATION               | Population in the U.S. state in a year                                                                                 |
|                                    | POPPCT_URBAN             | Percentage of the state’s population represented by urban population (%)                                                |
|                                    | POPPCT_UC                | Percentage of the state’s population represented by urban clusters (%)                                                  |
|                                    | POPDEN_URBAN             | Population density of urban areas (persons per square mile)                                                             |
|                                    | POPDEN_UC                | Population density of urban clusters (persons per square mile)                                                          |
|                                    | POPDEN_RURAL             | Population density of rural areas (persons per square mile)                                                             |
| Land area                          | AREAPCT_URBAN            | Percentage of land area in the state represented by urban areas (%)                                                    |
|                                    | AREAPCT_UC               | Percentage of land area in the state represented by urban clusters (%)                                                 |
|                                    | PCT_LAND                 | Percentage of land area in the state compared to total land area in continental U.S. (%)                                |
|                                    | PCT_WATER_TOT            | Percentage of water area in the state compared to total water area in continental U.S. (%)                              |
|                                    | PCT_WATER_INLAND         | Percentage of inland water area in the state compared to total inland water area in continental U.S. (%)               |

**Note:** “NA” in the data file indicates data not available.

While there are many columns in the dataset, we aim to primarily focus on the columns that would align with our research interest regarding the question of how do socio-economic factors and historical reliability metrics influence the resilience of power systems in different regions, and can we predict areas with high risk of prolonged outages?

## Data Cleaning and Exploratory Data Analysis
<iframe
  src="assets/outage_duration_vs_year.html"
  width="800"
  height="600"
  frameborder="0"
></iframe>

## Framing a Prediction Problem
## Baseline Model
## Final Model
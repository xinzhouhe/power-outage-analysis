| Variable Types                     | Variable Names           | Description                                                                                                             |
|------------------------------------|--------------------------|-------------------------------------------------------------------------------------------------------------------------|
| **GENERAL INFORMATION**            |                          |                                                                                                                         |
| Time of the outage event           | YEAR                     | Indicates the year when the outage event occurred                                                                       |
|                                    | MONTH                    | Indicates the month when the outage event occurred                                                                      |
| Geographic areas                   | U.S._STATE               | Represents all the states in the continental U.S.                                                                       |
|                                    | POSTAL.CODE              | Represents the postal code of the U.S. states                                                                           |
|                                    | NERC.REGION              | The North American Electric Reliability Corporation (NERC) regions involved in the outage event                         |
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
| **REGIONAL ECONOMIC CHARACTERISTICS** |                         |                                                                                                                         |
| Economic outputs                   | PC.REALGSP.STATE         | Per capita real gross state product (GSP) in the U.S. state (2009 chained U.S. dollars)                                 |
|                                    | PC.REALGSP.USA           | Per capita real GSP in the U.S. (2009 chained U.S. dollars)                                                             |
|                                    | PC.REALGSP.REL           | Relative per capita real GSP compared to total per capita real GDP of the U.S. (fraction of per capita State and US GDP)|
|                                    | PC.REALGSP.CHANGE        | Percentage change of per capita real GSP from the previous year (%)                                                     |
|                                    | UTIL.REALGSP             | Real GSP contributed by the Utility industry (2009 chained U.S. dollars)                                               |
|                                    | TOTAL.REALGSP            | Real GSP contributed by all industries (2009 chained U.S. dollars)                                                     |
|                                    | UTIL.CONTRI              | Utility industry's contribution to total GSP in the State (percent of total real GDP)                                  |
|                                    | PI.UTIL.OFUSA            | State utility sector's income as a percentage of total U.S. utility sector income (%)                                   |

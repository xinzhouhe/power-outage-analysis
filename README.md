---
title: "Analyzing and Predicting Lengthy Power Outages: Insights from Data and Model Development"
layout: spec
---

# Analyzing and Predicting Lengthy Power Outages: Insights from Data and Model Development
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

However, after observing the visualization, there was no sufficient evidence to back our assumption. Although it is shown that the highest pricing category does have the shortest outage, it could be the reason that there were too little utilities charging that unusually high price, and effectively making this category an outlier, which does not affect the overall pattern.

#### The Cause of Power Outages and Its Effects
At this point, we have changed our initial proposal on targeting the scio-economical factors on the effects of the duration of the power outage. We have made two analysis on how the cause of power outages affect its duration and the loss the power demand.
<iframe
  src="assets/outage_duration_vs_cause.html"
  width="800"
  height="600"
  frameborder="0"
></iframe>
<iframe
  src="assets/outage_loss_vs_cause.html"
  width="800"
  height="600"
  frameborder="0"
></iframe>
According to these two graphs, we believe that there is a correlation between the cause of the power outage and its duration, as well as the power demand loss cause by the power outage.

#### Bivariate Analysis
The analysis and visualizations above were focused on the univariate analysis, we have also explored the dataset a little bit more, to gain a deeper understanding of the pattern. The first would the trend of the frequency of the power outages occured over years.
<iframe
  src="assets/annual_trend.html"
  width="800"
  height="600"
  frameborder="0"
></iframe>
It is shown like that there were way less frequent power outage happened pre-2010, but slowly increasing, and the frequency has surged on 2010. After 2010, we have noticed that overall pattern starts to decrease. Therefore, we have made a more detailed analysis into the year of 2016, and noticed that the latest outage occured in 2016 is in July. As such, we believe that the data for 2016 is incomplete and therefore could be the evidence to back the claim that the frequency of power outages after 2010 has been steadily decreasing, but instead may be decreased slightly and back increasing again.

We have analyzed the trend over months within a year, but we have not found a specific pattern or correlation of which specific month of a year would likely to have more power outages. Therefore, we have combined all months and years into a new data frame, and created a heatmap as the visualization of the frequency of the power outages happened in each month of each year. This heatmap would combine two variables, which are month and year of the occured power outage.
<iframe
  src="assets/outage_counts_by_mon_and_year.html"
  width="800"
  height="600"
  frameborder="0"
></iframe>
It appears that the frequency of the power outages is concentrated on the the later year, and 2010 with the highest frequency of the power outage. To see if there could be any correlation between the frequency of the power outage and its average duration over the specific period of time, we have created a similar heatmap for the average duration of the power outage for the months in a year.
<iframe
  src="assets/average_duration_heatmap.html"
  width="800"
  height="600"
  frameborder="0"
></iframe>
By the comparison of two heatmaps that we have created, it leads to the belief that the month of a year experienced a higher frequency, tend to have a lower average duration. Therefore, it is likely if there are more power outages happened in a month, the shorter of each one might be lasting.

## Framing a Prediction Problem
### Conclusion From the Exploratory Data Analysis
Through our observation from the exploratory data analysis, we initially investigated correlations between socio-economic factors and power outage durations. However, no strong or reliable patterns were identified between variables like the real GSP contributed by the utility industry, state utility sector income as a percentage of the total U.S. utility income, and residential electricity price against outage duration. Our assumptions regarding these socio-economic variables influencing outage durations could not be substantiated.

### Development of Our Prediction Problem
The focus then shifted to analyzing the causes of power outages and their impact. Clear correlations were observed:

1. The cause of the power outage had a significant influence on its duration.
2. The cause also affected the loss in power demand during outages.

Additionally, trends in outage frequency across years and months indicated that:

- Frequency surged in 2010 but showed overall fluctuations in later years.
- Months with higher outage frequency tended to have shorter average durations.

These insights led to the refinement of our prediction problem to focus on classifying outages as either long or short based on available features like `CUSTOMERS.AFFECTED` and `CAUSE.CATEGORY`.

The prediction problem is framed as a binary classification task to determine whether a power outage will last 60 minutes or longer. Long outages are defined as outages lasting one hour or more, with the target variable `LONG_OUTAGE` set to 1 for long outages and 0 for short outages. The following aspects were considered:

- **Features (X):**
  - `CUSTOMERS.AFFECTED`
  - `CAUSE.CATEGORY`
- **Target (y):**
  - `LONG_OUTAGE`

The goal was to preprocess the features and train a model to accurately classify power outages based on the available data.

## Baseline Model
### Model Development
The baseline model was developed using Python's `scikit-learn` library to predict outage-related classifications based on key features. Below is a summary of the steps involved in the development:

1. **Data Preparation**:
   - The dataset includes features such as `CUSTOMERS.AFFECTED`, `CAUSE.CATEGORY`, and `OUTAGE.DURATION`.
   - Missing values were handled by filling with zeros for numerical features like `LONG.OUTAGE`.

2. **Feature Selection**:
   - The selected features for training included:
     - Numerical: `CUSTOMERS.AFFECTED`, `OUTAGE.DURATION`.
     - Categorical: `CAUSE.CATEGORY`.

3. **Data Splitting**:
   - The dataset was split into training and testing subsets with an 80-20 ratio to ensure unbiased evaluation.
   - A random seed (`random_state=42`) was used to allow reproducibility.

4. **Preprocessing**:
   - A `ColumnTransformer` was used to preprocess the features:
     - **Numerical features** were standardized using `StandardScaler`.
     - **Categorical features** were encoded using `OneHotEncoder`.

5. **Pipeline**:
   - A `Pipeline` was built to streamline preprocessing and model fitting:
     - Preprocessing steps were incorporated into the pipeline.
     - Logistic regression (`LogisticRegression`) was used as the classification model for simplicity and interpretability.

6. **Training**:
   - The pipeline was fit on the training data using the selected features.

### Performance Evaluation
The model was evaluated on the test dataset using the following metrics:

- **Precision**: Indicates how many of the predicted positive results were correctly classified.
- **Recall**: Measures the ability of the model to identify all positive instances.
- **F1-Score**: Harmonic mean of precision and recall, providing a balance between the two.
- **Accuracy**: Proportion of correctly classified instances over the total number of predictions.

The classification report generated for the test data is as follows:

| Class | Precision | Recall | F1-Score | Support |
|-------|-----------|--------|----------|---------|
| 0     | 0.47      | 0.57   | 0.52     | 70      |
| 1     | 0.87      | 0.78   | 0.82     | 237     |
| **Overall** | **0.77** | **0.76** | **0.77** | **307** |

- **Macro Average**: Precision (0.69), Recall (0.68), F1-Score (0.69).
- **Weighted Average**: Precision (0.77), Recall (0.76), F1-Score (0.77).

### Insights
1. The model achieved an overall accuracy of 77%, which is a reasonable performance for a baseline model.
2. Class 1 (majority class) had significantly higher precision, recall, and F1-score, indicating the model performs better for this class.
3. Class 0 (minority class) performance was weaker, highlighting class imbalance as a challenge for improvement.

### Next Steps
1. **Cross-validation**:
   - Use cross-validation to ensure the model generalized well across different subsets of the data.
2. **Feature Engineering**:
   - Explore additional features or transformations to enhance predictive power.
3. **Hyperparameter Tuning**:
   - Optimize the logistic regression model using techniques like grid search or random search.

## Final Model
### Features and Their Importance
For the final model, we added **`MONTH`** as an additional feature, for the following reasons:
  - Temporal patterns, such as seasonal effects, could play a role in outage duration, especially in regions prone to severe weather.
  - In the heatmap that we have created from the exploratory data analysis, we have found there are some months of some years tend to have more frequent power outages, and it could correlate to the duration of the power outage in that month.

### Modeling Algorithm
We replaced Logistic Regression with a **Decision Tree Classifier** to explore non-linear relationships between features and the target variable. Decision trees can capture complex patterns in the data, making them a suitable choice for this task. To optimize the model, we used the following techniques:

1. **Hyperparameter Tuning**:
   - The following hyperparameters were tuned using GridSearchCV:
     - `max_depth`: Controls the maximum depth of the tree. Values tested: [5, 10, 20].
     - `min_samples_split`: Specifies the minimum number of samples required to split an internal node. Values tested: [2, 5, 10].
   - The best parameters were:
     - `max_depth`: 5
     - `min_samples_split`: 2

2. **Cross-Validation**:
   - Used 5-fold cross-validation to ensure the model generalized well across different subsets of the data.

3. **Pipeline Integration**:
   - A pipeline was constructed to combine preprocessing steps and the Decision Tree Classifier, ensuring streamlined model training and evaluation.

### Performance Comparison
**Final Model Metrics (Decision Tree Classifier)**:

| Metric       | Class 0 | Class 1 | Accuracy | Macro Avg | Weighted Avg |
|--------------|---------|---------|----------|-----------|--------------|
| Precision    | 0.66    | 0.89    |          | 0.77      | 0.83         |
| Recall       | 0.64    | 0.90    |          | 0.77      | 0.83         |
| F1-Score     | 0.65    | 0.89    | 0.83     | 0.77      | 0.83         |

### Key Insights
1. **Improved Balance Across Classes**:
   - The final model achieved balanced precision, recall, and F1-score for both classes, indicating good generalization.

2. **Class 0 (Short Outages)**:
   - Precision improved to **0.66**, and recall reached **0.64**, resulting in a well-rounded F1-score of **0.65**.

3. **Class 1 (Long Outages)**:
   - Maintained strong precision and recall at **0.89**, highlighting the model's ability to correctly identify long outages.

4. **Overall Metrics**:
   - Accuracy improved to **83%**, with macro and weighted averages also reflecting balanced performance.

#### **Conclusion**
The Decision Tree Classifier provided a significant improvement in handling the minority class (Class 0) while maintaining strong performance for the majority class (Class 1). The model's ability to capture non-linear relationships contributed to its better overall performance compared to the baseline Logistic Regression model.

## Acknowledgments
This project report authored by <a href='https://xinzhouhe.github.io/'>Daniel X. He</a> and <a href='https://www.linkedin.com/in/mboze/'>Michael D. Boze</a> as part of <a href='https://practicaldsc.org/'>EECS 398-003 Practical Data Science</a> portfolio homework by <a href='https://rampure.org/'>Professor Suraj Rampure</a> at the University of Michigan College of Engineering.

Dataset provided by <a href='https://engineering.purdue.edu/LASCI/research-data/outages'>Laboratory for Advancing Sustainable Critical Infrastructure</a> at Purdue University.
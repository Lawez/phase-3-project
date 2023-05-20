# Phase 3 Project 

# Chicago City Crash analysis

# Project Overview
The City of Chicago Vehicle Safety Board (CCVSB) interested in reducing traffic accidents and becoming aware of any interesting patterns.

# Business Problem

The business problem is to build a classifier that can predict the primary contributory cause of car accidents in Chicago city.

# Defing the Questions
   1. *Are there any specific locations or road segments in Chicago city that have a higher frequency of car accidents?*

   2. *What are the contributing factors or characteristics associated with severe car accidents in Chicago city?*

   3. *Are there any seasonal or temporal patterns in car accidents in Chicago city?*

Additionally, I will create a classification model to categorize accidents into two main groups for future reference:

1. Accidents caused by unintentional factors: *These accidents occur when drivers are not purposely or knowingly involved in causing the accident. They may result from factors such as driver error, environmental conditions, mechanical failures, or other unforeseen circumstances.*

2. Accidents caused by intentional factors: *These accidents involve drivers who are deliberately or knowingly involved in causing the accident. They may engage in reckless driving, aggressive behavior, or intentionally violate traffic laws, leading to the occurrence of the accident.*

By developing this classification model, we aim to distinguish between accidents that result from unintentional factors and those that involve intentional actions. This categorization will enable us to analyze and understand the different contributing factors and characteristics associated with each category, leading to targeted strategies for accident prevention and improving overall road safety.

# Data

The dataset was from Chicago city. Their were three datasets that was obtain from Chicago Data Portal:


    * Traffic_Crashes_-_People 
    * Traffic_Crashes_-_Vehicles
    * Traffic_Crashes_-_Crashes
The data provides up-to-date information as per now May 2023 from 2015.The two datasets was cleaned and merged to one.

# Data Grocery

| Index | Column Name             | Description                                                  |
|-------|-------------------------|--------------------------------------------------------------|
| 1     | SEX                     | Gender of the person involved in the accident                |
| 2     | AGE                     | Age of the person involved in the accident                   |
| 3     | DRIVER_ACTION           | Action taken by the driver before the accident               |
| 4     | DRIVER_VISION           | Vision condition of the driver during the accident           |
| 5     | PHYSICAL_CONDITION      | Physical condition of the driver at the time of the accident |
| 6     | MANEUVER                | Maneuver performed by the driver during the accident         |
| 7     | POSTED_SPEED_LIMIT      | Speed limit posted on the road where the accident occurred   |
| 8     | TRAFFIC_CONTROL_DEVICE  | Traffic control device present at the accident location      |
| 9     | DEVICE_CONDITION        | Condition of the traffic control device                       |
| 10    | WEATHER_CONDITION       | Weather conditions during the accident                        |
| 11    | LIGHTING_CONDITION      | Lighting conditions during the accident                       |
| 12    | TRAFFICWAY_TYPE         | Type of the trafficway where the accident occurred           |
| 13    | ROADWAY_SURFACE_COND    | Surface condition of the roadway at the accident location    |
| 14    | ROAD_DEFECT             | Defects present on the road where the accident occurred       |
| 15    | PRIM_CONTRIBUTORY_CAUSE | Primary contributory cause of the accident                    |
| 16    | CRASH_HOUR              | Hour of the day when the accident occurred                   |
| 17    | CRASH_DAY_OF_WEEK       | Day of the week when the accident occurred                   |
| 18    | CRASH_MONTH             | Month when the accident occurred                             |
| 19    | LATITUDE                | Latitude coordinate of the accident location                  |
| 20    | LONGITUDE               | Longitude coordinate of the accident location                 |
| 21    | LOCATION                | Location description of the accident                          |



# Recording the Experimental Design

To record the experimental design for building the classifier to predict the primary contributory cause of car accidents in Chicago, I used the following steps:

* Data Collection:  I gather crashes, vehicle and people accident data from https://data.cityofchicago.org/Transportation/Traffic-Crashes-Vehicles/68nd-jvt3  and https://data.cityofchicago.org/Transportation/Traffic-Crashes-People/u6pd-qa9d 

* Data Preprocessing: Clean the data by handling missing values, inconsistencies, and outliers.
                      Transform categorical variables into numerical representations suitable for machine learning algorithms.
                      Normalize or standardize numerical features if necessary

* Exploratory Data Analysis (EDA): Perform exploratory analysis to understand the characteristics and distributions of variables.
                                   Identify patterns, correlations, or any interesting insights within the data.
                                   Visualize the data using plots, charts, or graphs to aid in understanding.

* Feature Engineering:Extract relevant features from the available data that may contribute to predicting the primary contributory cause of car accidents.
* Target Variable Binning: Analyze the distribution of the primary contributory cause categories.
Merge or eliminate categories with very few samples to limit the number of target categories.                                  

* Feature Selection: Select the most informative features that are likely to have a significant impact on the prediction.

* Model Selection and Training:Choose a suitable machine learning algorithm for multi-class classification, considering factors like performance, interpretability, and scalability.Split the preprocessed data into training and testing sets.
Train the chosen model on the training data using appropriate algorithms and methodologies.
* Model Evaluation:Evaluate the trained model's performance using relevant evaluation metrics for multi-class classification, such as accuracy, precision, recall, F1-score, or confusion matrix.Perform cross-validation techniques like k-fold cross-validation to assess the model's robustness.
* Model Optimization:Fine-tune the model by optimizing hyperparameters to improve its performance.
Use techniques like grid search, random search.
* Predictions and Interpretation:Use the optimized model to predict the primary contributory cause of car accidents for new instances.
Analyze the predictions and interpret the results to gain insights into patterns, potential causes, or any interesting findings that can aid accident prevention efforts.
* Reporting and Recommendations:Summarize the findings and insights obtained from the classifier.
Provide actionable recommendations for the Vehicle Safety Board or the City of Chicago based on the analysis and predictions.


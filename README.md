# Phase 3 Project 

# Chicago City Crash analysis

<p align="center">
  <img width="800" height="400" src="https://github.com/Lawez/phase-3-project/tree/main/images/chicago_city.jpg">
</p> 


# Project Overview
The City of Chicago Vehicle Safety Board (CCVSB) interested in reducing traffic accidents and becoming aware of any interesting patterns.

# Business Problem

The business problem is to build a classifier that can predict the primary contributory cause of car accidents in Chicago city.

# Defineing the Questions
   1. *Are there any specific locations or road segments in Chicago city that have a higher frequency of car accidents?*

   2. *What are the contributing factors or characteristics associated with severe car accidents in Chicago city?*

   3. *Are there any seasonal or temporal patterns in car accidents in Chicago city?*

   4. *Can we build a classification model to predict the primary contributory cause of car accidents?*


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

# EDA analysis and Visualization
#### Question one 
    *Are there any specific locations or road segments in Chicago city that have a higher frequency of car accidents?*

![one.png](https://github.com/Lawez/phase-3-project/tree/main/images/one.png)

    The map highlights a significant concentration of accidents in the downtown area of Chicago, indicating a higher density of incidents in that region. The predominant color in this area is green, indicating that a majority of the accidents are attributed to intentional actions or driver errors. However, it's important to note that there are also scattered blue plots throughout the map, suggesting a considerable number of accidents that occur unintentionally or present opportunities for improvement in terms of safety measures.

#### Question Two
    *What are the contributing factors or characteristics associated with severe car accidents in Chicago city?*

![quiz_two.png](https://github.com/Lawez/phase-3-project/tree/main/images/quiz_two.png)

Upon analyzing the contributing factors associated with control failures in unintentional accidents, it is evident that a majority of the accidents occurred when the driver's vision was not obscured. Furthermore, it is notable that these accidents occurred while the drivers were adhering to the posted speed limit, typically set at 30 mph. These findings suggest that factors other than vision or speed might be contributing to control failures in these accidents.

An important finding from the analysis is that the absence of traffic control devices has been the primary contributing factor to the number of accidents in Chicago. This suggests that increasing the presence of traffic control devices throughout the city could potentially reduce the occurrence of unintentional accidents. This finding is further supported by the Device Condition plot, which indicates a higher count of accidents when there are no traffic control devices in place. Implementing and improving traffic control measures can therefore be an effective strategy to mitigate control failures and enhance road safety in Chicago.

The analysis indicates that weather condition and lighting condition have relatively minimal impact on the occurrence of accidents. These factors do not show a strong correlation with the number of accidents in Chicago.

Significant number of accidents occur on roads categorized as "Not Divided" in terms of trafficway type. This suggests that implementing road division measures, such as adding medians or physical barriers, can potentially mitigate the occurrence of accidents. Dividing the roads can enhance traffic management, separate opposing flows of traffic, and reduce the likelihood of collisions, thereby contributing to improved road safety.

The analysis indicates that the roadway surface condition and road defects have a relatively minimal impact on the occurrence of these accidents. It suggests that the condition of the road surface, such as potholes or uneven pavement, and the presence of road defects, such as cracks or debris, may not be significant contributors to the unintentional accidents in Chicago.

#### Question Three
    *Are there any seasonal or temporal patterns in car accidents in Chicago city?*

![three.png](https://github.com/Lawez/phase-3-project/tree/main/images/three.png)

The analysis of the crash time data reveals that a significant number of accidents in Chicago occur between the hours of 14 to 18, which coincides with the peak rush hour traffic. This suggests that the high volume of vehicles during these hours contributes to the increased accident rate. Considering the concentration of accidents in the downtown area during this time frame, it becomes apparent that better traffic management strategies are needed.

To address this issue, it is recommended that the city implements additional measures to facilitate traffic flow and reduce congestion in the downtown area during these peak hours. This can include deploying more traffic management personnel or implementing intelligent transportation systems to optimize traffic signal timings and improve the coordination of traffic movements. By enhancing traffic management during rush hours, the city can mitigate the number of accidents and improve overall road safety in the downtown area.

The analysis of the crash data by day of the week indicates that there is a slightly higher number of accidents during the weekends compared to other days. However, the difference in accident frequency between weekdays and weekends is not substantial. Therefore, it can be concluded that the crash hour plays a more significant role in determining accident occurrence than the specific day of the week.

Analyzing the crash data by month reveals some interesting patterns. The number of car accidents in Chicago tends to be higher during the summer months, particularly in June, July, August and September. This can be attributed to various factors such as increased travel and tourism, more outdoor activities, and potentially more congested roads during the summer season.

However, it is important to note that while there may be higher accident rates during certain months, the difference in accident frequency between months is not significant enough to warrant major adjustments in road safety strategies based solely on the crash month.


#### Question Four
     *Can we build a classification model to predict the primary contributory cause of car accidents?*

![matrix.jpg](https://github.com/Lawez/phase-3-project/tree/main/images/matrix.jpg)

## Methods

After exploring and preprocessing the data I applied the following models:
    * Logistic Regression

    * Decesion Tree

    * Random Forest
    
    * XG 
    
## Results

|     MODEL            |  ACCURACY  |  PRECISION SCORE 0  |  F1-SCORE 0 TESTING  |  F1-SCORE 1 TESTING  |  AUC  |
| -------------------- | ---------- | ------------------ | -------------------- | -------------------- | ----- |
| Logistic Regression  |   0.68     |        0.74        |         0.59         |         0.75         | 0.75  |
| Decision Tree        |   0.64     |        0.67        |         0.6          |         0.62         | 0.62  |
| Random Forest        |   0.66     |        0.63        |         0.62         |         0.64         | 0.64  |
| XG Boost             |   0.7      |        0.68        |         0.68         |         0.69         | 0.69  |


Based on the provided results, the XG Boost model achieved the highest accuracy of 0.70, outperforming the other models (Logistic Regression, Decision Tree, and Random Forest) in terms of accuracy. The XG Boost model also had relatively higher precision scores, F1-scores for both classes (0 and 1), and AUC compared to the other models.

Therefore, based on the evaluation metrics, the XG Boost model is considered the best model for the given task.

## Conclusion

* Downtown Chicago has a high concentration of accidents, primarily caused by intentional actions or driver errors. However, there are scattered incidents of unintentional accidents, indicating the need for safety improvements.

* Control failures in unintentional accidents are not significantly influenced by vision or speed. Other factors may contribute to these accidents and require further investigation.

* The absence of traffic control devices is a significant contributing factor to accidents in Chicago. Increasing their presence can help reduce unintentional accidents.

* Weather and lighting conditions have minimal impact on accident occurrence in Chicago.

* Accidents are common on non-divided roads, suggesting the need for road division measures to improve traffic management and safety.

* Road surface condition and defects have a minimal impact on unintentional accidents.

* Rush hour traffic, particularly between 14-18 hours, contributes to a higher number of accidents in the downtown area. Better traffic management strategies are needed during these peak hours.

* Weekend days show a slightly higher number of accidents compared to weekdays, but crash hour plays a more significant role in determining accident occurrence.

* Summer months have a higher number of accidents, potentially due to increased travel and outdoor activities. However, adjustments in road safety strategies based solely on the crash month may not be necessary.

Overall, these findings suggest the importance of implementing targeted safety measures, increasing traffic control devices, improving traffic management during peak hours, and considering various factors contributing to accidents to enhance road safety in Chicago.


## Recomendations

* Increase Traffic Control Measures: Install additional traffic control devices, such as traffic lights, stop signs, and speed limit signs, particularly in areas with a high concentration of accidents. Ensure that existing devices are well-maintained and functioning properly.

* Enhance Road Infrastructure: Implement road division measures, such as adding medians or physical barriers, to separate opposing flows of traffic and reduce the likelihood of collisions. Improve road surfaces to minimize hazards like potholes or uneven pavement.

* Improve Traffic Management: Implement intelligent transportation systems and optimize traffic signal timings to facilitate traffic flow and reduce congestion, especially during peak rush hour periods. Consider deploying additional traffic management personnel to ensure efficient traffic management.

* Driver Education and Awareness: Conduct targeted educational campaigns to raise awareness about safe driving practices, including the importance of attentiveness, obeying traffic laws, and maintaining a safe speed. Emphasize the risks associated with intentional actions, such as reckless driving or aggressive behavior.

* Collaborate with Law Enforcement: Strengthen collaboration between the City of Chicago Vehicle Safety Board, law enforcement agencies, and other relevant stakeholders to enforce traffic laws effectively and deter dangerous driving behaviors.

* 
Continuous Monitoring and Evaluation: Establish a robust system to collect and analyze data on car accidents continuously. Regularly evaluate the effectiveness of implemented measures and adjust strategies based on evolving trends and patterns in accidents.

## Limitations
* Future Changes: The analysis is based on data up to a certain cutoff date. Road conditions, traffic patterns, and other factors may change over time, potentially affecting the relevance and applicability of the conclusions and recommendations in the future.

* Implementation Challenges: Implementing the recommended interventions may face practical challenges, such as budget constraints, regulatory hurdles, public acceptance, and coordination among multiple stakeholders. These challenges should be considered during the planning and implementation phases.

* External Factors: The analysis primarily focuses on internal factors such as driver actions, road conditions, and traffic control devices. External factors such as socioeconomic factors, urban planning, and public policies may also contribute to the occurrence of accidents but are not extensively explored in this analysis.

## Next steps
* Detailed Analysis of Contributory Factors: Conduct a deeper analysis of the contributing factors associated with intentional and unintentional accidents. Explore specific driver actions, physical conditions, maneuver types, and other variables to identify patterns and prioritize targeted interventions.

* Advanced Modeling Techniques: Consider implementing advanced modeling techniques, such as ensemble methods, deep learning, or anomaly detection algorithms, to improve the accuracy and robustness of the classification model for predicting primary contributory causes of accidents.

* Geographic Hotspot Analysis: Perform a spatial analysis to identify specific locations or road segments with a higher frequency of accidents. Use techniques such as hotspot analysis or spatial clustering to pinpoint areas requiring focused attention for safety improvements.

* Long-Term Data Analysis: Expand the analysis period beyond the available data to identify long-term trends and changes in accident patterns. This can help in identifying the effectiveness of implemented measures over time and detecting emerging issues or new risk factors.

* Collaboration with Insurance Companies: Collaborate with insurance companies to access additional data, such as accident severity, insurance claims, and vehicle information. This data can provide further insights into the factors associated with severe accidents and help develop targeted strategies for prevention.

**Repository Structure:**

```
├── data                                                   <- Data folder location of our study
├── images                                                 <- images folder of our notebook 
├── presentation.pdf                                       <- PDF version of project presentation 
├── .canvas                                                <- canvas extention 
├── .gitignore                                             <- gitignore 
├── CONTRIBUTING                                           <- Conribution logs
├── LISENCE.md                                               <- LICENCE of the project
├── README.md                                              <- The top-level README for reviewers of this project                  
└── student.ipynb                                          <- Narrative documentation of analysis in Jupyter notebook
```


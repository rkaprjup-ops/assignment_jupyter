# assignment_jupyter

Summary of Assignment

https://github.com/rkaprjup-ops/assignment_jupyter/blob/main/Summary_Assignment.pdf

Presentation Audio

https://drive.google.com/file/d/1juPjfaFbwrO_EWIfvgHSLI9TklDovBzs/view

Presentation Transcribe

https://view.officeapps.live.com/op/view.aspx?src=https%3A%2F%2Fraw.githubusercontent.com%2Frkaprjup-ops%2Fassignment_jupyter%2Frefs%2Fheads%2Fmain%2FPTT-20260820-WA0007_transcribe.docx&wdOrigin=BROWSELINK

AI Summary:

# Summary of Nectar IT Pre-Screening Assignment Tasks and Methods

## Task 2: Predictive Maintenance Model [00:00:37 – 00:01:17]

The main objective was to create a predictive maintenance model to forecast equipment failure before it happened. The presenter used a dataset containing a failure indicator column. The approach involved training an XGBoost classifier on this data after splitting it into training and test sets. Due to significant class imbalance in the training set, the Synthetic Minority Over-sampling Technique (SMOTE) was applied to balance the dataset. Model evaluation included classification metrics such as precision, recall, and F1 score, alongside visualization tools like confusion matrices, ROC curves, and precision-recall curves. A key insight was that **VOC (Volatile Organic Compounds) showed the highest correlation with failure prediction**, indicating its importance as a predictive feature.

## Task 3: Energy Forecasting and Data Preprocessing [00:01:17 – 00:03:32]

This task involved forecasting energy consumption using a dataset with both numerical (temperature, humidity, square footage, occupancy, renewable energy, hour, day, month) and categorical features (HVAC usage, lighting usage, day of week, holiday). Key steps were:

- **Outlier Detection and Removal:** 
  - Used IQR range filtering for categorical features.
  - Used z-score filtering for numerical features to handle outliers detected in energy consumption.

- **Feature Engineering:** 
  - Converted categorical variables using label encoding for binary types (e.g., HVAC on/off as 1/0).
  - Applied one-hot encoding for nominal categorical variables (e.g., days of the week).
  - Created two additional features: 
    - **Time period level** distinguishing morning, afternoon, evening, and night for weekdays.
    - **Weekend level** binary indicator for weekend days (Saturday/Sunday = 1, else 0).

- **Model Comparison:** 
  Evaluated four models: XGBoost, Random Forest, Linear Regression, and Ridge Regression. Linear Regression gave the best results based on RMSE values.

- **Key Finding:** Temperature emerged as the most important feature affecting energy consumption predictions.

## Task 1: Exploratory Data Analysis (EDA) on Sensor Data [00:03:33 – 00:04:40]

The dataset encompassed sensor data from three devices across different environments, monitoring light, motion, temperature, humidity, CO, LPG, and smoke. 

- **Data Reduction:** LPG and smoke sensors were removed as they were highly correlated with CO, reducing redundancy.
- **Environmental Insights:** Two devices had stable, tightly controlled environments, while one showed higher variability.
- **Signal Processing:** Light and motion sensors provided binary outputs; a rolling average was applied to smooth these signals alongside temperature data.
- **Anomaly Detection:** Used the Isolation Forest algorithm to detect anomalies in temperature and motion readings, aiming to identify irregular sensor behaviors or environmental changes.

---

**Summary Table of Key Points:**

| Task | Objective                         | Main Dataset Features                       | Techniques Applied                                   | Key Outcome/Insight                         |
|-------|---------------------------------|--------------------------------------------|----------------------------------------------------|---------------------------------------------|
| 2     | Predictive Maintenance           | Dataset with failure label                  | XGBoost, SMOTE, classification metrics & curves   | VOC highly correlated with failure         |
| 3     | Energy Consumption Forecasting   | Numerical: weather, occupancy; Categorical: HVAC, day, holiday | Outlier removal, label & one-hot encoding, feature engineering, multiple regression models | Linear regression best; temperature key predictor |
| 1     | EDA on Sensor Data               | Sensors: light, motion, temp, humidity, CO, LPG, smoke    | Correlation analysis, rolling average smoothing, anomaly detection with Isolation Forest | Removed redundant sensors; identified anomalies |

---

This summary reflects the candidate’s approach in tackling complex data challenges through thoughtful preprocessing, feature engineering, and model evaluation across multiple tasks. It highlights how feature selection and handling imbalanced or noisy data played pivotal roles in modeling and analysis outcomes.

# Project Title: Predicting Mortality Among ICU Admitted Heart Failure Patients

## Team Members: Project Group 1
- Emily Bowers
- Matt Flanagan
- Luis Martinez

## Project Overview & Purpose
To use machine learning for predicting in-hospital mortality among ICU-admitted Heart Failure (HF) patients using data downloaded from Kaggle (originally sourced from MIMIC-III database). Patients with a diagnosis of HF, who were ≥ 19 years old at the time of ICU admission were included in the study. Our Project set out to determine wich, if any variable(s) more strongly predict inpatient mortality among HF admitted patients. 

## Data References
Data are sourced from Kaggle.com, In Hospital Mortality Prediction Dataset, Admissions to ICU of the Beth Israel Deaconess Medical Center, Boston, MA June 1, 2001-October 31, 2012
(https://www.kaggle.com/datasets/saurabhshahane/in-hospital-mortality-prediction/data)


## Data Analysis Questions
1.	Descriptive Data Overview:
  - Volume & Frequency of:
  - Age
  - Comorbidities
  - % survival/deaths

2.	Determine predictive characteristics (Independent variables) of inpatient mortality among Heart Failure patients


## Instructions on How to Use and Interact with Data
Explore Tableau dashboard, public use file here: https://public.tableau.com/shared/M6R8FZH2C?:display_count=n&:origin=viz_share_link

You can download the dashboard to review existing data insights and also create your own insights through the dashboard. 

## Data Methods & Tools Used
- Data Exploration and Preparation: 
Cleaning data: Checked for missing values and determined to keep records with missing clinical information as NA. We removed one record as the Outcome was not recorded (0 = expired, 1= not expired).
  - Tools: Python, Pandas

- Model Selection and Training:
    - Exploratory Data Analysis We explored the dataset to understand the relationships between different variable groups (lab values, vital signs, comorbidities) and determined to use these groupings as collective variables for testing.

    -Classification Model: We chose a Decision tree model because the dataset consisted of non-linear data and the project required binary classification (expired or not expired). The dataset was split into training and testing sets utilizing standardScaler to ensure all features tested have the same scale. We did not utilize Stratified Sampling due to when we tested the model with stratified sampling, the accuracy and precision decreased. We tested 4 variable groups - lab values, vital signs, comorbidities, and all clinical data combined to determine which variable groups may be helpful in predicting inpatient mortality. 
        - Tools:Python, Pathlib, sklearn, matplotlib, seaborn

- Visualization:
  - Jupyter notebook, Python, seaborn
  - Tableau Dashboard to display descriptive characteristics of patient population and outcomes of model testing
- README File:
  - VSCode
- Presentation:
  - Google Slides

## Interpretation and Analysis 
1. Interpretability: 
- Lab Value grouping model had an accuracy score of 0.819, predicting the class correctly approximately 81.9% of the instances. The model was good at predicting True Negatives (Actual 0, Predicted 0) = 231, however not good at predicting True Positives (TP) (Actual 1, Predicted 1) = 10, roughly correct 24% of the time. Additionally, the model's recall of Positives (expired patients) was 0.31, indicating the model only identifies 31% of the actual instances of class 1. 

- Comorbidity grouping model had an accuracy score of 0.891, predicting the class correctly approximately 89.1% of the time, higher than the Lab Value model. Similar to the Lab value model, the precision for class 0 (not expired patients) was 89%, a high precision score. This model was not a good predictor of inpatient mortality as the model's precision was 0% in precision for predicting expired patients. Additionally, this model's recall of Class 1 (expired patients) was 0%, and could not identify any of the actual instances of expired patients. 

- Vital Sign grouping model had an accuracy score of 0.795, predicting the class correctly approximately 79.5% of the instances. The model was precision for correctly identifying true negatives was high at 89%. On the other hand, the model was less precise for correctly identifying True Positives at 6%. Additionally, the model's recall for class 0 was 89%, whereas the model's recall for class 0 was 6%. Overall, good at identifying patients that do not expire, but does not help in predicting inpatient mortality.

- All 48 Variables grouping model had an accuracy score of 0.789, predicting the class correctly approximately 78.9% of the time. The model also had a a good precision score for class 0 at 92%, and had the highest precision score for class 1 at 22% out of the 4 models tested thus far. The recall for class 1 was 0.38, identifying 38% of the actual instances of class 1 - again the highest among the 4 models tested. Overall, this model may be the best out of the 4 tested but was not reliable enough to be utilized in any clinical application. 


2. Descriptive Data:
  - Volume & Frequency of:
  - Age: 40% (n=476) of patients are 80-90 years old, followed by 23% (n=272) 70-80 years old. 
  - Body Mass Index (BMI):
    - Majority of patients were considered Obese (>30) or Overweight (25-29.9)
  - Comorbidities
    - 72% were Hypertensive
    - ~45% had Afib
    - ~42% had Diabetes
    - Less common comorbidities were: COPD, Depression, Anemia, and Coronary Heart Disease
  - % survival/deaths
    - Overall, 86% of patients did not expire while inpatient

## References
We utilized prior class activities to help write and/or modify code for specific use in this project. Addtionally, we utilized https://scikit-learn.org/stable/modules/tree.html
We utilized (https://www.geeksforgeeks.org/confusion-matrix-machine-learning/) to help understand Confusion matrices and data output. 


## Presentation
Our visualizations can be found on our Tableau dashboard: https://public.tableau.com/shared/SNBMQKXPM?:display_count=n&:origin=viz_share_link

Presentation slides here: 

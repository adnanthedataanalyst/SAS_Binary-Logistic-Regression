# Logistic Regression predicting Student Dropout

## Introduction
This project aims to develop a logistic regression model for predicting undergraduate student dropouts based on a dataset containing student demographics, academic performance, and socio-economic information. The goal is to create a robust predictive model that can assist educational institutions in allocating resources efficiently, implementing early interventions, and providing support to at-risk students.

## Key Question
What factors contribute significantly to student dropout, and how can these factors be leveraged to develop an accurate predictive model?

## Method
### Data Collection
- **Data Source**: Kaggle dataset.
- **Dataset Description**: This dataset, collected by experts from the VALORIZA Research Center and Polytechnic Institute of Portalegre, compiles information on students in diverse undergraduate degrees. It includes details from enrollment, such as academic path and socio-economic factors, as well as academic performance at the first and second semesters. The dataset is designed for building classification models to predict students' dropout and success at the end of the course duration.
- **Code Description Integration**: Integrating Dataset Column Descriptions and Categories from Damiieibikun's GitHub repository appendix.

### Data Loading and Exploration
The dataset is loaded into SAS and explored for its structure, including variable names and data types. Subsequently, it is split into training and testing sets for model development and evaluation.

## Binary Logistic Regression Analysis Results
### Model Information:
- **Data Set**: WORK.IMPORT
- **Response Variable**: Dropout (levels: "No" and "Yes")
- **Model**: Binary logistic regression
- **Optimization Technique**: Fisher's scoring method
- **Number of Observations**: 4424

### Response Profile:
- 1421 students dropped out ("Yes"), 3003 students did not ("No").

### Model Fit Statistics:
- Lower AIC, SC, and -2 Log L statistics indicate better fit compared to the intercept-only model.

### Parameter Estimates:
- **Intercept**: Statistically significant (p < 0.0001)
- **Application_Mode, Course, Tuition_fees_up_to_d, Scholarship_Holder, Age_At_Enrollment, Curricular_Units_2nd**: All predictor variables are statistically significant (p < 0.0001).

### Odds Ratio Estimates:
- Insights into the effects of predictor variables on the odds of dropout.

### Association of Predicted Probabilities and Observed Responses:
- Concordance statistics indicate predictive ability.

### Influence Plots:
- Visual representation of influential cases in the data.

### Conclusion:
- Factors such as application mode, course, tuition fees, scholarship status, age at enrollment, and curricular units are significantly associated with student dropout, suggesting potential interventions to reduce dropout rates.

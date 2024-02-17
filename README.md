# Logistic Regression predicting Student Dropout

## Introduction
This project aims to develop a logistic regression model for predicting undergraduate student dropouts based on a dataset containing student demographics, academic performance, and socio-economic information. The goal is to create a robust predictive model that can assist educational institutions in allocating resources efficiently, implementing early interventions, and providing support to at-risk students.

**Note**: 
[Excel file]
[SAS Output]

## Key Question
What factors contribute significantly to student dropout, and how can these factors be leveraged to develop an accurate predictive model?

## Method
### Data Collection
- **Data Source**: [Kaggle dataset](https://www.kaggle.com/datasets/thedevastator/higher-education-predictors-of-student-retention).
- **Dataset Description**: This dataset, collected by experts from the [VALORIZA Research Center and Polytechnic Institute of Portalegre](https://zenodo.org/records/5777340#.Y7FJotJBwUE), compiles information on students in diverse undergraduate degrees. It includes details from enrollment, such as academic path and socio-economic factors, as well as academic performance at the first and second semesters. The dataset is designed for building classification models to predict students' dropout and success at the end of the course duration.
- **Code Description Integration:** Integrating Dataset Column Descriptions and Categories from Damiieibikun's GitHub repository appendix, found [here](https://github.com/Damiieibikun/Student-s-Dropout-Prediction-using-Supervised-Machine-Learning-Classifiers). This repository provides the missing information regarding the categorical labels used in the dataset.

### Data Loading and Exploration
The dataset is loaded into SAS and explored for its structure, including variable names and data types. Subsequently, it is split into training and testing sets for model development and evaluation.


```markdown
# Logistic Regression predicting Student Dropout

## Model Information
1. Data Set: WORK.IMPORT
2. Response Variable: Dropout
3. Number of Response Levels: 2
4. Model: Binary Logit
5. Optimization Technique: Fisher's Scoring
6. Number of Observations Read: 4424
7. Number of Observations Used: 4424

### Summary:
- The logistic regression model was built using data from WORK.IMPORT dataset to predict student dropout.
- The response variable "Dropout" has two levels: "No" and "Yes".
- Fisher's scoring method was utilized for model estimation, with all 4424 observations being used for analysis.

## Response Profile
|     | Ordered | Value | Dropout | Total |
|-----|---------|-------|---------|-------|
|     |         | No    | 3003    |       |
| 1.  |         | Yes   | 1421    |       |

### Summary:
- The response profile shows that out of the 4424 students, 3003 did not drop out ("No") while 1421 did ("Yes").

## Model Fit Statistics
|     | Criterion | Intercept Only | Intercept and Covariates |
|-----|-----------|----------------|--------------------------|
| 2.  | AIC       | 5556.532       | 3380.896                 |
| 3.  | SC        | 5562.927       | 3425.660                 |
| 4.  | -2 Log L  | 5554.532       | 3366.896                 |

### Summary:
- The AIC (Akaike Information Criterion) and SC (Schwarz Criterion) values are measures used to compare the goodness-of-fit of statistical models. Lower values of AIC and SC indicate a better fit of the model. Typically, differences in AIC or SC greater than 2 indicate some evidence for one model over the other, and differences greater than 10 indicate strong evidence. In our analysis, the model with covariates (independent variables) has lower AIC (5556.532 vs. 3380.896) and SC (5562.927 vs. 3425.660) values compared to the model with only the intercept term, suggesting that the model with covariates fits the data better.

- The -2 Log L statistic is another measure of the goodness-of-fit of a statistical model, specifically for logistic regression. Similar to AIC and SC, a lower -2 Log L value indicates a better fit of the model to the data. However, there is no universal threshold for what constitutes a low -2 Log L value, as it depends on the specific dataset and research context. In our analysis, the -2 Log L value for the model with covariates (3366.896) is lower than for the intercept-only model (5554.532), indicating that the model with covariates provides a better fit to the data.


- Significance Threshold: p < 0.05

## Analysis of Maximum Likelihood Estimates
|     | Parameter             | DF | Estimate | Standard Error | Wald Chi-Square | Pr > ChiSq |
|-----|-----------------------|----|----------|----------------|-----------------|------------|
| 5.  | Intercept             | 1  | 2.2842   | 0.2254         | 102.7241        | <.0001     |
| 6.  | Application_Mode      | 1  | 0.0443   | 0.00927        | 22.8185         | <.0001     |
| 7.  | Course                | 1  | 0.0919   | 0.0102         | 80.6283         | <.0001     |
| 8.  | Tuition_fees_up_to_d  | 1  | -2.6607  | 0.1527         | 303.7729        | <.0001     |
| 9.  | Scholarship_Holder    | 1  | -1.0240  | 0.1218         | 70.7151         | <.0001     |
| 10. | Age_At_Enrollment     | 1  | 0.0373   | 0.00611        | 37.3544         | <.0001     |
| 11. | Curricular_Units_2nd  | 1  | -0.2640  | 0.00962        | 752.9464        | <.0001     |

### Summary:
- The estimates represent the change in log odds of dropout associated with a one-unit change in the predictor variable, holding other variables constant.
- All predictor variables are statistically significant (p < 0.05) in predicting student dropout.

## Odds Ratio Estimates
|     | Effect                | Point Estimate | 95% Wald Confidence Limits |
|-----|-----------------------|----------------|-----------------------------|
| 12. | Application_Mode      | 1.045          | 1.026 - 1.064               |
| 13. | Course                | 1.096          | 1.075 - 1.119               |
| 14. | Tuition_fees_up_to_d  | 0.070          | 0.052 - 0.094               |
| 15. | Scholarship_Holder    | 0.359          | 0.283 - 0.456               |
| 16. | Age_At_Enrollment     | 1.038          | 1.026 - 1.051               |
| 17. | Curricular_Units_2nd  | 0.768          | 0.754 - 0.783               |

### Summary:
- Odds ratios provide insights into the magnitude and direction of the effects of predictor variables on the odds of dropout.
- A one-unit increase in "Course" is associated with a 9.6% increase in the odds of dropout.

## Association of Predicted Probabilities and Observed Responses
- Percent Concordant: 87.5%
- Somers' D: 0.750
- Percent Discordant: 12.5%
- Gamma: 0.751
- Percent Tied: 0.0%
- Tau-a: 0.327
- Pairs: 4267263

### Summary:
- Concordance statistics indicate the predictive ability of the model.
- A high concordance percentage and values close to 1 suggest a good predictive performance of the model.
```

### Association of Predicted Probabilities and Observed Responses:
- Concordance statistics indicate predictive ability.

### Influence Plots:
- Visual representation of influential cases in the data.
<img width="475" alt="Screenshot 2024-02-17 104044" src="https://github.com/adnanthedataanalyst/SAS_Binary-Logistic-Regression/assets/152249280/cbe664b2-8b9d-4ee2-812b-b35add4d8782">

<img width="474" alt="Screenshot 2024-02-17 104044" src="https://github.com/adnanthedataanalyst/SAS_Binary-Logistic-Regression/assets/152249280/09703ef1-2374-4ca6-a75b-234621b1af1c">

  
<img width="476" alt="Screenshot 2024-02-17 104044" src="https://github.com/adnanthedataanalyst/SAS_Binary-Logistic-Regression/assets/152249280/59797207-d85e-499d-a16d-51ae65d3f70d">

### Conclusion:
The logistic regression analysis revealed significant predictors of student dropout, including application mode, course, tuition fees, scholarship holder status, age at enrollment, and curricular units. These findings highlight the importance of considering various factors when identifying at-risk students. By leveraging this predictive model, educational institutions can allocate resources more efficiently, implement early interventions, and provide targeted support to reduce dropout rates and enhance student success. Further research and refinement of the model could enhance its effectiveness in addressing the complex issue of student attrition.

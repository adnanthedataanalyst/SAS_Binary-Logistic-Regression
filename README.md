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
- The AIC (Akaike Information Criterion) and SC (Schwarz Criterion) values are lower in the model with covariates, indicating better model fit compared to the intercept-only model.
- The -2 Log L statistic is also lower in the model with covariates, further supporting its better fit.

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

### Conclusion:
- Factors such as application mode, course, tuition fees, scholarship status, age at enrollment, and curricular units are significantly associated with student dropout, suggesting potential interventions to reduce dropout rates.

# Logistic Regression Model

## Overview
The logistic regression model was used to assess the impact of demographic factors (Age, Gender, Marital Status, Occupation, and Income) on the likelihood of experiencing mental health issues.

## Model Summary

The logistic regression model results are presented below:

| Factor                          |  Estimate | Std. Error |  z value |  Pr(> mod of z) | Significance |
|---------------------------------|-----------|------------|----------|-----------|--------------|
| Intercept                       |   3.8448  |   4.6537   |   0.826  |   0.4087  |              |
| Age                             |  -0.1840  |   0.1337   |  -1.377  |   0.1686  |              |
| Gender (Male)                   |  -0.9515  |   0.5280   |  -1.802  |   0.0715  | .            |
| Marital Status (Unmarried)      |  -3.5038  |   2.0273   |  -1.728  |   0.0839  | .            |
| Occupation (Retired)            |  -8.5768  |  6522.6405 |  -0.001  |   0.9990  |              |
| Occupation (Student)            |   3.1338  |   1.5947   |   1.965  |   0.0494  | *            |
| Occupation (Unemployed)         | -15.5437  | 1847.5754  |  -0.008  |   0.9933  |              |
| Income (10 and above lakhs)     |   3.3749  |   1.3754   |   2.454  |   0.0141  | *            |
| Income (3-5 lakhs)              |   0.8749  |   0.8737   |   1.001  |   0.3167  |              |
| Income (5-8 lakhs)              |   0.2466  |   0.9442   |   0.261  |   0.7940  |              |
| Income (8-10 lakhs)             |   0.3039  |   1.0965   |   0.277  |   0.7817  |              |
| Income (Below 1 lakh)           |   0.1217  |   0.6562   |   0.186  |   0.8528  |              |


*Significance Codes*:
- **0.001** = Very significant
- *0.01* = Significant
- *0.05* = Mild significance (*)
- *0.1* = Marginal significance (.)
- *1* = No significance

## Interpretation
- *Gender (Male)*: The coefficient for males is -0.9515, with a p-value of 0.0715, indicating marginal significance. Men are less likely to have mental health issues compared to other genders, but the result is not highly significant.
  
- *Marital Status (Unmarried)*: The coefficient is -3.5038, with a p-value of 0.0839, suggesting marginal significance. Being unmarried slightly reduces the likelihood of experiencing mental health issues.
  
- *Occupation (Student)*: The coefficient is 3.1338, with a p-value of 0.0494. This is significant at the 5% level, indicating that students are more likely to experience mental health issues compared to other occupations.
  
- *Income (10 and above lakhs)*: The coefficient is 3.3749, with a p-value of 0.0141. This is significant, suggesting that individuals with an income above 10 lakhs are more likely to experience mental health issues.

The demographic factors gender, marital status, occupation, Income has significant impact on mental health issues

## Confusion Matrix for Logistic Regression Model

The model's predictions are evaluated using a confusion matrix:

|              | Predicted 0 | Predicted 1 | Total |
|--------------|-------------|-------------|-------|
| Actual 0     | 59          | 11          | 70    |
| Actual 1     | 10          | 31          | 41    |
| *Total*    | 69          | 42          | 111   |

The accuracy of the model is calculated as:

Accuracy={59 + 31}/{111} = 0.8108

The model achieves an accuracy of *81.08%*, indicating that it correctly predicts mental health factors 81.08% of the time.

#ROC curve
![This is the ROC curve](https://github.com/user-attachments/assets/6432aeb5-dde6-4cee-93b0-14dffb57dc3d)
The model is still not very effective in classifying the positive and negative classes, indicating room for improvement.

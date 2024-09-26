1. **Logistic Regression**: A model to evaluate the impact of demographic factors on mental health.
```r
ab <- read.csv(file.choose(), header = TRUE)
summary(ab) # Display summary statistics of the dataset
```

### Split the Data

Split the dataset into training and testing sets using an 80-20 ratio.

```r
set.seed(123) # Set seed for reproducibility
split <- sample.split(ab, SplitRatio = 0.8) # Split data
train <- subset(ab, split == TRUE) # Training set
test <- subset(ab, split == FALSE) # Testing set
```

### Convert Variables to Factors

Convert relevant variables to factors for model fitting.

```r
ab$Yes.no <- as.factor(ab$Yes.no)      # Response variable
ab$Gender <- as.factor(ab$Gender)      # Gender
ab$MT <- as.factor(ab$MT)              # Mental Training
ab$EQ <- as.factor(ab$EQ)              # Emotional Quotient
ab$MS <- as.factor(ab$MS)              # Mental State
ab$Occ <- as.factor(ab$Occ)            # Occupation
ab$Income <- as.factor(ab$Income)      # Income level
ab$locality <- as.factor(ab$locality)  # Locality
```

## Model Fitting

### Logistic Regression Model

Fit a logistic regression model to predict mental health status (`Yes.no`) based on various factors.

```r
model <- glm(Yes.no ~ Age + Gender + MT + EQ + MS + Occ + Income + locality, family = "binomial", data = test)
summary(model) # Display summary of the logistic regression model
```

### Stepwise Regression

Perform stepwise regression to optimize the model.

```r
stp <- step(model, direction = "both") # Perform stepwise regression
summary(stp) # Summary of the optimized model
```

### Variance Inflation Factor (VIF)

Calculate the VIF to check for multicollinearity among the predictors.

```r
vif(model) # Calculate and display VIF for model predictors
```

## Model Evaluation

### ROC Curve

Plot the ROC curve to evaluate the model's performance.

```r
plotROC(actuals = train$Yes.no, as.numeric(fitted(stp))) # Plot ROC curve
```

### Confusion Matrix

Generate a confusion matrix to assess the model's classification performance.

```r
confusion_matrix <- confusion_matrix(model, test) # Generate confusion matrix
print(confusion_matrix) # Display confusion matrix
```

## Conclusion

This analysis provides insights into the factors affecting mental health using logistic regression modeling. The model's performance can be further evaluated through metrics such as accuracy, precision, and recall based on the confusion matrix and ROC curve.

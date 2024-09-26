# Statistical Analysis of Mental Health Data

## Overview

This document presents the statistical analysis conducted to predict the factors affecting mental health using R. The analysis includes data preparation, model fitting, and evaluation based on the questionnaire data.
Below are the major analyses conducted:

1. **Logistic Regression**: A model to evaluate the impact of demographic factors on mental health.
2. **Proportion Tests**: Tests for proportions of alcohol consumption, counsellors availability, and major life events.

## Data Preparation

### Load Required Libraries

Before starting the analysis, we need to load the required libraries.

```r
library(ggplot2)          # For data visualization
library(caTools)         # For data splitting
library(car)             # For checking multicollinearity
library(InformationValue) # For ROC curve plotting
library(regclass)        # For confusion matrix
```

### Load Data

Load the dataset from a CSV file. You can choose the file interactively using the `file.choose()` function.

To run the code:
- Use the Logistic regression and proportion test files for statistical analysis.

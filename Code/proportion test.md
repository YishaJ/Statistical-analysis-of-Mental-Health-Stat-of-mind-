2. **Proportion Tests**: Tests for proportions of alcohol consumption, counsellors' availability, and major life events using R.

```r
# Hypothesis Test for Alcohol Consumption
# H0: Proportion of people consuming alcohol is the same as proportion of people not consuming alcohol.
# H1: Proportion of people consuming alcohol is less than proportion of people not consuming alcohol.

# Perform the proportion test
result <- prop.test(31, 200, conf.level = 0.95, alternative = "less")

# Display the result
print(result)

# Hypothesis Test for Counsellors Availability
# H0: Proportion of people having counsellors in their area is the same as proportion of people not having counsellors.
# H1: Proportion of people having counsellors is less than proportion of people not having counsellors.

# Perform the proportion test
result <- prop.test(69, 200, conf.level = 0.95, alternative = "less")

# Display the result
print(result)

# Hypothesis Test for Major Life Events
# H0: Proportion of people who have experienced a major life event is the same as proportion of people who have not.
# H1: Proportion of people who have experienced a major life event is greater than those who have not.

# Perform the proportion test
result <- prop.test(105, 200, conf.level = 0.95, alternative = "greater")

# Display the result
print(result)

# econ3916-lab14-ols-diagnostics

# OLS Diagnostics: When the Standard Error Is Lying

## Objective

In this lab, I learned how to check OLS regression assumptions, identify problems using residual plots, and understand why robust standard errors are important.

## Methodology

- Simulated data with heteroskedasticity and compared classical and HC3 robust standard errors.
- Ran 400 simulations to compare the coverage rates of classical and robust 95% confidence intervals.
- Examined four residual plots and used Breusch-Pagan and Jarque-Bera tests to identify problems.
- Used leverage, standardized residuals, and Cook's distance to identify influential observations.
- Removed one influential observation and compared the regression results before and after.
- Used the California Housing dataset to compare classical and HC3 standard errors.
- Wrote a function called `hc3_se()` to calculate the HC3 standard error for a selected variable.

## Key Findings

- **Heteroskedasticity:** The estimated slope was 2.0147 for both classical and robust methods. However, the classical standard error was 0.0264, while the HC3 standard error was 0.0290. This shows that heteroskedasticity can affect standard errors without changing the coefficient.

- **Confidence Interval Coverage:** Across 400 simulations, the classical 95% confidence interval covered the true slope 91.8% of the time, compared with 93.5% for the robust interval. Their Monte Carlo standard errors were 1.4% and 1.2%, respectively. The robust interval was closer to the expected 95% coverage.

- **Residual Diagnostics:** The four residual plots showed a well-behaved model, heteroskedasticity, missing curvature, and an outlier. I learned that statistical tests may not detect every problem that is visible in a residual plot.

- **Influential Observations:** After removing one observation out of 600, the slope changed by 0.58 of its own standard error, while the standard error decreased by 33%. This shows that one extreme observation can have a large effect on the standard error.

- **California Housing:** The HC3 standard error for AveRooms was 5.02 times the classical standard error, showing that classical standard errors may underestimate uncertainty.

- **HC3 Function:** My `hc3_se()` function passed the notebook's checks. The HC3 standard error for AveRooms was 0.0121 with all districts and 0.0082 after excluding the 965 districts at the housing value ceiling. However, a smaller standard error alone is not a good reason to remove valid observations.

## Conclusion

This lab helped me understand why checking regression assumptions is important. I learned that a regression coefficient can look reasonable even when its standard error is unreliable. Robust standard errors can help with heteroskedasticity, but they cannot fix every problem in a regression model.

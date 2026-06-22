# \---

# title: "Assessing Methods for Generalizing Experimental Impact Estimates"

# author: "Syed Hamza Afzal Ashraf \& Abdul Muqsit Farooqui"

# output: github\_document

# \---

# 

# \# FIFA Players Performance: Generalization Strategies

# 

# \## Overview

# This repository explores how design methodologies and strategic techniques contribute to \*\*Generalization\*\* in statistical and machine learning models. Inspired by the research paper \*"Assessing methods for generalizing experimental impact estimates to target populations"\*, we apply propensity-score-based methods and various generalization approaches to estimate the Average Treatment Effect (ATE) on a target population.

# 

# Instead of traditional demographic data, this project evaluates player performance using FIFA video game datasets. We analyze how changes in player wages influence their overall performance ratings across different game editions.

# 

# \---

# 

# \## Data Requirements

# To run the notebooks and scripts in this repository, ensure the following datasets are placed in your working directory. You must use these exact filenames verbatim:

# \* `fifa.csv`

# \* `players\_18.csv`

# \* `players\_20.csv`

# 

# The data is pre-processed to handle missing values, encode text variables into indices, normalize numeric ranges, and remove extreme outliers to prepare it for propensity modeling.

# 

# \---

# 

# \## Methodology

# 

# \### Treatment Definition

# We aim to generalize the "Overall" rating influenced by the "Wage" of a player. By comparing the datasets (e.g., `fifa.csv` and `players\_18.csv`), we calculate the differences in `Wage` and `Overall` ratings. 

# \* \*\*Treatment = 1\*\*: If there is a difference in Wage and Overall between the rankings.

# \* \*\*Treatment = 0\*\*: If there is no difference.

# 

# \### Feature Selection

# We applied the \*\*Chi-Square\*\* test to identify the top 30 most important covariates influencing the outcome. Key features include \*SlidingTackle, StandingTackle, Marking, Composure, Penalties, Vision, Positioning, Interceptions,\* and \*Aggression\*.

# 

# \### Generalization Strategies Tested

# We compared the relative bias, efficiency, and accuracy of the following statistical and machine learning approaches:

# 1\. \*\*Linear Regression\*\*

# 2\. \*\*Doubly Robust (DR) with Logistic Regression (LR)\*\*

# 3\. \*\*Doubly Robust Random Forest (DR-RF)\*\*

# 4\. \*\*Gaussian Naive Bayes\*\*

# 

# \---

# 

# \## Results \& Evaluation

# 

# We evaluated the models based on \*\*RMSE (Root Mean Square Error)\*\*, \*\*R-squared\*\*, \*\*ATT (Average Treatment Effect on the Treated)\*\*, and \*\*Accuracy\*\*. 

# 

# \### 1. Linear Regression

# \* \*\*RMSE\*\*: 3.34551

# \* \*\*R-squared\*\*: 0.715343

# \* \*\*ATT\*\*: 3.97966

# \* \*\*Accuracy\*\*: 0.134711

# 

# \### 2. Doubly Robust Logistic Regression

# \* \*\*RMSE\*\*: 0.6284

# \* \*\*R-squared\*\*: 0.98996

# \* \*\*ATT\*\*: 3.97966

# \* \*\*Accuracy\*\*: 0.59669

# \* \*\*AUC-ROC\*\*: 0.70072

# \* \*\*F1 Score\*\*: 0.74741

# 

# \### 3. Doubly Robust Random Forest

# \* \*\*RMSE\*\*: 0.57585

# \* \*\*R-squared\*\*: 0.99157

# \* \*\*ATT\*\*: 3.97966

# \* \*\*Accuracy\*\*: 0.59669

# \* \*\*AUC-ROC\*\*: 0.70072

# \* \*\*F1 Score\*\*: 0.74741

# 

# \### 4. Gaussian Naive Bayes

# \* \*\*RMSE\*\*: 6.35988

# \* \*\*R-squared\*\*: -0.05944

# \* \*\*ATT\*\*: 3.97966

# \* \*\*Accuracy\*\*: 0.61734

# 

# \---

# 

# \## Conclusion

# Based on our experimental impact estimates, the \*\*Machine Learning-based algorithm (Doubly Robust Random Forest)\*\* performs significantly better than standard Linear Regression, boasting the lowest RMSE and the highest R-squared value. Conversely, \*\*Gaussian Naive Bayes\*\* performed the worst, yielding a negative R-squared and the highest error rate. 

# 

# These findings highlight the importance of using robust, ML-driven propensity-score methods when generalizing experimental data to larger target populations.


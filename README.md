# customer-response
This repository contains R code used to forecast customer behavior by predicting the likelihood that a customer will purchase a specific product—in this case, a new pasta dish. The project demonstrates how logistic regression can be applied to binary classification problems in a marketing context.

## Overview 
Imagine needing to predict not just overall customer spending, but also specific actions like making a purchase this month. Using regression analysis, and more specifically logistic regression, this project addresses questions such as:
- Will a customer make a purchase?
- What factors increase the odds of a purchase?

By using logistic regression, we transform predictors into a probability (ranging from 0 to 1) of a purchase, allowing us to gauge the influence of various factors such as gender, past purchase behavior, and total spending.

## Project Components
- ### Data & Features:
  The dataset includes the binary target variable buyer (1 for purchase, 0 otherwise) along with predictors like:
  - gender
  - last (an index or recency metric)
  - purch (frequency of past purchases)
  - total$ (total expenditure)
- ### Modeling Approach:
  - Logistic Regression: used to model probability of purchase.
  - Interpretation of coefficients:
   - For example, the coefficient for gender (0.51) implies that, holding other variables constant, the odds of a male customer purchasing are approximately 1.67 times higher than those of a female customer.
   - For the continuous variable purch, each additional purchase increases the odds by about 1.09 times.
- ### Prediction:
   - The predict() function in R outputs probabilities, which ranged from 0.7% to 41% across customers. This variance suggests a strong relationship between the predictors and purchase behavior.
- ### Model Evaluation:
    - An ROC curve was generated to assess model performance, plotting the true positive rate versus the false positive rate at various thresholds. Although visualizing the ROC curve is useful, its insights can be summarized with the AUC metric.
    - AUC Findings: The model achieved an AUC of 0.708. Generally, an AUC above 0.8 is considered strong, between 0.7 and 0.8 acceptable, and over 0.9 outstanding. An AUC of 0.708 indicates that the model produces an acceptable balance between true positive and false positive predictions.


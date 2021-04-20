# San Bay Tel
![bridge_logo.jpg](https://github.com/wswager/san_bay_tel/blob/main/images/bridge_logo.jpg)
***
# Overview

Analyze data associated with telecommunications customers in the San Francisco Bay area and predict churn using classification modeling.
***
![bridge_photo](https://github.com/wswager/san_bay_tel/blob/main/images/bridge_photo.jpg)
***
# Business Problem

San Bay Tel is a new telecommunications startup looking to establish themselves in the San Francisco Bay area. 

San Day Tel's main priority is retention while they establish themselves in the market.  For this reason they have requested a model predicting the likelihood of customer churn.
***
# Data
## Churn in Telecom Data

Data associated telecommunications customers from the San Franciscon Bay area, area codes:

* **415** City of San Francisco, Marin County, and the northeast corner of San Mateo County
* **408** City of San Jose, Santa Clara County, and northern Santa Cruz County
* **510** Contra Costa County and western Alameda County

*Data sourced from* [Churn in Telecom's dataset](https://www.kaggle.com/becksddf/churn-in-telecoms-dataset/code) *by* [david_becks](https://www.kaggle.com/becksddf)
***
# Data Cleaning

Remove phone number, area code, and state 
* Individual phone numbers will be unique to each customer
* Only three area codes are represented, all within the same defined geographic area
* State, indicates the customer's origin state, however, the current assumption is that they reside in the defined geographic area

Define Catergorical Data and Label Encode
***
# Data Exploration
Total Churn: 483 
Percentage of Churn: 14.49 %
![total_churn.png](https://github.com/wswager/san_bay_tel/blob/main/images/histograms/total_churn.png)

## Feature Exploration
Example: Account Length
![account_length.png](https://github.com/wswager/san_bay_tel/blob/main/images/histograms/account_length.png)

Example: International Plan
![internation_plan.png](https://github.com/wswager/san_bay_tel/blob/main/images/histograms/international_plan.png)

## Correlation
![initial_correlation.png](https://github.com/wswager/san_bay_tel/blob/main/images/correlation/initial_conrrelation.png)
***
# Modeling
***
## Evaluation Metrics
The following metrics are being calulated for each of the models tested:
* Accuracy as compared to the inverse of the percentage of churn (85.51%)(the average of random samplings of the data would have an accuracy of 85.51%, therefore, for accuracy to be considered positive it would need to indicate a significant improvement over this baseline)

* Precision, the ratio of false negatives, instances correctly identified as churned

* Recall, the ratio of true positives, instances correctly identified as not churned

* F1 Score, the weighted average of the precision and recall values

For each model, a confusion matrix is being created, visually representing the dispersal of True Positives, True Negatives, False Positives, and False Negatives.

San Bay Tel has requested a model predicting the liklihood of churn.  Therefore, for the purposes of the this project the highest valued metrics will be Precision and Accuracy.
***
## Logistic Regression Evaluation
![logistic_regression.png](https://github.com/wswager/san_bay_tel/blob/main/images/confusion_matrix/logistic_regression.png)

The model's accuracy, 88.02% is not significantly higher than the inverse percentage of customers who churn, 85.50%.

The model's precision, 78.94%, indicates the model is detecting a higher percentage of false instance of churn.

The model's F1 Score, 42.85%, is low.
***
## Ada Boost Evaluation
![adaboost.png](https://github.com/wswager/san_bay_tel/blob/main/images/confusion_matrix/adaboost.png)

The model's accuracy, 88.02% is the same as the Logistic Regression model.

The model's precision, 65.71%, is lower than the Logistic Regression model.

The model's F1 Score, 42.85%, is higher than the Logistic Regression model.
***
## K Neighbors Evaluation
![k_neighbors.png](https://github.com/wswager/san_bay_tel/blob/main/images/confusion_matrix/k_neighbors.png)

The model's accuracy, 88.02% is the same as the Logistic Regression and Ada Boost models.

The model's precision, 86.67%, is higher than the Logistic Regression and Ada Boost models.

The model's F1 Score, 39.39%, is lower than the Logistic Regression and Ada Boost models.
***
## Decision Tree Evaluation
![decision_tree.png](https://github.com/wswager/san_bay_tel/blob/main/images/confusion_matrix/decision_tree.png)

The model's accuracy, 93.41%, is the highest of models so far.

The model's precision, 73.08%, is the second highest of the models so far (with Decision Tree being higher).

The model's F1 Score, 73.79%, is the highest of models so far.
***
## Extra Tree Evaluation
![extra_tree.png](https://github.com/wswager/san_bay_tel/blob/main/images/confusion_matrix/extra_tree.png)

The model's accuracy, 96.41%, is the highest of models so far.

The model's precision, 97.56%, is the highest of models so far.

The model's F1 Score, 86.96%, is the highest of models so far.
***
## Gradient Boosting Evaluation
![gradient_boosting.png](https://github.com/wswager/san_bay_tel/blob/main/images/confusion_matrix/gradient_boosting.png)

The model's accuracy, 96.70%, is the highest of models so far.

The model's precision, 97.61%, is the highest of models so far.

The model's F1 Score, 88.17%, is the highest of models so far.
***
## Random Forest Evaluation
![random_forest.png](https://github.com/wswager/san_bay_tel/blob/main/images/confusion_matrix/random_forest.png)

The model's accuracy, 97.01%, is the highest of models so far.

The model's precision, 97.50%, is the second highest of models so far (with Gradient Boosting being higher).

The model's F1 Score, 85.71%, is the third highest of models so far(with Gradient Boosting and Extra Trees being higher).
***
## XG Boost Evaluation
![xg_boost.png](https://github.com/wswager/san_bay_tel/blob/main/images/confusion_matrix/xg_boost.png)

The model's accuracy, 97.30%, is the highest of models so far.

The model's precision, 100.00%, is the highest of models so far.

The model's F1 Score, 90.32%, is the highest of models so far.
***
# Conclusion

**Based on the metrics calculated ans the valuation of the metrics stated based on the business problem, XG Boost performed best of all of the models tested.**
***
## Feature Importance
![xgb_feature_importance.png](https://github.com/wswager/san_bay_tel/blob/main/images/feature_importance/xgb_feature_importance.png)

The above feature importance indicates the the most most significant features toward predicting customer churn are the features associated with minutes, with the top four features being:
* Daytime Minutes - F-Score: 446
* Evening Minutes - F-Score: 440
* Night Minutes - F-Score: 294
* International Minutes - F-Score: 233

(All remaining features drop to F-Scores between 159 and 99)
***
# San Bay Tel
![bridge_logo.jpg](https://github.com/wswager/san_bay_tel/blob/main/images/bridge_logo.jpg)
***
![bridge_photo](https://github.com/wswager/san_bay_tel/blob/main/images/bridge_photo.jpg)
# Thank You

### Wes Swager
[Email](mail.westin.swager@lsventures.com)

[GitHub](https://github.com/wswager)

[LinkedIn](linkedin.com/in/wes-swager-36a84a2a)

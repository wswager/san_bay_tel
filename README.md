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

Data associated telecommunications customers from the San Francisco Bay area, area codes:

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
**Total Churn**: 483 

**Percentage of Churn**: 14.49 %

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
The following metrics are being calculated for each of the models tested:

* ROC Score, the measurement of the Area Under the Curve (AUC) for the Receiver Operating Characteristic (ROC), a plot of True Positive Rate (TPR) v False Positive Rate (FPR)

* Precision, the ratio of false negatives, instances correctly identified as churned

* Recall, the ratio of true positives, instances correctly identified as not churned

* F1 Score, the weighted average of the precision and recall values

Training and Test data metrics will be displayed to ensure overfitting is avoided.

The base metric used to evaluate the success of the models will be ROC Score, analyzing the predictive power through maximizing true positives and minimizing false positives.

San Bay Tel has requested a model predicting the likelihood of churn.  Therefore, for the purposes of the this project the next highest valued metric will be Precision, the proportion of actual customers who churned correctly classified with F1 Score considered only as a third (much lessor) metric for comparison purposes between similarly performing models.
***
## Model Fitting
The following models were fitted:
* Logistic Regression Evaluation
* Ada Boost Evaluation
* K Neighbors Evaluation
* Decision Tree Evaluation
* Extra Tree Evaluation
* Gradient Boosting Evaluation
* Random Forest Evaluation
* XG Boost
***
## Modeling Conclusion

**Based on the metrics calculated and the valuation of the metrics stated based on the business problem, XG Boost performed best of all of the models tested**

* **ROC Score: 91.80%**
* **Precision: 95.56%**
* **F1 Score: 89.58%**

![xg_boost.png](https://github.com/wswager/san_bay_tel/blob/main/images/confusion_matrix/xg_boost.png)

![xg_roc.png](https://github.com/wswager/san_bay_tel/blob/main/images/roc/xgb_roc.png)
***
# Conclusions

## Minutes
Feature Importance indicates the most most significant features toward predicting customer churn are the features associated with minutes used by the customer, with the top three overall features being:
* Daytime Minutes
* Evening Minutes
* International Minutes

The visualization for Churn by Daytime Minutes indicates a skew churn toward the higher number of daytime minutes used.

![daytime_minutes.png](https://github.com/wswager/san_bay_tel/blob/main/images/histograms/daytime_minutes.png)

This poses the question, is there a factor regarding the service which is negatively impacting customers who use more daytime minutes?
Possible factors may be:
* General quality of service in the area
* Areas of lower quality
* Decreased quality at high use times during the day
***
## Customer Service Calls
The next most important feature not associated with minutes used (or, closely associated, number of calls) is Customer Service Calls.

The visual for Churn by Customer Service Calls indicates a skew for churn toward customer with greater than three customer service calls.

![customer_service_calls.png](https://github.com/wswager/san_bay_tel/blob/main/images/histograms/customer_service_calls.png)

Further investigation reveals **51.68%** of customers with greater than three customer service calls churn v **11.25%** of customers with three or less.

This poses questions such as:
* What are the questions and/or issues customers are calling about?
* Can the individual questions and/or issues be resolved to a more satisfactory level (within reason of the overall business-model) so as to retain customers?
* Are there recurring questions and/or issues across customer service calls which can be addresses at a macro-level?
* Are customers satisfied with their interactions with customer service; what is customers' perception of the quality of customer service?
***
# Voicemails
The next most important feature after Customer Service Calls is Number of Voicemail messages.

The visual for Churn by Number of Voicemail Messages indicates a much higher churn rate amongst customers with zero voicemails, which is consistent with Churn by Voicemail Mail, which indicates a significantly higher rate of churn amongst customers without a voicemail plan (who would therefore have zero voicemails).

![number_of_voicemails.png](https://github.com/wswager/san_bay_tel/blob/main/images/histograms/number_of_voicemails.png)
![voicemail_plan.png](https://github.com/wswager/san_bay_tel/blob/main/images/histograms/voicemail_plan.png)

Further investigation reveals **83.44%** of customers who churn do not have a voicemail plan.

This poses the questions:
* Are customers aware of the voicemail plan?
* Are sales associates educating customers about the voicemail plan and encouraging it?
***
# Next Steps

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

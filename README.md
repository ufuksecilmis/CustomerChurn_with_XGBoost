# Customer Churn Prediction 

![Title](https://github.com/ufuksecilmis/CustomerChurn_with_XGBoost/assets/51096261/65966cab-b18c-40d4-8006-775e1f2fd78b)
 
Customer churn refers to the percentage of customers who have ceased purchasing a business's products or services within a specific time frame. Given the substantial cost associated with acquiring new customers, companies are naturally inclined to retain their existing ones. Consequently, the ability to predict whether a customer is likely to leave or remain is of paramount importance for companies.

# Steps
1.Conduct Exploratory Data Analysis using pandas-profiling.

2.Perform Data Preprocessing, including imputation and one-hot encoding.

3.Build an XGBoost Model.

4.Construct a LightGBM Model.

5.Select the Best Model through Cross-Validation and ROC-AUC analysis.  As the recall metric is very important for this case, the model with the highest recall is chosen.

6.Utilize SHAP for Model Interpretation.

# Dataset
Telco Customer Churn

## Data Description

7043 observations with 19 variables

CustomerID: A unique ID that identifies each customer.

Gender: The customer’s gender: Male, Female

Senior Citizen: Indicates if the customer is 65 or older: Yes, No

Partner: Indicate if the customer has a partner: Yes, No

Dependents: Indicates if the customer lives with any dependents: Yes, No. Dependents could be children, parents, grandparents, etc.

Tenure: Indicates the total amount of months that the customer has been with the company by the end of the quarter specified above.

Phone Service: Indicates if the customer subscribes to home phone service with the company: Yes, No

Multiple Lines: Indicates if the customer subscribes to multiple telephone lines with the company: Yes, No

Internet Service: Indicates if the customer subscribes to Internet service with the company: No, DSL, Fiber Optic, Cable.

Online Security: Indicates if the customer subscribes to an additional online security service provided by the company: Yes, No

Online Backup: Indicates if the customer subscribes to an additional online backup service provided by the company: Yes, No

Device Protection: Indicates if the customer subscribes to an additional device protection plan for their Internet equipment provided by the company: Yes, No

Tech Support: Indicates if the customer subscribes to an additional technical support plan from the company with reduced wait times: Yes, No

Streaming TV: Indicates if the customer uses their Internet service to stream television programing from a third party provider: Yes, No. The company does not charge an additional fee for this service.

Streaming Movies: Indicates if the customer uses their Internet service to stream movies from a third party provider: Yes, No. The company does not charge an additional fee for this service.

Contract: Indicates the customer’s current contract type: Month-to-Month, One Year, Two Year.

Paperless Billing: Indicates if the customer has chosen paperless billing: Yes, No

Payment Method: Indicates how the customer pays their bill: Bank Withdrawal, Credit Card, Mailed Check

Monthly Charge: Indicates the customer’s current total monthly charge for all their services from the company.

Total Charges: Indicates the customer’s total charges, calculated to the end of the quarter specified above.

Churn Label: Yes = the customer left the company this quarter. No = the customer remained with the company.


# Model Results

![Model_Results](https://github.com/ufuksecilmis/CustomerChurn_with_XGBoost/assets/51096261/244fc6fc-2efe-44f1-aedf-3f504af8a5f4)

![XGB_CONF](https://github.com/ufuksecilmis/CustomerChurn_with_XGBoost/assets/51096261/65991614-1dbd-46af-8394-cb08b66f9f65)

![LIGHTGBM_CONF](https://github.com/ufuksecilmis/CustomerChurn_with_XGBoost/assets/51096261/4ecd71ba-367e-4f99-a68e-3bb9811aba84)

![Classification Report](https://github.com/ufuksecilmis/CustomerChurn_with_XGBoost/assets/51096261/92475017-7d07-4821-b921-f5053f207a28)

![ROC](https://github.com/ufuksecilmis/CustomerChurn_with_XGBoost/assets/51096261/7021212e-378f-472d-9183-0e7f58ee7884)

**Result: If we possess sufficient computational power and time, selecting XGBoost is viable. Conversely, if our computational resources and time are limited, choosing LightGBM serves as a suitable alternative. In this scenario, we will move forward with the XGBoost model.**

# Model Interpretation

**The waterfall plot indicates that when a customer does not have a month-to-month contract, the logarithm of odds of churn decreases by 0.25. Moreover, customers who have a longer tenure with the company  are less likely to churn.**
![Waterfall_1](https://github.com/ufuksecilmis/CustomerChurn_with_XGBoost/assets/51096261/6b8fc6fc-8b58-4517-9a71-c4d4e18f699c)

**As observed, the "contract_month-to-month" option has the most significant impact. This is logical because if a customer renews their contract on a monthly basis, they are more likely to switch to a different carrier in the following month.**
![MEAN_SHAP](https://github.com/ufuksecilmis/CustomerChurn_with_XGBoost/assets/51096261/65ee7299-7f05-478e-9c16-51bed40543d3)

![BeeSwarm](https://github.com/ufuksecilmis/CustomerChurn_with_XGBoost/assets/51096261/9d747f0d-868d-49cf-8548-a29a7ff94a23)


# Further Improvements

1. Different prediction thresholds other than 0.5 can be applied. Decreasing the prediction threshold is advisable to decrease False Negatives. However, if the business can accept a higher number of False Positives, then reducing the prediction threshold might be considered.

2. An ML app can be developed using either Streamlit or Flask.



# Customer Churn Prediction 
 
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

Churn Label: Yes = the customer left the company this quarter. No = the customer remained with the company. Directly related to Churn Value.

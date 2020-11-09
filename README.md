# FraudDetection
Fraud Detection for online payments for Vesta Corporation ( Data Science Challenge)
 
# Background
Company : Vesta Corporation
Service : Guaranteed e-commerce Payments
Size : More than $18B in transcations annualy as of 2019
Problem :Vesta’s current Fraud Detection Algorithm has seen
 Increase in numbers of FALSE POSITIVES 
Significant misclassification rates in existing model
Existing fraud detection algorithm frequently flags many non-fraud transactions as fraud
  
 # Business Impact
## Impact of Current Classification Algorithm :
“Increased Customer frustration”
“Loss from fraud transactions that could have been avoided ”
“Increased costs due to unnecessary fraud alerts”
## Desired Solution : Improve Customer Experience
“Improved efficacy of fraudulent transaction alerts”
via An improved Fraud Detection Model with an optimal probability threshold to
Reduce false positives
Increase prediction accuracy
 
# Literature
## WHAT’S BEEN DONE 
http://www.ecmlpkdd2018.org/wp-content/uploads/2018/09/567.pdf
https://www.researchgate.net/publication/325589159_Reducing_false_positiv es_in_fraud_detection_Combining_the_red_flag_approach_with_process_min ing
https://www.researchgate.net/publication/327889886_An_Artificial_Intelligen ce_Approach_to_Financial_Fraud_Detection_under_IoT_Environment_A_Surv ey_and_Implementation
## WHAT’S NEW
Reducing False-Positives using Dense Neural Networks ( Deep Learning in Python)
Penalty for misclassification in the form of a custom weighted cost metric for FP & FN
Ability to quantify loss from misclassification incurred by Vesta Corporation

  
 #Data Description : Collection & Challenges
Data Source : Data sets provided by Vesta Corporation as part of IEEE CIS Fraud Detection data challenge
Size : 590540 rows 434 columns
	‘IsFraud’ Categorical (0,1)
Structure: 
Data is available in two sheets : Transaction and identity
Transaction data includes:
● Target Variable
● Transaction amounts
● Card used, card type
● Variables related to name and address
● Other vesta engineered features
    Identity data includes variables collected by:
● Vesta’s fraud protection system
● Digital security partners
  
 #Data Exploration : Univariate and bivariate plots
● Plotted Univariate graphs to understand the spread of data
● And, bivariate boxplots to check variables’ spread within fraud and non-fraud
segments
     
 #Data Exploration: Interesting data points
75% of the transactions fall under one product code and have 40% lower fraud rate compared to overall
   
 ## Data Exploration: Card company
● Discover customers are transacting about 7 times more compared to other credit card customers and have twice the fraud rate.
● Discover constitutes to only 1% of transactions though
    
 ## Data Exploration: Card type
 ● Transactions per debit card is 4 times that of credit card
● Credit cards have 2.75 times the fraud rate of debit cards
   
 ## Data Exploration: Email domain
 ● Customers using gmail & hotmail have higher fraud rates compared to those using yahoo and others
   
 # Data Transformation : Pre-Processing
Dealing with Missing data :
● There are 41 4 columns of missing data in the dataset
● For the numerical columns, imputed based on median values
Dealing with Categorical variables:
● Converting to Number: Used Label Encoder in transforming to numerical variables
● Dummy Variables creation: Created dummy variable for each level present
  
  # Data Transformation : Pre-Processing
Log Transformation for variables:
For few variables, we have transformed using the logarithmic transformation, this helps us to scale down the extreme values and make them more linear
   
  # Data Transformation : Tackling class imbalance
Class imbalance can result in bias towards the majority class ( isFraud=0 ) Reducing classification performance
Increasing the number of false negatives
       Resampling
● Oversampling ● Undersampling
 Remedy
Chosen Method : Undersampling
ONLY 3.5% of records have isFraud =1
  
  ## Data Transformation : Undersampling in Python
DRAWBACKS
● Maybe removing information that may be valuable.
● Could lead to underfitting
  EQUAL % of both classes
  
  # Predictive Modeling :
Models built
1. Logistic Regression
2. Random Forest
3. Dense Neural Networks
4. Extreme Gradient Boosting
5. Support Vector Machine
6. Decision Trees
Top 3 Models
1. Dense Neural Networks
2. Extreme Gradient Boosting
3. Logistic Regression
  
  Predictive Modeling : Dense Neural Network
     
  Predictive Modeling : Extreme Gradient Boosting (XGB)
     
  Predictive Modeling : Logistic Regression with Hyperparameters Tuning
Hyperparameters tuning:
•Used GridSearchCV method to tune hyperparameters for choosing the best parameters for optimal model. •GridSearchCV is an exhaustive search over specified parameter values for an estimator.
•The model with tuned parameters has performed well with higher
precision and accuracy. Increase in accuracy from 57% to 75%
      
 Model Evaluation
Criteria used for Model Comparison
● Precisión
● Recall
● F1
● Weighted Cost ( Custom)
● ROC Area Under the Curve
   In the current problem , the focus is develop a classifier that reduces the number of false-positives. Since Precision tells us what percent of positive (fraudulent) predictions were correct, and Recall tells us what percent of the positive (fraudulent) cases did you catch? our focus is more on these metrics (F1)
    NOTE : Although Accuracy is a simple and "intuitive" measure, yet it may be a poor measure for imbalanced data. Weighted cost attempts to quantify the loss incurred by Vesta if the model misclassifies fraud-transactions as Non-Fraudulent.
 
 Model Comparison:Precision, Recall, F1 - Score
Best Model : Dense Neural Network is our choice for best model as it has both high precision, high accuracy and low weighted cost

  Findings
  Desktop transactions account for larger fraud numbers compared to mobile
Discover customers are transacting about 7 times more compared to other credit card customers and have twice the fraud rate
 
  Findings
75% of the transactions fall under ol.
 75% of the transactions fall under one product code and have 40% lower fraud rate compared to overall.
 Credit cards have 2.75 times the fraud rate of debit cards
 
 Recommendations
Vesta Corporation could
● enhance payments security protocols for all transactions made through Desktop devices
● pay more attention to transactions from customers using Discover Cards as they have higher fraud rates than other card types
● examine payments/ transactions made through credit card and implement fraud prevention techniques for this category
 
  Thank you for your patience Q&A

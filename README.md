# Welcome to the Bike Sharing project

## Business Goal:
This project is to model the demand for shared bikes with the available independent variables. It will be used by the management to understand how exactly the demands vary with different features. They can accordingly manipulate the business strategy to meet the demand levels and meet the customer's expectations. Further, the model will be a good way for management to understand the demand dynamics of a new market. 

### Data Preparation:
- Dataset "day.csv" originally has shape of 730 rows and 16 columns 
- After removing unnecessary columns, it remains 7 catagorical features and 4 numerical features. The target variable is column 'cnt'.
- The 7 catagorical features are converted to dummy variables

### Model Building
- The dataset is splitted in to train and test datasets at 0.7-0.3 ratio respectively
- StandardScaler is used to fit the train dataset
- Features selection adopts VIF, p-value and RFE in combination. All features have VIF > 5 and p-value > 0.05 are removed.

### Model Evaluation:
- After selecting appropriate features as expected, the model is run
- Residuals analysis is conduct to validate the normality assumption of error terms. The scatter plot and histogram plot show error terms fairly normally distributed, while Q-Q plot shows it is not well normally distributed, but I hold this assumption that error terms follow normal distribution for next analysis.
- Once assumption is confirmed, the test dataset is predicted and the final model is evaluated, the R2 score - test =  0.81 and others as folowing: R2 score - train =  0.85 , MAPE score - train =  0.46, R2 score - test =  0.81, MAPE score - test =  0.19, Corr_test:  0.90
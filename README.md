## Analysis Summary

The purpose of this model is to predict the risk level associated with issuing a new line of credit to a client based on factors including loan size, interest rate, borrower income, borrower debt to income ratio, borrower number of acounts, borrower debt, and borrower derogatory marks. The model is designed to indicate if, based on this same existing data from previous borrowers, a new loan would likely result in a healthy loan or a high-risk loan, meaning the client is likely to fail to repay the loan. 

In summary, this model is designed to assess if a loan is likely to be a healthy loan or a high-risk loan (indicating high likeliness to default) based on details about the loan and of the borrowers finances. 

Existing borrower data and loan status was used to train the model using the SKLearn Library. First, the data was split into training and testing data using the default ratio of 75% training data and 25% testing data. Following this step a logistic regression model was instantiated using the SKLearn library, with the solver set to 'lbfgs' and a random state of 1 to ensure reproducibility of the results. The logistic regression was then fit to the training data deliniated above. Logistic regression was selected because this model outputs a binary prediction, in this case indicating if a loal is likely to be either healthy or high-risk. 

Next, the resulting logistic regression model was applied to the test data to produce preditions of either 0 or 1, 0 indicating a healthy loan and 1 indicating a high-risk loan. 

Finally, a confusion matrix and classification report were used to demostrate the effectiveness of the model in predicting loan status of known loans to identify its reliability for future unknown loans. 

## Results

- For healthy loans the logistic regression model produced the following indications of reliability:
    - Precision: 1.00
        This indicates that every loan the model predicted would be health was in fact a healthy loan. 
    - Recall: 0.99
        This indicates that the model captured 99% of the truly healthy loans and predicted they would be healthy
-For high risk loans the logistic regression model produced the following indications of reliability: 
    - Precision: 0.85
        This indicates that 85% of loans that the model predicted would be high-risk were truly high risk.
    - Recall: 0.91
        This indicates that 91% of the truly high risk loans were included in the predicted high-risk group.
-Overall the average precision of the model was 92%, and 99% of it was weighted based on the number of high risk and healthy loans. 

## Summary

The distribution of precision and recall scores for both categories indicates that model somewhat favors correctly classifying healthy loans, or in other terms, it is not likely to indicate that a true high risk loan is healthy. In the case of issuing lines of credit, favoring misclassification that results in declining potentially healthy loans is probably preffered over the reverse misclassification because it results in less risk for the credit issuer. 
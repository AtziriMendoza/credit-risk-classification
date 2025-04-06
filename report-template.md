# Module 12 Report Template

## Overview of the Analysis

In this section, describe the analysis you completed for the machine learning models used in this Challenge. This might include:

* Explain the purpose of the analysis.
    The purpose of the analysis is supposed to be to see if we can predict if a client's loan will be high risk or healthy, which is important for the bank to determine to ensure that the borrower will pay the loan back. The bank can make this prediction based on the features of a healthy loan and unhealthy loan. 

* Explain what financial information the data was on, and what you needed to predict.
    The financial data was on mortgage loans and it takes aspects that are important in determining whether a loan will receive an underwriting final approval such as the size of the loan amount, income, interest rate, debt to income ratio, liabilities (revolving accounts that are open), derrogatory marks on their credit, their total debt,  and whether the loan was approved or denied in the laon status.

    The model that we created attempts to predict whether or not a loan will be approved or denied based on the above features (minus the 'loan status' since that is what we are predicting). The features will be used to predict whether a loan will be approved or denied which these features do give enough information on whether a loan will be approved or denied, I would say we are missing a critical component which is credit score that is a feature that I would add. 

* Provide basic information about the variables you were trying to predict (e.g., `value_counts`).
    We were trying to predict 'loan_status'. A zero would indicate an approval (healthy loan) while a 1 would indicate a denial (unhealthy loan). 

* Describe the stages of the machine learning process you went through as part of this analysis.
    we got a dataset that had contained the aspects we needed to train the model to predict whether a loan would be approved or denied. We set the y variable as the 'loan_status' because that is the dependent variable. We set the X variable as the features (independent variables) which contained 'loan_size', 'interest_rate', 'borrower_income', 'debt_to_income', 'num_of_accounts', 'derrogatory_marks', 'total_debt', and 'loan_status'. We split the data into training and testing sets. We made a logistic regression model by using the training data set for the model. We then made the predictions on the testing data labels by using the testing feature data. We then generated a confusion matrix which tells us about the True Positives (amount of times that the model correctly predicted yes), False Negatives (amount of times the model predicted no but it was yes), False Positives (amount of times the model predicted yes but it was no), and True Negatives (amount of times that the model correctly predicted no) that were generated int his model. The confusion matrix is very important because this helps us calculate important metrics such as accuracy, precision, and recall which were calculated in the classification report which includes the f-1 score that represents a balance between precision and recall. 
    
* Briefly touch on any methods you used (e.g., `LogisticRegression`, or any other algorithms).
    We did use logistic regression to see how well our test data set that was used for predictions fit our trained data set.Logistic Regression uses a signmoid function to output probabilities by taking information and classifying it into a binary (yes/no or true/false) or multi-class (predicting whether something is an animal such a cat, dog, rabbit, etc). Logistic regression tells how likely a loan is to be approved or denied based on the features of the data. 

## Results

Using bulleted lists, describe the accuracy scores and the precision and recall scores of all machine learning models.

* Machine Learning Model 1:
    * Description of Model 1 Accuracy, Precision, and Recall scores.
    -Accuracy: is how good the model was at predicting true negatives and true positives by taking the sum of both TN + TP and dividing it by the total predictions.
    -Precision: is measuring how often the model is right when it tells us that a loan is approved. So it takes the true positives and true negatives and divides it by the total number of predictions.
    -Recall: is measuring of all approvals how many did the model actually correctly define as approvals. We do this by measure all true positives and dividing it by the sum of the true positives and false negatives.

## Summary

Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. For example:

* Which one seems to perform best? How do you know it performs best?
    I liked the logistic regression model that we used I think that it performs quite well in identifying healthy loans. We can tell that it does a good job at this by seeing the accuracy score of the model in the classification report and confusion matrix.

* Does performance depend on the problem we are trying to solve? (For example, is it more important to predict the `1`'s, or predict the `0`'s? )

    I think that the effectiveness of the machine learning model is dependent on the size of the company. For example, I think a big bank can recoup the loss of incorrectly allowing a loan that should be denied to go pass through as an approval. 

    The model should be better at detecting the unhealthy loans but it is not and I think if we gave it more training data on loans that are denied it would be better able to predict the denials but the amount of denials (1) in the data set are much lower in comparison to the amount of approvals (0). It makes sense that it does not necessarily know other combinations of features that would create an unhealthy loan but it does know what combinations of features creates a healthy loan because that is the majority of the data. 

    I think banks want the revenue that come with healthy loans but they are more concerned with the loss that can come from approving a high risk loan. This model needs to do a better job atr predicting unhealthy loans.

If you do not recommend any of the models, please justify your reasoning.

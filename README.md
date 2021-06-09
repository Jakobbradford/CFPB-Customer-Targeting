# CFPB-Customer-Targeting

**Business Question #1:** 
What population would be most likely to use a prepaid card over a regular credit card?

Potential population considerations:
- People who have used "alternative" financial products
- People who have had issues with financial services in the past
- Had previous spending issues
- Don't know how to manage their money

**Business Question #2:**
How do we identify users with low financial literacy to implement protective measures when taking on high-interest products?

Potential risk factors:
- Poor self control
- Financial management issues
- Answers to financial wellbeing survey
- Poverty status

**Summary**

This project is focused on identifying potential users for the Consumer Financial Protection Bureau's policy and a pre-paid card product. We cleaned the data by defining an unanswered question as "REFUSED" which allowed us to remove it from the DataFrame. We used Random Forest, SVM and ADABoost as we were looking to classify users of pre-paid cards for business question 1, and users of high-interest products for question 2. 

**Model Results**

*Random Forest*

Hyperparameters: 
- n-estimators: number of trees used in the forest
- 125 produced highest recall & accuracy
- max_depth: longest path b/w root node and leaf node
- 125 produced highest recall & accuracy
```
			        BQ1		BQ2
RandomForest Recall:  		0.7013		0.5236                	
RandomForest Accuracy: 		0.9052		0.9510             	
RandomForest F1 Score:  	0.9048		0.9391            	
RandomForest Confusion Matrix:	[[1059   57]	[[1200   14]
                                 [  59   49]]	[  48    3]]
RandomForest AUC:  		0.9373		0.5496
```
*SVM*

Hyperparameters:
- Gamma: Determines the area of influence each point on the model has in creating the hyperplane
- 100 produced highest recall & accuracy
```
			 	BQ1		BQ2
SVM Recall:  			0.6697		0.5159		
SVM Accuracy: 			0.9085		0.9542 			
SVM F1 Score: 			0.9038		0.9397 			
SVM Confusion Matrix:		[[1071   45]    [[1205    9]
 				[  67   41]]	[  49    2]]
SVM AUC: 			0.7143		0.5626
```
*ADABoost*

Hyperparameters:
- n-estimators: boosting terminated after this amount
- 15 produced highest recall & accuracy
```
					BQ1		BQ2
ADABoost Recall: 			0.6139		0.5			
ADABoost Accuracy:  			0.9060 		0.9596			
ADABoost F1 Score: 			0.8946		0.9399 			
ADABoost Confusion Matrix: 		[[1081   35]	[[1214    0]
 					[  80   28]]	[  51    0]]
ADABoost AUC: 				0.9336    	0.7445
```

**Conclusion and Insights**

Business Question 1 Insights:

The random forest model had the highest predictive power with an F1 score of 0.9048 (BQ1). The variables which contributed most to this conclusion were history with credit, spending habits and issues with financial services in the past. This model is not only effective at predicting 0's (non-users of the product) but effective at predicting viable candidates. It's highly probabable those who were "rejected from using credit" when applying for a credit card turn to alternative products such as prepaid cards, which positively contributed to the models predictive power.

Business Question 2 Insights:

Conversely, the model displayed low predictive power for business question 2, failing to predict 1's accurately. Hyperparameter tuning had little effect on the outcome of the analysis. This is likely attributed to the low sample size of 25/1200+ who reported using high-interest products. It's most likely that the population surveyed had difficulty obtaining high-interest products, which made it difficult for the model to establish any predictive ability. Data from a different population would need to be collected to further this analysis. Despite this, it's possible for the CFPB to give at-risk users financial education resources after completing the survey in an attempt to better inform users.






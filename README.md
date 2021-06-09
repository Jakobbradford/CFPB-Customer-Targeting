# CFPB-Customer-Targeting

**Business Question #1:** 
What population would be most likely to use a prepaid card over a regular credit card?

Potential population considerations:
- People who have used "alternative" financial products
- People who have had issues with financial services in the past
- Had issues with spending issues
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

```
			        BQ1		BQ2
RandomForest Recall:  		0.7013		0.5236                	
RandomForest Accuracy: 		0.9052		0.9510             	
RandomForest F1 Score:  	0.9048		0.9391            	
RandomForest Confusion Matrix:	[[1059   57]	[[1200   14]
                                 [  59   49]]	[  48    3]]
RandomForest AUC:  		0.9373		0.5496
```
```
			 	BQ1		BQ2
SVM Recall:  			0.6697		0.5159		
SVM Accuracy: 			0.9085		0.9542 			
SVM F1 Score: 			0.9038		0.9397 			
SVM Confusion Matrix:		[[1071   45]    [[1205    9]
 				[  67   41]]	[  49    2]]
SVM AUC: 			0.7143		0.5626
```
```
					BQ1		BQ2
ADABoost Recall: 			0.6139		0.5			
ADABoost Accuracy:  			0.9060 		0.9596			
ADABoost F1 Score: 			0.8946		0.9399 			
ADABoost Confusion Matrix: 		[[1081   35]	[[1214    0]
 					[  80   28]]	[  51    0]]
ADABoost AUC: 				0.9336    	0.7445
```






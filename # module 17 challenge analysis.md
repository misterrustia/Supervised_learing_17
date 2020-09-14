# module 17 challenge analysis 

## credit_risk_ensemble classifer analysis 

The objective of this notebook was to evalute the supervised learning of two different classifiers from the 
imblearn library, one being Easy Ensemble AdaBoost Classifier and the other , Balanced Random Forest Classifier. 




###  Easy Ensemble AdaBoost Classifier
This classifier uses a boosting method that fits multiple copies of the orignial classifiers results one after the other but changes the weights of incorrectly classified instances so that later classifiers dont replicate the previous exact results. The data was not amplified in any way before the classifier was given training data so when predicions were created they scored fairly poorly when compared to the testing data. for High Risk Loans the precision was  0.03 meaning there were lots of false positives, this could cause a lot of people who have low risk loans to be classified as having high risk loans. The recall was .92  showing  there were few false positives  and few  High Risk Loans were being predicited to be low risk which cat least does not leave lenders vulnerable to many lenders that could default on payments.
The classification report does not allow me to recomend this classifier with out more fine tuning to allow for greater precision. 

### Balanced Random Forest Classifier 
This classifier used 128 tress to interact with the training data and got a percision of 0.03 and a recall of .67. This classifiers  incorrecly predicited 1863 low risk loans as high risk and could limit access to credit to many credit worthy applicants. The recall also shows about a third of the High Risk Loans were predicited to be low risk and could leave the leanders vulnerable to lenders who could default. The classification report does not allow me to recomend this classifier with out more fine tuning to allow for greater precision. 


## Credit Risk Resampling Techniques

The objective of this notebook was to evaulate which resampling technique were more effective in dealing with the class inbalance between the smaller high risk loans and the larger  low risk loan class. The sampling techinques used were Oversampling, SMOTE Oversampling and Undersampling. 




### Random Oversampling
Random oversampling makes copies of the smaller High Risk class so that both classes are equal before the are given to the linear regression model to make predicitions. the precision for the high risk loans was .01 and the recall for the high risk loans was .63. these values are very low and could be due to the copies of the small high risk class sample generating a lot of oversampling in the predicitons thus having lots of miss clasified low risk loans as high risk. 


### SMOTE Oversampling
new syntheic centroids are created from the minor class to balance the two classes out before predicitons are made. the high rick precision was .01 and the recall was .63, which are identical to the random oversampling and still shows overfiting likeyly not allowing for quality predictions. 

### Undersampling
Undersampling is where the major class is cut down to match the minor class.The minor class precision was still .01 and the recall was .55, this techique had the lowest scores of all three techniques. cutting down the data points caused for there to be even lower quality predicitions than in the other two sampling techniques. 


## additinal use of SMOTEEEN sampling and Random forrest classifier 
after working throught the different predicitive models and sampling technqiues I chose to try to combine some of the techniques from the module to attempt to get better predicirve scores than what I had already encountered. I used the SMOTEEN sampling technique with the testing x and y then a random forrest classifier to create the predicitions for my final attempt. for the High risk i got a precision of .83 and a recall of 
.35. for the low risk i got a precision of 1 and a recall of 1. this garnered the greatest f1 scores of all of the kinds of sampling attempted. since there was only 6 low risk loans misclassified as high risk I feel that the combination of these two techinques would be the best choice for the credit company as there would be the least change of giving loans to high risk lenders if new data was given to this model. 
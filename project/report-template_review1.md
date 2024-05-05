# Report: Predict Bike Sharing Demand with AutoGluon Solution
#### Harlem Arol RAKOTONANDRASANA

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?
When I try to submit my prediction, I realize that the rmse score is high. For that, I need to do exploratory data analysis on my data. 
1-change the format of the features: parse date 
2-specify some categorical data type that was considered as integer: season, weather, holiday and workingday
3-delete and ignore some columns that have none correlation on the target: datetime after sepating them, casual and registered
4-The submission on Kaggle does not accept negative value. So I need to make those value 0.

### What was the top ranked model that performed?
My top rank model is the WeightedEnsemble_L3 with a validation rmse score of 32.577257

## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?
Exploratory analysis finds that some features need to be precise and not make confusing like the datetime column and some integer data type that need to be changed in categorical.
 . The data time is originaly with object data type and should be changed in datetime so parse date is applyied
 . I add additional features by splitting separate column the year, month, hour and dayoff from the datetime column. So the datetime column did have no longer correlation with the target so it is dropped from the data.
 . Graph visualization using histograph gave me insight that there are some columns type categorical like season, weather, holiday and workingday. So I convert them into categorical data type.


### How much better did your model preform after adding additional features and why do you think that is?
My model after adding more features performed better as the score was improved. Kaggle score shows that initialy it is from 1.80753 to 0.47464. I think that splitting the date and categorized data help the model to learn more the correlation between the features and the target.

## Hyper parameter tuning
### How much better did your model preform after trying different hyper parameters?
After trying different hyper parameters, the score was slightly improved. The Kaggle score was 0.47464 to 0.46057. I tryed to evaluate 2 different model by optimizing hyper parameter (changing default value). 1rst uses 4 ensemble different model and the 2nd uses 2 ensemble different model. There are no real changed in result because both of them give Kggle score of 0.46057.

### If you were given more time with this dataset, where do you think you would spend more time?
If I given more time with this dataset, I think I would spend more time on features engineering and also try to improve my choice of hyperparameter.

### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.
|model|hpo1|hpo2|hpo3|score|
|--|--|--|--|--|
|initial|Default|Default|Persets: Best quality|1.80753|
|add_features|Dates parsing|Feature Engineering|Persets: Best quality|0.47464|
|hpo|GBM, KNN, XGB|Optimize Hyperparameter|Bagging, Stack|0.4605|



### Create a line plot showing the top model score for the three (or more) training runs during the project.

TODO: Replace the image below with your own-.

![model_train_score.png](img/model_train_score.png)

### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.

TODO: Replace the image below with your own.

![model_test_score.png](img/model_test_score.png)

## Summary
I get my best model on the hyperparameter optimization methode

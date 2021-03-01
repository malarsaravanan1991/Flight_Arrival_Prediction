# Predicting Arrival Times for Denver airport using Random Forests and Naive Bayes

Correlation matrix of independent varaible with dependent variable
![matrix](https://github.com/malarsaravanan1991/Flight_Arrival_Prediction/blob/main/correlation_matrix.PNG)

## Models Tried:

* Random Forest Regressor
* Random Forest Classifier
* Naive Bayes Gaussian Classifier

## Random Forest Models:
Significance of the variables in predicting the Arrival Delay as identified by the Random Forest model:

![Plot](https://github.com/malarsaravanan1991/Flight_Arrival_Prediction/blob/main/VariableImportance_plot.PNG)

### Hyper-Parameter Tuning: The following are the Random Forest Parameters that we care going to experiment with to find the best parameters.

* n_estimators = number of trees in the forest
* max_features = max number of features considered for splitting a node
* max_depth = max number of levels in each decision tree
* min_samples_split = min number of data points placed in a node before the node is split
* min_samples_leaf = min number of data points allowed in a leaf node
* bootstrap = method for sampling data points (with or without replacement)

### Best Parameters:

* n_estimators : 400
* min_samples_split : 10
* min_samples_leaf : 1
* max_features : 'auto'
* max_depth : 20
* bootstrap : True
* ArrDelay categories for Random Forest Classifier Model:

### Classification bin labels
* Less than -30 minutes : Very Early
* Less than 0 minutes & Greater than or equal to -30 minutes : Early
* 0 minutes to 5 minutes : Ontime
* 5 minutes to 30 minutes : Late
* Greater than 30 minutes : Very late.

# Conclusion:
The accuracy of our Random Forest Classification is 81% while our Naive Bayes Classification is only 70%. We were able to generate the best Random Forest Classifier by hyper-parameter tuning. However we did could not do hyper-parameter tuning on the Naive Bayes classifier as it is so naive that it doesn't accept parameters except priors which we don't know.

# Reference:
* Convert the time columns in HH:MM:SS format - https://www.cedwards.info/projects/airline/
* Remove outlier / IQR - https://stackoverflow.com/questions/50461349/how-to-remove-outlier-from-dataframe-using-iqr
* Hyper parameter tuning - https://towardsdatascience.com/hyperparameter-tuning-the-random-forest-in-python-using-scikit-learn-28d2aa77dd74
* RandomizedSearchCV - https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.RandomizedSearchCV.html
* Column bin in pandas - https://stackoverflow.com/questions/45273731/binning-column-with-python-pandas
* Naive bayes tuning - https://stackoverflow.com/questions/39828535/how-to-tune-guassiannb

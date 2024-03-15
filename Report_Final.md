# Report: Predict Bike Sharing Demand with AutoGluon Solution
Ramkumar M 
Date - 15-March-2024

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?

Model performance is low, as I have not performed any feature engineering. This can be due to datetime feature which is not split into month, day, year etc. 

Also while submitting it is important to remove negative values in predictions that it will be accepted in kaggle submission


### What was the top ranked model that performed?

From all the experiments that I have performed it appears that WeightedEnsemble type models are performing well compared to other model. This is an ensemble type of model -  WeightedEnsemble refers to a method for combining predictions from multiple models. 

**Experiment 1 - Base experiment**

- WeightedEnsemble_L3  - RMSE 1.77810

**Experiment 2 - Feature Engineering**

- WeightedEnsemble_L3   - RMSE 0.46778

**Experiment 3 - HPO**

- WeightedEnsemble_L2  - RMSE 0.50189


  From the above values we can see that WeightedEnsemble_L3 model from experiment 2 has performed well.

  ---
  

## Exploratory data analysis and Feature creation


![Exploratory Data Analysis](images/exp1.png)

### What did the exploratory analysis find and how did you add additional features?

Key Finding 
- There are no missing values in the data
- **Datetime**: It seems to have a uniform distribution except for some gaps, which might represent missing data or no bike rentals during specific periods (likely night hours). Additional features like hour, day, month, and year could be extracted to capture the cyclical nature of time, which can affect bike rental frequency.
- **Season**: This categorical feature has four distinct values likely representing the four seasons. Since it is categorical, no further feature engineering is necessary besides possibly ensuring it's treated as a categorical variable during modeling.
- **Workingday**: There's a noticeable balance between working days and non-working days, which may significantly influence rental patterns.
- **Temp and Atemp**: These two features show a somewhat bell-shaped distribution, indicating that there are common average temperatures where bike rentals occur.

### How much better did your model preform after adding additional features and why do you think that is?
TODO: Add your explanation

## Hyper parameter tuning
### How much better did your model preform after trying different hyper parameters?
TODO: Add your explanation

### If you were given more time with this dataset, where do you think you would spend more time?
TODO: Add your explanation

### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.
|model|hpo1|hpo2|hpo3|score|
|--|--|--|--|--|
|initial|?|?|?|?|
|add_features|?|?|?|?|
|hpo|?|?|?|?|

![Table](images/table.png)

### Create a line plot showing the top model score for the three (or more) training runs during the project.

TODO: Replace the image below with your own.

![model_train_score.png](images/score.png)

### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.

TODO: Replace the image below with your own.

![kaggle Score](images/kaggle_score.png)

## Summary
TODO: Add your explanation

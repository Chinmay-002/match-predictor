# **Cricket Match Outcome Predictor**

## **About**

Project repository for SC1015 (Introduction to Data Science and Artificial Intelligence)
Uses IPL Complete Dataset 2008-2020 (https://www.kaggle.com/datasets/patrickb1912/ipl-complete-dataset-20082020), obtained from Kaggle.
The dataset contains CSV files which provide essential data relating to 816 cricket matches played in the Indian Premier League between the years of 2008 and 2020.

## **Contributors**

@chinmay-002

@shikharjain1802

@emmanuelmthomas

## **Problem Definition**

Can the outcome of a cricket match be predicted using the initial 75% of the data from both innings? If so, how accurately?
Which Machine Learning algorithm (classification or regression) would be optimal for this prediction?

## **Models Used**

#### Multivariate Linear Regression
#### Random Forest Classification

## **Process**

#### Preparing the Data:

* Cleaned the dataset by removing data from abandonded or incomplete matchs and other outlier data.
* Created 5 predictor variables by manipulating the provided dataset: 
   * current score 
   * wickets left
   * weighted economy
   * average strike rate
   * average runs of current batsmen
* Response variable: **Outcome** of the match (Calculated from the predicted final scores of each team)

##### Multivariate Linear Regression:
* Used 75:25 train-test data split in order to train the model.
* Obtained multivariate regression equation with coefficients for each of the predictor variables.
* Plotted resultant regression line that predicted final score of an innings.
* Compared final scores of each team to predict the outcome of the match.
* Accuracy: **73.45%**

##### Random Forest Classification:
* Used 75:25 train-test data split in order to train the model.
* Refined dataframe to combine both innings of the match into one record.
* Model uses numerous individual decision trees which return a class prediction. At the end, the majority prediction of all the trees is used to determine final outcome.
* Model predicted outcome of each match based on data from both innings.
* Accuracy: **80.80%**

## **Conclusion**

The Random Forest classification had greater accuracy than multivariate linear regression. 
Probable explanations: 
  * Random Forest predicts a class, while regression model predicts numeric value which is then compared. Therefore, regression has greater susceptibility to error. 
  * Multivariate regression used is suited to linear data, while Random Forest is better at capturing non-linearity. It is possible to predict the match outcome from 75% of the data from both innings, with accuracy of the models ranging from 73-81%.
  * The Models made use of data from only 816 matches. Accuracy can be improved significantly with greater sample size.

Other potential predictor variables not used in these models could be: 
  * historical performance of teams and players in the match
  * home team advantage 
  * effect of pitch conditions on a game
  
The Indian Premier League uses projected score metric to predict final score, which is based solely on the actuakl score of a team at any point in time. With increased accuracy, this project can potentially replace the current metric.

What did we learn from this project?

* Manipulating Pandas DataFrame to extract required variables.
* Resetting indices, sorting values, and removing redundant values.
* Pandas.DataFrame.groupby()
* Concatentation to recombine data
* Calculating cumulative sum
* Regression with multiple predictor variables
* Random Forest as an improved version of single classification tree

## **References**

* https://www.kaggle.com/datasets/patrickb1912/ipl-complete-dataset-20082020
* https://pandas.pydata.org/docs/reference/frame.html
* https://medium.com/analytics-vidhya/evaluating-a-random-forest-model-9d165595ad56
* https://towardsdatascience.com/five-regression-python-modules-that-every-data-scientist-must-know-a4e03a886853
* https://www.w3schools.com/python/python_ml_multiple_regression.asp
* https://towardsdatascience.com/all-pandas-groupby-you-should-know-for-grouping-data-and-performing-operations-2a8ec1327b5

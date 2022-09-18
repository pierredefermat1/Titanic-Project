# Titanic-Project
This was my first machine-learning project for a [Kaggle competition](https://www.kaggle.com/competitions/titanic).
With a given dataset of passanger details- build a model that can predict which kind of passangers are more likley to survive.
When I first understood my mission (classification model)- I went to the [Training Data Statistics](https://www.kaggle.com/competitions/titanic/data?select=train.csv)
to understand the features I'll work with, how many missing values per column are there and further details.
After understanding everything I needed- I went to the code section, and started to apply everything I've learned in the different courses I took, starting with
dealing with categorical values (factorizing and ordinal encoding) and making an effort to use as many features as possible, untill I would be able to
determine if they are relevant or not.
As part of the preprocessing procedure, I decided to balance my dataset (for there were more victims than survivors),  and for the dealing with the missing values
I've decided to use imputation with extansion using sklearn, i.e imputing missing values with the mean value of a specific column, and adding to the data set a
boolean value column with information about any column with missing values (e.g if a value was missing in the age column of row 2, then a True value will be seen
in the added column: "age_was_missing" in row 2).
After the dataset was ready to work with- I applied the Mutual Information methode for understanding which features were irrelevant, by understanding the dependance
between any feature to our target column ('Survived'):
![mi scores features selecting](https://user-images.githubusercontent.com/94384079/190900365-ae96ca4e-0a9e-44ad-9a60-7002b3fc7611.PNG)
Then I got rid of all the features with low correlation to our target column, and proceeded to one-hot encoding for the 'Name' coloumn when I figured there might be
a strong relation between a respectable passanger (can be inferred by it's status) to the target column.
That point was the last in the preprocessing procedure, and I was ready to train & validate my model.
I chose to use five different classification models:

1. Random Forest Classifier
2. Gaussian Naive Bayes
3. Logistic Regression
4. K nearest neighbor
5. Support Vector Machine

The score matrix containes the results each model's accuracy. Clearly- the Random forest classifier took the trophy with 84% accuracy score.
Note: For the chosen optimal values of the KNN & Random Forest I've attached 2 distributions


1. KNN 


![K nearest neighbor optimal val](https://user-images.githubusercontent.com/94384079/190901398-ac6cbbe0-a214-477c-89e8-cfbcaa4fe6dc.PNG)


2. Random forrest n_estimator 


![optimal n_estimator for random forest classifier](https://user-images.githubusercontent.com/94384079/190901426-225268a8-82bd-4124-9563-2f6912b79a57.PNG)

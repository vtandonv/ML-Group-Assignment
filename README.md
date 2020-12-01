# ML-Group-Assignment (Team of 3 students)
Training a classifier to predict whether a Windows machine can detect a Malware or not

Steps for Model Building:

1. DATA VISUALIZATION:

The dataset consists of numerical and object (categorical)
type of features. The numerical data is of type either int64
or float64. There seem to be a high amount of missing
values amongst the features of the dataset (upto 99% missing
values).There is a high amount of correlation (0.6 and greater)
amongst the numerical features. The object data types seem
to have enormously large number of categories. Now on
visualizing the training label it is clear that the dataset is highly
unbalanced.

2. DATA PREPROCESSING

A. Handling Missing Data
We are removing the features having more than 40% of
missing data since imputing such columns will have undefined
behavior on the target variable.

B. Feature Selection
For numeric data we are removing highly correlated
columns i,e having Pearson correlation value greater than 0.6
so as to avoid multidimentionality in the dataset.
For categorical data we are removing features having large
number of categories since as the number of categories in-
creases, the complexity of the model increases which will
unnecessarily lead to large amount of time in predicting the
results which may not be accurate.

C. Encoding
Most of the categorical data is of string data type. So we
used Label Encoder to to convert the same into numerical
ones so that these columns can be mathematically trained by
the model.

D. Imputation
To handle missing data amongst the numeric features we
employ mean strategy of imputation. For categorical features
Label Encoder automatically assigns a numeric category to
missing (NaN) values.

E. Oversampling
Since our target variable is highly unbalanced so we employ
SMOTE oversampling technique to equate the number of
binary classes.

3. TRAINING THE MODEL


After feature engineering, our number of useful features
reduced to 45 We trained our data on the following algorithms:
• Logistic Regression
• RandomForest
• XGBoost
• lightGBM

4.  CONCLUSION


With the roc auc scores score of 0.65769, XGBoost model
(without SMOTE) best predicted whether the malware was
detected by the system or not.

# Regression with Regularization and Cross Validation. Predicting prices of diamonds.

## Objective:
The objective of this project is to find the best regression model that can predict the price of diamons given the features of the data. The regression models that are going to be tested are: regression, ridge regression, lasso regression, elastic net. Moreover, to find the best hyperparameters ( degree of the polynomial regression and the hyperparameters for the regularizations) we will be doing cross-validation.

## About the data:
This dataset is related to diamonds, containing information on various attributes of diamonds. Here's a breakdown of the columns:
1. carat: The weight of the diamond, measured in carats (a unit of mass used for gemstones).
2. cut: Describes the quality of the cut of the diamond. This is likely a categorical variable with different levels such as 'Fair', 'Good', 'Very Good', 'Premium', and 'Ideal'.
3. color: Represents the color grade of the diamond. This could be a categorical variable indicating the color, with levels like 'D' (colorless), 'E', 'F', 'G', 'H', 'I', 'J' (near colorless), etc.
4. clarity: Indicates the clarity of the diamond, referring to the presence of internal flaws or inclusions. This is also likely a categorical variable with levels such as 'IF' (internally flawless), 'VVS1', 'VVS2' (very, very slightly included), 'VS1', 'VS2' (very slightly included), 'SI1', 'SI2' (slightly included), and 'I1', 'I2', 'I3' (included).
5. depth: Represents the depth percentage of the diamond, calculated as the height of the diamond divided by its average diameter.
6. table: Refers to the width of the diamond's table expressed as a percentage of the average diameter.
7. price: The price of the diamond in USD.
8. x: Length of the diamond in mm.
9. y: Width of the diamond in mm.
10. z: Depth of the diamond in mm.

The dataset consists of 53,940 entries with no missing values across these 10 columns. It seems well-prepared for analysis, with various numerical and categorical variables providing a comprehensive view of diamond attributes. 

The dataset can be found at kaggle following the link below:

https://www.kaggle.com/datasets/rohit265/diamonds-dataset/data


## Conclusion:
We used a dataset containing different features of diamons to predict their price. To this end, we trained different regression models: Polynomial regression, Ridge Regression, Lasso Regression, Elastic Net. To tuned the hyperparameters of the model we performed 5-fold cross validation. 

Our results yield as the best model an elastic net regression, fitting a polynomial of degree=2, with hypeparameters $\alpha = 0.1$ and $l1_{ratio} = 0.25$. 

One of the main difficulties found in this work was the lack of RAM memory, the computations were performed in a machine with 16gb of ram memory. Taking into account that the dataset consists of 53,940 entries across 10 columns, runing the computations in parallel require to allocate enough memory (specially when working with polynomial features). To deal with this issue we have taken a small random sample of the data to be able to train the models with the limited amount of ram memory available, then we tested the model with a test set and with the whole dataset. The model considered as the best, mentioned the previous paragraph, seem to perfom well in the whole data yielding a r2_score = 0.94, when tested with the whole data, and yielding the minimum mean_squared_error among the models tested.

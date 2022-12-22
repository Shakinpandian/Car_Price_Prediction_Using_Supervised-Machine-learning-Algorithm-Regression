# Car Price Prediction by Supervised Machine Learning - Regression

<p align="center">
     <img width="400" height="200" src="https://user-images.githubusercontent.com/119164734/208312859-9e236d65-8ac8-4f88-8d32-7e0a61ef6336.jpg">
</p>

## Table of Contents

### 1.Problem Statement

### 2.Installing and Importing Packages
  
### 3.Loading Data

### 4.Data Acquistititon and Description

### 5.Data Wrangling

### 6.Exploratory Data Analysis

### 7.Data Postprocessing

### 8.Modelling

### 9.Test Set

### 10.Conclusion

## 1.PROBLEM STATEMENT

A Chinese automobile company Geely Auto aspires to enter the US market by setting up their manufacturing unit there and producing cars locally to give competition to their US and European counterparts.

They have contracted an automobile consulting company to understand the factors on which the pricing of cars depends. Specifically, they want to understand the factors affecting the pricing of cars in the American market, since those may be very different from the Chinese market. The company wants to know:

- Which variables are significant in predicting the price of a car
- How well those variables describe the price of a car

Based on various market surveys, the consulting firm has gathered a large dataset of different types of cars across the Americal market.

## 2.Installing and Importing Packages
The following libaries and tools are used in the project.
<p align="center">
  <img width="400" height="200" src="https://user-images.githubusercontent.com/119164734/208314443-2ef2756b-470c-4619-b7a4-1a48bf3c6cd3.png">
</p>

- **Pandas**: Importing for panel data analysis                     

- **Numpy**: For numerical python operations

- **Matplotlib (Pyplot)**: A popular plotting library used along with pandas

- **Seaborn**: A library, built on matplotlib, to create beautiful plots

- **Scikit Learn**: To perform all tasks realted to Machine Learning

# 3.Loading Data

- The dataset has been collected from the **Kaggle.com** and the dataset in **CSV** format.
- To load the data **pd.read_csv("data//path")**.
- From the data **205 rows** and **26 features** are gained.

# 4.Data Acquistititon and Description  
                                                                                  
| Column Name | Description |                     
|---|---|
|Car_ID|Unique ID for each cars|
|Wheelbase|Distance between the centre of the front wheelsand the centre of the rear wheels|
|Carlength|Length of the car|
|Carwidth|Wigth of the car|
|Carheight|Height of the car|
|Curbweight|Weight of the Car, including full petrol tank|                         
|Enginesize|Size of the Engine|
|Boreratio|The ratio of bore to stroke|
|Stroke|Type of stroke|
|Compressionratio|The ratio between the volume of the cylinder and combustion chamber |
|Horsepower| The metric used to indicate the power produced by a car's engine |
|Peak Rpm|Maximum torque will occur at different rpms for every engine|
|City Mpg|The score a car will get on average in city conditions|
|Highway Mpg|The score a car will get on average in city conditions|
|Price|Price of the car|

- Total 18 Numerical datatype and 8 object datatype are recorded.
- The average  of the Price is found to be **$13276.7**.
- The maximum and minimum value of the Peak Rpm are **6650** and **4150**.

# Data Wrangling

In this section, we cleaned out our data based on the information retrieved from the previous observations.

Hence, we performed the following subtasks.

- Checking for missing values and manipulating them.

- Checking the datatype.

- Checking the Spelling Correction.

# 6.Exploratory Data Analysis

<p align="center">
  <img width="400" height="200" src="https://user-images.githubusercontent.com/119164734/208973853-2ff76988-ab78-4ae1-a465-8d2e9e1b48e1.png">
</p>

## Observation:
- It show the usage of gas is higher than the fuel in Americian market.
- Highest number of cylinder has been used was four and four door cars are favoured.
- Engine type of ohc has high demand and huge sales in market.
- Car body of sedan has the most used product in the market.
- Distribution shows that the 85% of price lies between 5000 and 20000 and price distriibution is Right-Skew.

# 7. Data Postprocessing

## Encoding Categorical Variable
- Encoding is a technique of converting categorical variables into numerical values so that it could be easily fitted to a machine learning model.
I have used the Label / Ordinal encoding.

**from sklearn.preprocessing import LabelEncoder**

**Label=LabelEncoder()**

**data_1["Fuel Type"]=Label.fit_transform(data_1["Fuel Type"])**

# Separating train and test data:
- The train-test split is used to estimate the performance of machine learning algorithms that are applicable for prediction-based Algorithms/Applications. This method is a fast and easy procedure to perform such that we can compare our own machine learning model results to machine results.

**from sklearn.model_selection import train_test_split**

**X_train,X_test,Y_train,Y_test=train_test_split(X,Y,test_size=0.3,random_state=45)**

<p align="center">
  <img width="400" height="200" src="https://user-images.githubusercontent.com/119164734/208979910-33a3af21-734b-4ef9-8cc3-b4c51efed7af.png">
</p>

- The dataset has been separated into 70% train data and 30% test data.

# Feature Scaling:
- Feature Scaling is a technique to standardize the independent features present in the data in a fixed range. So the X_train and X_test data should standardize for easy preformance.In standardizing, the mean and range should br 0 to 1.

**from sklearn.preprocessing import StandardScaler**

**Scaler=StandardScaler()**

**X_train_Scaler=Scaler.fit_transform(X_train)**

**X_test_Scaler=Scaler.transform(X_test)**


# 8.Modeling
## Defining baseline model:
A baseline model is essentially a simple model that acts as a reference in a machine learning project. Its main function is to contextualize the results of trained models. Baseline models usually lack complexity and may have little predictive power.

Number of Machine algorithm has been used for baseline model to choose the **Low overfitting**

### 1) KNeighbors Regression

<p align="center">
     <img width="400" height="200" src="https://user-images.githubusercontent.com/119164734/208985398-19f15038-7c46-4ea1-9e91-8780d71c82f2.png">
</p>

- KNN algorithm can be used for both classification and regression problems. 
- The KNN algorithm uses ‘feature similarity’ to predict the values of any new data points.
- If K=3, it will select three values near to them.
- The average of these data points is the final prediction for the new point. Here, we have weight of new data (k=3) = (77+72+60)/3 = 69.66 kg.
- **Euclidean Distance**: Euclidean distance is calculated as the square root of the sum of the squared differences between a new point (x) and an existing point (y).

<p align="center">
     <img width="200" height="100" src="https://user-images.githubusercontent.com/119164734/208984654-060e44fb-2f7c-4ae3-a7f7-00c5640cd7f5.png">
</p>

- This function calculation is used to find out the least distance from the new data.

### 2) RandomForest Regression

<p align="center">
     <img width="400" height="200" src="https://user-images.githubusercontent.com/119164734/209158651-a12d3755-ba8f-460b-b947-cb3e93f1b492.png">
</p>


- A random forest is a meta estimator that fits a number of **classifying decision trees on various sub-samples of the dataset** and uses averaging to improve the predictive accuracy and **control over-fitting**.
- The sub-sample size is controlled with the max_samples parameter if **bootstrap=True (default)**, otherwise the whole dataset is used to build each tree.
-  It can be used for both Classification and Regression problems in ML. It is based on the concept of **Ensemble learning**.

### 3) Bagging Regression

<p align="center">
     <img width="400" height="200" src="https://user-images.githubusercontent.com/119164734/209166273-54d764ee-6e01-4708-b440-5a85cab779e5.png">
</p>


- A Bagging regressor is an ensemble meta-estimator that fits base regressors each on **random subsets of the original dataset** and then **aggregate their individual predictions** (either by voting or by averaging) to form a final prediction.
- Bagging regression is similar to Randomforest regression,but the bootstrap will split into **different model or dataset**

#### 4) Decision Tree Regression

<p align="center">
     <img width="400" height="200" src="https://user-images.githubusercontent.com/119164734/209168623-b363f4db-402f-4bb4-a094-21fb581e3e9f.png">
</p>


- Decision tree regression observes features of an object and trains a model in the structure of a tree to predict data in the future to produce meaningful continuous output. 
- It breaks down a dataset into smaller and smaller subsets while at the same time an associated decision tree is incrementally developed. 
- The final result is a tree with **decision nodes** and **leaf nodes**. 
- The topmost decision node in a tree ,which corresponds to the best predictor called root node. Decision trees can handle **both categorical and numerical data**.

### 4) Linear Regression

<p align="center">
     <img width="400" height="200" src="https://user-images.githubusercontent.com/119164734/209169348-b1641f89-1ac6-4aa0-817b-716d1dbfad69.png">
</p>

- Linear regression analysis is used to predict the value of a variable based on the value of another variable.
-  The variable you want to predict is called the **dependent variable**. The variable you are using to predict the other variable's value is called the **independent variable**.
- This form of analysis estimates the coefficients of the linear equation, involving one or more independent variables that best predict the value of the dependent variable.
- Linear regression fits a straight line or surface that minimizes the discrepancies between predicted and actual output values. 
- There are simple linear regression calculators that use a **“least squares” method to discover the best-fit line for a set of paired data**. You then estimate the value of **X (dependent variable) from Y (independent variable)**.

### **Step 1** : Above models are imported and ready for test the train data.
### **Step 2** : In each model,**X_train and Y_tain has been fitted for prediction**.
### **Step 3** : Predict the **train data(X_train)** using above model.
### **Step 4** : R2_score has been used to find out the accuracy of the train and test data.

- **R2_score**: **The proportion of the variance in the dependent variable that is predictable from the independent variable(s)**.
- **(Total variance explained by model) / total variance)** ,So if it is 100%, the two variables are perfectly correlated.

## Observation:-
**RandomForest Regression** gives the best **r2 score** and **Low Basis** and **low variance (low overfitting)** among the models, so the RandomForest Regression will be used for **Hyperparameter tunning**.

# Hyperparameter tunning:-

Hyperparameters are parameters whose values control the learning process and determine the values of model parameters that a learning algorithm ends up learning and also used **to find out the best model**.

- We will be using Random Search in order to find the best values.

- We will consider RandomForest Regression as they have given best results.

## RandomizedSearchCV

It is meant to find the best parameters to improve a given model.A key difference is that **it does not test all parameters. Instead, the search is done at random**.

### Random forest parameters

**n_estimators** : This parameter denotes the maximum number of trees in an ensemble/forest.

**max_features** : This represents the maximum number of features taken into consideration when splitting a node.

**max_depth** : max_depth represents the maximum number of levels that are allowed in each decision tree.

**min_samples_split** : To cause a node to split, a minimum number of samples are required in a node. This minimum number of data points is what is represented by to as min_samples_split.

**min_samples_leaf**: The minimum count of data points that can be stored in a leaf node.

**cv=5**:we train a model 5 times using cross-validation.

## Observation:-

- The best model has created by Hyperparameter tunning as a result, the best_model has fitted with X_train and Y_train.

- It occur the best **Hyperparameters: {'n_estimators': 33, 'min_samples_split': 5, 'min_samples_leaf': 1, 
               'max_features': 'auto', 'max_depth': 4, 'bootstrap': True} **.
               
- Train Score: **0.9146482211854652**         [Train_score], random_tuning_model.best_score_

- Validation Score: **0.9691344968856467**  [Validation Score]:", r2_score(Y_train,Y_pre)

# 9) Test data-

- Best_model= **model.best_estimator_(which give a higher score and accuracy)**.

- This model is fitted with X_train and Y_train and prediction is obtained to **X_test**.

- Accuracy of the test data is **0.8899** measure by **R2_score**.

### Submission of Unseen data:

<p align="center">
     <img width="500" height="250" src="https://user-images.githubusercontent.com/119164734/209204378-66d041e2-46b7-4851-9be6-dc16f99e82a7.png">
</p>
                                      
 # Conclusion:
 
- In this case study the given data was analysed and on top of that a regression model was built.

- It can be found that Enginesize,stroke and curbweight are making the price high in the Amercian Market.

- The model chosen for this case study was a RandomsForest Regression as it was retruning **the least overfitting** and best r2 score on unseen data.

- The r2 score genarated in unseen data was 0.90 which means that the modedl performs really good and is generalizing well on unseen data.













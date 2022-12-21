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
<p align="right">
        <img width="200" height="100" src="https://user-images.githubusercontent.com/119164734/208954684-6dc35945-f2e2-4fe9-  8638-c255b3ad9dd1.jpg")>
</p>
                                                                                  
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













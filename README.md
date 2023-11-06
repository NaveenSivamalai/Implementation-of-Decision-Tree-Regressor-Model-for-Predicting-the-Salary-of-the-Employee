# Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the required libraries .
2. Read the data frame using pandas.
3. Get the information regarding the null values present in the dataframe.
4. Apply label encoder to the non-numerical column inoreder to convert into numerical values.
5. Determine training and test data set.
6. Apply decision tree regression on to the dataframe.
7. Get the values of Mean square error, r2 and data prediction.
   

## Program:
```
/*
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: NAVEEN S
RegisterNumber: 212222110030 
*/
```

```
import pandas as pd
data=pd.read_csv("/content/Salary.csv")

data.head()

data.info()

data.isnull().sum()

from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data["Position"]=le.fit_transform(data["Position"])
data.head()

x=data[["Position","Level"]]
y=data["Salary"]

from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=2)

from sklearn.tree import DecisionTreeRegressor
dt=DecisionTreeRegressor()
dt.fit(x_train,y_train)
y_pred=dt.predict(x_test)

from sklearn import metrics
mse=metrics.mean_squared_error(y_test,y_pred)
mse

r2=metrics.r2_score(y_test,y_pred)
r2

dt.predict([[5,6]])
```
## Output:

## data.head()
![276262885-d6b4cb40-1795-4b64-8683-7acc5b701051](https://github.com/NaveenSivamalai/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/123792574/952dc651-b8ae-4d6f-a469-9f9172f0e871)


## data.info()
![276262851-d410937e-837d-4ce0-ae0d-d18246cbb07b](https://github.com/NaveenSivamalai/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/123792574/380ff3ef-1f30-40c8-8b07-1b7f71529c96)


## isnull() & sum() function
![276262814-1ac338d8-7d40-403a-90e4-48a7d6fc03cb](https://github.com/NaveenSivamalai/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/123792574/50a5ac88-21a4-4985-b46e-d5da0baaea1a)


## data.head() for position
![276262767-8b81fa42-a87e-49a8-8129-884c0e6de355](https://github.com/NaveenSivamalai/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/123792574/20bf46bb-ae49-4ef1-88f9-1d89a0f8f51a)


## MSE value
![276262714-7afc264d-6718-4b8e-a234-aea823b90e0e](https://github.com/NaveenSivamalai/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/123792574/e5314a69-d2eb-4ed8-a7e7-e9c551a97f43)


## R2 value
![276262661-f0e9b89b-40d0-442c-bead-4ecbfe53aa62](https://github.com/NaveenSivamalai/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/123792574/09ba7061-61ac-4e31-b199-801a9bd0b854)


## Prediction value

![276262449-49a799ab-6bf5-45d7-8024-83e39b739903](https://github.com/NaveenSivamalai/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/123792574/36ea8a25-c3eb-473f-96d9-3a622cafa567)


## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.

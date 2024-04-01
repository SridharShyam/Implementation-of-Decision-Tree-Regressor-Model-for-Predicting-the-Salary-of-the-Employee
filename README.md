# Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
### Step-1:
Import the required libraries .
### Step-2:
Read the data frame using pandas.
### Step-3:
Get the information regarding the null values present in the dataframe.
### Step-4:
Apply label encoder to the non-numerical column inoreder to convert into numerical values.
### Step-5:
Determine training and test data set.
### Step-6:
Apply decision tree regression on to the dataframe.
### Step-7:
Get the values of Mean square error, r2 and data prediction.

## Program:
```
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: SHYAM S
RegisterNumber: 212223240156
import pandas as pd
data=pd.read_csv("Salary.csv")
print(data.head())
print(data.info())
print(data.isnull().sum())

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
print("MSE:",mse)

r2=metrics.r2_score(y_test,y_pred)
print("R2:",r2)

dt.predict([[5,6]])

```

## Output:

![image](https://github.com/SridharShyam/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/144871368/33e4470e-d73a-4d95-a358-73c1e9c13476)

![image](https://github.com/SridharShyam/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/144871368/ff7745be-b5a3-49b5-b50c-d384f938a8ad)

### MSE:

![image](https://github.com/SridharShyam/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/144871368/ef661443-9813-4dc0-a689-9afe234e9fec)

### R2:

![image](https://github.com/SridharShyam/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/144871368/36d69f1e-9086-4a10-ac51-9d4d9abcf6dd)

### Prediction:

![image](https://github.com/SridharShyam/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/144871368/b32372c0-5472-443b-bd3f-b4d2051106de)

## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.

# Implementation-of-Simple-Linear-Regression-Model-for-Predicting-the-Marks-Scored

## AIM:
To write a program to predict the marks scored by a student using the simple linear regression model.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import the standard Libraries 
2.Set variables for assigning dataset values 
3.Import linear regression from sklearn.  
4..Assign the points for representing in the graph. 5.Predict the regression for marks by using the representation of the graph. 6.Compare the graphs and hence we obtained the linear regression for the given datas. 

## Program:
```  
/*
Program to implement the simple linear regression model for predicting the marks scored.
Developed by: Santharamanath
RegisterNumber:  212223220097
*/
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from sklearn.metrics import mean_absolute_error,mean_squared_error
df=pd.read_csv('student_scores.csv')
df.head()
df.tail()
x = df.iloc[:,:-1].values
x
y = df.iloc[:,1].values
y
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=1/3,random_state=0)
from sklearn.linear_model import LinearRegression
regressor = LinearRegression()
regressor.fit(x_train,y_train)
y_pred = regressor.predict(x_test)
y_pred
y_test
#Graph plot for training data
plt.scatter(x_train,y_train,color='black')
plt.plot(x_train,regressor.predict(x_train),color='purple')
plt.title("Hours vs Scores(Training set)")
plt.xlabel("Hours")
plt.ylabel("Scores")
plt.show()
#Graph plot for test data
plt.scatter(x_test,y_test,color='red')
plt.plot(x_train,regressor.predict(x_train),color='blue')
plt.title("Hours vs Scores(Testing set)")
plt.xlabel("Hours")
plt.ylabel("Scores")
plt.show()
mse=mean_absolute_error(y_test,y_pred)
print('MSE = ',mse)
mae=mean_absolute_error(y_test,y_pred)
print('MAE = ',mae)
rmse=np.sqrt(mse)
print("RMSE= ",rmse)
```

## Output:
![229979169-ad4db5b6-e238-4d80-ae5b-405638820d35](https://github.com/Santharamanath/Implementation-of-Simple-Linear-Regression-Model-for-Predicting-the-Marks-Scored/assets/149035289/9ccd4331-156c-4d54-b4b0-3f36cc82f587)
![229979225-ba90853c-7fe0-4fb2-8454-a6a0b921bdc1](https://github.com/Santharamanath/Implementation-of-Simple-Linear-Regression-Model-for-Predicting-the-Marks-Scored/assets/149035289/44b6d505-28c0-4994-b4a1-a01e734d0e13)



## Result:
Thus the program to implement the simple linear regression model for predicting the marks scored is written and verified using python programming.

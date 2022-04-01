# Implementation-of-Linear-Regression-Using-Gradient-Descent

## AIM:
To write a program to implement the linear regression using gradient descent.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1.Import the required packages.
2.Declare the default values.
3.Predict the y value.
4.Calculate the meansquare error.
5.Plot the graph using the matplotlib.
6.End the program 

## Program:
```
/*
Program to implement the linear regression using gradient descent.
Developed by: G Venkata Pavan Kumar
RegisterNumber: 212221240013
*/
~~~python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("student_scores.csv")
data.head()
data.isnull().sum()
x = data.Hours
x.head()
y = data.Scores
y.head()
n = len(x)
m = 0
c = 0
L = 0.001
loss = []
for i in range(10000):
    ypred = m*x + c
    MSE = (1/n) * sum((ypred - y)*2)
    dm = (2/n) * sum(x*(ypred-y))
    dc = (2/n) * sum(ypred-y)
    c = c-L*dc
    m = m-L*dm
    loss.append(MSE)
print(m,c)
y_pred = m*x + c
plt.scatter(x,y,color='Blue')
plt.plot(x,y_pred,color='green')
plt.xlabel("Study hours")
plt.ylabel("Scores")
plt.title("Study hours vs. Scores")
plt.plot(loss)
plt.xlabel("Iterations")
plt.ylabel("loss")
plt.show()
~~~

## Output:
![Intro](https://user-images.githubusercontent.com/94827772/161199791-27bb0440-885b-4274-9a81-46f550482724.png)


## Result:
Thus the program to implement the linear regression using gradient descent is written and verified using python programming.

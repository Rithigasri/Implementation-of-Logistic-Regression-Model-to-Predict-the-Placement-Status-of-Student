# EXPERIMENT 04: IMPLEMENTATION OF LOGISTIC REGRESSION MODEL TO PREDICT THE PLACEMENT STATUS OF STUDENT

## AIM:
To write a program to implement the the Logistic Regression Model to Predict the Placement Status of Student.

## SOFTWARE REQUIRED:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## ALGORITHM
1.Import the standard libraries.   
2.Upload the dataset and check for any null or duplicated values using .isnull() and .duplicated() function respectively.  
3.Import LabelEncoder and encode the dataset.  
4.Import LogisticRegression from sklearn and apply the model on the dataset.  
5.Predict the values of array.  
6.Calculate the accuracy, confusion and classification report by importing the required modules from sklearn.  
7.Apply new unknown values.  

## PROGRAM:
```
Program to implement the the Logistic Regression Model to Predict the Placement Status of Student.
Developed by: RITHIGA SRI.B  
Register Number: 212221230083    
```
```
import pandas as pd
data=pd.read_csv("Placement_Data.csv")
data.head()

data1=data.copy()
data1=data1.drop(["sl_no","salary"],axis=1)#Removes the specified row or column
data1.head()

data1.isnull().sum()

data1.duplicated().sum()

from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data1["gender"]=le.fit_transform(data1["gender"])
data1["ssc_b"]=le.fit_transform(data1["ssc_b"])
data1["hsc_b"]=le.fit_transform(data1["hsc_b"])
data1["hsc_s"]=le.fit_transform(data1["hsc_s"])
data1["degree_t"]=le.fit_transform(data1["degree_t"])
data1["workex"]=le.fit_transform(data1["workex"])
data1["specialisation"]=le.fit_transform(data1["specialisation"])
data1["status"]=le.fit_transform(data1["status"])
data1

x=data1.iloc[:,:-1]
x

y=data1["status"]
y

from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=0)

from sklearn.linear_model import LogisticRegression
lr=LogisticRegression(solver="liblinear")# A library for large linear classification
lr.fit(x_train,y_train)
y_pred=lr.predict(x_test)
y_pred

from sklearn.metrics import accuracy_score
accuracy=accuracy_score(y_test,y_pred)# Accuracy Score = (TP+TN)/
#accuracy_score(y_true,y_prednormalize=False)

from sklearn.metrics import confusion_matrix
confusion = confusion_matrix(y_test,y_pred)
confusion

from sklearn.metrics import classification_report
classification_report1=classification_report(y_test,y_pred)
print(classification_report1)

lr.predict([[1,80,1,90,1,1,90,1,0,85,1,85]])

```

## OUTPUT:
### 1.PLACEMENT DATA:  
![image](https://user-images.githubusercontent.com/93427256/233653648-80c4ed05-ad1d-458d-b1d5-e57572014af7.png)

### 2.SALARY DATA:
![image](https://user-images.githubusercontent.com/93427256/233653765-a9c25cc7-db43-4584-bfd2-617327e1552a.png)

### 3.CHECKING THE NULL() FUNCTION:
![image](https://user-images.githubusercontent.com/93427256/233653882-25559b60-9426-4599-84be-48fec4a73f2c.png)

### 4.DATA DUPLICATE:
![image](https://user-images.githubusercontent.com/93427256/233654120-5b9091a7-74d3-4b8f-a438-1d7b7685caa8.png)

### 5.PRINT DATA:
![image](https://user-images.githubusercontent.com/93427256/233654445-ec2bbc92-ccf6-4e0d-ae98-0bb70da10992.png)

### 6.DATA STATUS:
![image](https://user-images.githubusercontent.com/93427256/233654553-f8b5a8a7-189e-427b-9a35-3894826c3055.png)
![image](https://user-images.githubusercontent.com/93427256/233654825-0243b7bd-43e4-48f6-9397-a9706b2fb6bf.png)

### 7.Y_PREDICTION ARRAY:
![image](https://user-images.githubusercontent.com/93427256/233654895-81f81bbb-d4c4-4cce-b1a9-dca67fd6ddda.png)

### 8.ACCURACY VALUE:
![image](https://user-images.githubusercontent.com/93427256/233655080-f1dd7c49-95db-445e-8f02-fe14073a8038.png)

### 9.CONFUSION ARRAY:
![image](https://user-images.githubusercontent.com/93427256/233655218-2d1edc13-603e-4812-a4d8-b2ea478471b6.png)

### 10.CLASSIFICATION REPORT:
![image](https://user-images.githubusercontent.com/93427256/233655316-0c61b48f-b6d9-4acf-8fd0-67141ebb0f3f.png)

### PREDICTION OF LR:
![image](https://user-images.githubusercontent.com/93427256/233655389-d3840945-1b44-4c9b-b860-d0119bb91955.png)

## RESULT:
Thus the program to implement the the Logistic Regression Model to Predict the Placement Status of Student is written and verified using python programming.

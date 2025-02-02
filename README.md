# Ex.No.1---Data-Preprocessing
## AIM:
To perform Data preprocessing in a data set downloaded from Kaggle
## REQUIPMENTS REQUIRED:
Hardware – PCs
Anaconda – Python 3.7 Installation / Google Colab /Jupiter Notebook
## RELATED THEORETICAL CONCEPT:
Kaggle :
Kaggle, a subsidiary of Google LLC, is an online community of data scientists and machine learning practitioners. Kaggle allows users to find and publish data sets, explore and build models in a web-based data-science environment, work with other data scientists and machine learning engineers, and enter competitions to solve data science challenges.

Data Preprocessing:

Pre-processing refers to the transformations applied to our data before feeding it to the algorithm. Data Preprocessing is a technique that is used to convert the raw data into a clean data set. In other words, whenever the data is gathered from different sources it is collected in raw format which is not feasible for the analysis.
Data Preprocessing is the process of making data suitable for use while training a machine learning model. The dataset initially provided for training might not be in a ready-to-use state, for e.g. it might not be formatted properly, or may contain missing or null values.Solving all these problems using various methods is called Data Preprocessing, using a properly processed dataset while training will not only make life easier for you but also increase the efficiency and accuracy of your model.

Need of Data Preprocessing :

For achieving better results from the applied model in Machine Learning projects the format of the data has to be in a proper manner. Some specified Machine Learning model needs information in a specified format, for example, Random Forest algorithm does not support null values, therefore to execute random forest algorithm null values have to be managed from the original raw data set.
Another aspect is that the data set should be formatted in such a way that more than one Machine Learning and Deep Learning algorithm are executed in one data set, and best out of them is chosen.
## ALGORITHM:
Importing the libraries

Importing the dataset

Taking care of missing data

Encoding categorical data

Normalizing the data

Splitting the data into test and train
## PROGRAM:
```
import io
from sklearn.preprocessing import StandardScaler
from sklearn.preprocessing import MinMaxScaler
from sklearn.model_selection import train_test_split
from sklearn.preprocessing import LabelEncoder
import pandas as pd
df = pd.read_csv('Churn_Modelling.csv')
df.head()
le=LabelEncoder()
df["CustomerId"]=le.fit_transform(df["CustomerId"])
df["Surname"]=le.fit_transform(df["Surname"])
df["CreditScore"]=le.fit_transform(df["CreditScore"])
df["Geography"]=le.fit_transform(df["Geography"])
df["Gender"]=le.fit_transform(df["Gender"])
df["Balance"]=le.fit_transform(df["Balance"])
df["EstimatedSalary"]=le.fit_transform(df["EstimatedSalary"])
X=df.iloc[:,:-1].values
print(X)
Y=df.iloc[:,-1].values
print(Y)
print(df.isnull().sum())
df.fillna(df.mean().round(1),inplace=True)
print(df.isnull().sum())
y=df.iloc[:,-1].values
print(y)
df.duplicated()
print(df['Exited'].describe())
scaler= MinMaxScaler()
df1=pd.DataFrame(scaler.fit_transform(df))
print(df1)
x_train,x_test,y_train,x_test=train_test_split(X,Y,test_size=0.2)
print(x_train)
print(len(x_train))
print(x_test)
print(len(x_test))
```
## OUTPUT:
![ex 1](https://github.com/Dhanashreemullaithasan/Ex.No.1---Data-Preprocessing/assets/94165415/e298a5f6-9893-4323-88b1-468b389800de)
![EX11](https://github.com/Dhanashreemullaithasan/Ex.No.1---Data-Preprocessing/assets/94165415/368cb934-9ecf-4040-b3f0-1ee78d0c54f0)
![EX12](https://github.com/Dhanashreemullaithasan/Ex.No.1---Data-Preprocessing/assets/94165415/d4017c45-ce3f-4d1f-af11-32e913384c62)
![EX13](https://github.com/Dhanashreemullaithasan/Ex.No.1---Data-Preprocessing/assets/94165415/54a949a8-73bf-4684-a44a-e632b3b104c0)
![EX14](https://github.com/Dhanashreemullaithasan/Ex.No.1---Data-Preprocessing/assets/94165415/b0bab1ef-b621-4b48-9d3d-6b5ef2cbf5b1)
![EX15](https://github.com/Dhanashreemullaithasan/Ex.No.1---Data-Preprocessing/assets/94165415/8fbe5927-3229-44f9-8c11-ee9ca5d1b9c1)
![EX16](https://github.com/Dhanashreemullaithasan/Ex.No.1---Data-Preprocessing/assets/94165415/d7cea8b8-c795-49ec-ab9a-e20ca0c63d26)
## RESULT :
Hence the data preprocessing is done using the above code and data has been splitted into trainning and testing data for getting a better model.

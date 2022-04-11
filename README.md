# Ex-03EDA

## AIM
To perform EDA on the given data set. 

# Explanation
The primary aim with exploratory analysis is to examine the data for distribution, outliers and 
anomalies to direct specific testing of your hypothesis.
 

# ALGORITHM
### STEP 1
Import the required packages(pandas,numpy,seaborn).

### STEP 2
Read the given csv file.

### STEP 3
Convert the file into a dataframe and get information of the data.

### STEP 4
Remove the non numerical data columns using drop() method.
### STEP 5
Replace the null values using (.fillna).

### STEP 6
Returns object containing counts of unique values using (value_counts()).

### STEP 7
Plot the counts in the form of Histogram or Bar Graph.

### STEP 8
Find the pairwise correlation of all columns in the dataframe(.corr()).Save the final data set into the file.



# CODE
```
import pandas as pd
import numpy as np
import seaborn as sns
df=pd.read_csv("titanic_dataset.csv")
df.info()
df.head()
df.isnull().sum()
df.drop("Cabin",axis=1,inplace=True)
df.info()
df.isnull().sum()
df["Age"]=df["Age"].fillna(df["Age"].median())
df.boxplot()
df.isnull().sum()
df["Embarked"]=df["Embarked"].fillna(df["Embarked"].mode()[0])
df["Embarked"].value_counts()
df["Pclass"].value_counts()
df["Survived"].value_counts()
sns.countplot(x="Survived",data=df)
sns.countplot(x="Pclass",data=df)
sns.countplot(x="Sex",data=df)
df.info()

sns.displot(df["Fare"])
sns.countplot(x="Pclass",hue="Survived",data=df)
sns.displot(df[df["Survived"]==0]["Age"])
pd.crosstab(df["Pclass"],df["Survived"])
pd.crosstab(df["Sex"],df["Survived"])
df.corr()
sns.heatmap(df.corr(),annot=True)
```
# OUPUT
![image](https://user-images.githubusercontent.com/94810884/162801271-9a9f8c90-3503-4d6a-a5cb-e3df6f898749.png)

![image](https://user-images.githubusercontent.com/94810884/162801444-f4e581be-5d02-4af2-93b6-3fb68b5633da.png)

![image](https://user-images.githubusercontent.com/94810884/162801513-3d306f9a-68f2-40e6-823d-17419042cd23.png)

![image](https://user-images.githubusercontent.com/94810884/162801623-47847e02-c00f-4bfc-86a0-7bbc299be5a2.png)

![image](https://user-images.githubusercontent.com/94810884/162801717-7a51a28b-1877-4cf5-b6ef-225c863e7208.png)

![image](https://user-images.githubusercontent.com/94810884/162801824-addb556e-340b-4f8c-bdcd-b596c3cd0b68.png)

![image](https://user-images.githubusercontent.com/94810884/162801899-6574aa25-b1a1-432e-b2e0-1339bbd136cf.png)

![image](https://user-images.githubusercontent.com/94810884/162801963-b89023d1-72d0-4e02-ba02-525b9b2db751.png)

### RESULT
Thus the EDA on the given data set is sucessfully done.


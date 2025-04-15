# EXNO2DS

 ### NAME : PREETHI D
 ### REGISTER NUMBER : 212224040250
# AIM:
      To perform Exploratory Data Analysis on the given data set.
      
# EXPLANATION:
  The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
# ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODIND AND OUTPUT

``` python

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

```
``` python

dt=pd.read_csv("/content/titanic_dataset (2).csv")

```
``` python

dt

```
![image](https://github.com/user-attachments/assets/fe347b8b-e399-4bee-818a-94229969ebcb)

``` python

dt.info()

```
![image](https://github.com/user-attachments/assets/d6ce9da2-929b-4b80-9789-6f12c86beae5)

``` python

dt.shape

```
![image](https://github.com/user-attachments/assets/130d97ab-1edd-41d8-890d-dc31e092cdd9)

``` python

dt.set_index("PassengerId",inplace=True)
dt.describe()

```
![image](https://github.com/user-attachments/assets/fcdfaa8f-1b65-4fbd-9895-50a2c5ca6d85)

``` python

dt.nunique()

```

![image](https://github.com/user-attachments/assets/cfee16df-6e3d-4871-9239-5c0bd3b73286)

``` python

dt["Survived"].value_counts()

```
![image](https://github.com/user-attachments/assets/908d4098-c5e5-4155-9172-ec2ad1ddf9a2)

``` python

per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per

```
![image](https://github.com/user-attachments/assets/b8440694-07cf-4af3-beef-fd7b83e7411f)

``` python

sns.countplot(data=dt,x="Survived")

```
![image](https://github.com/user-attachments/assets/3dfbbeae-76a3-4066-a749-6f22041aebfb)

``` python

dt

```
![image](https://github.com/user-attachments/assets/cce767b8-6633-44a3-90d8-0b2222bf8a5c)

``` python

dt.Pclass.unique()

```
![image](https://github.com/user-attachments/assets/7c17f93a-4050-47f3-a4a4-66943be1eeac)

``` python

dt.rename(columns = {'Sex':'Gender'},inplace = True)

```
``` python

sns.catplot(x="Gender",col="Survived",kind="count",data=dt)

```
![image](https://github.com/user-attachments/assets/43ed0bc5-8377-485e-b6b3-341f6726e0ea)

``` python

sns.catplot(x='Survived',hue="Gender",data=dt,kind="count")

```
![image](https://github.com/user-attachments/assets/2b11e8e6-3481-4a9a-80ae-756e1b9364bf)


``` python

dt.boxplot(column="Age",by="Survived")

```
![image](https://github.com/user-attachments/assets/57397b61-c989-4628-b51f-b30dfdd44935)

``` python

sns.scatterplot(x=dt["Age"],y=dt["Fare"])

```
![image](https://github.com/user-attachments/assets/28271ece-f6c1-49a1-a58b-d7cfef115806)

``` python

sns.jointplot(x="Age",y="Fare",data=dt)

```
![image](https://github.com/user-attachments/assets/e037e883-2c38-48a8-bd32-4eba5dc5748f)

``` python

fig,ax1 = plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=dt)

```
![image](https://github.com/user-attachments/assets/7ea27e2b-e518-4d8d-bba4-7101c08aa23e)

``` python

sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count")

```
![image](https://github.com/user-attachments/assets/a54b2fda-11aa-4c75-bb58-9d78e2eb3414)

``` python

import seaborn as sns
corr=df.corr()
sns.heatmap(corr,annot=True)

```
``` python

sns.pairplot(dt)

```
![image](https://github.com/user-attachments/assets/715ea8e6-5b13-4772-ab80-be5703e69b41)












# RESULT
       Thus the process of Exploratory Data Analysis has been carried out successfully 

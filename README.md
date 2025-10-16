# EXNO2DS
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

## CODING AND OUTPUT
```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```
```python
dt=pd.read_csv("/content/titanic_dataset.csv")
```
```python
dt
```
<img width="1550" height="648" alt="image" src="https://github.com/user-attachments/assets/921ac25a-1f8a-41f0-941a-63757c9a53d6" />

```python
dt.info()
```
<img width="1152" height="648" alt="image" src="https://github.com/user-attachments/assets/e9908447-be53-4219-bd4d-824715eb418d" />

```python
dt.set_index("PassengerId",inplace=True)
```
```python
dt.describe()
```
<img width="1152" height="648" alt="image" src="https://github.com/user-attachments/assets/754880cf-6527-4e2b-9ac0-63169c21d423" />

```python
dt.shape
```
<img width="1152" height="648" alt="image" src="https://github.com/user-attachments/assets/8e57f4e4-8ab9-4a0f-98d0-8d4eec670a04" />

```python
dt.nunique()
```
<img width="1152" height="648" alt="image" src="https://github.com/user-attachments/assets/03a3d736-2d9c-4b58-88dc-4908146cc4f5" />

```python
dt["Survived"].value_counts()
```
<img width="1152" height="648" alt="image" src="https://github.com/user-attachments/assets/67615fb5-f8b2-43c1-8a28-8befeffa4e11" />

```python
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
```
<img width="1152" height="648" alt="image" src="https://github.com/user-attachments/assets/d9192124-ee59-4685-9d68-f9d39b0608dd" />

```python
sns.countplot(data=dt,x="Survived")
```
<img width="1152" height="673" alt="image" src="https://github.com/user-attachments/assets/8d8bba52-f96a-4bd3-81fe-2903b9a3391d" />

```python
dt.Pclass.unique()
```
<img width="1152" height="648" alt="image" src="https://github.com/user-attachments/assets/98f03408-2970-4d69-a6c7-b7f26e201233" />

```python
dt.rename(columns={'Sex':'Gender'},inplace=True)
dt
```
<img width="1670" height="672" alt="image" src="https://github.com/user-attachments/assets/22b4eb0f-0190-478d-9919-3328a7b04f6f" />

```python
sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5,aspect=.7)
```
<img width="1152" height="776" alt="image" src="https://github.com/user-attachments/assets/9bc5c6f4-2de9-44a1-acee-e1520e08ea32" />

```python
sns.catplot(x="Survived",hue="Gender",data=dt,kind="count")
```
<img width="1152" height="772" alt="image" src="https://github.com/user-attachments/assets/09004996-a796-4b72-a2bd-3ef54aa6988e" />

```python
sns.catplot(x="Survived",hue="Gender",data=dt,kind="count")
```
<img width="1152" height="742" alt="image" src="https://github.com/user-attachments/assets/da26634c-641e-4593-b89b-d724b93e3183" />

```python
sns.scatterplot(x=dt["Age"],y=dt['Fare'])
```
<img width="1152" height="692" alt="image" src="https://github.com/user-attachments/assets/40b2e841-2aa7-4894-8f3f-f14cb3135c95" />

```python
sns.jointplot(x="Age",y="Fare",data=dt)
```
<img width="1152" height="926" alt="image" src="https://github.com/user-attachments/assets/75e7119a-f6be-43b9-a5bb-1f678347fbd4" />

```python
fig,ax1=plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=dt)
```
<img width="1152" height="682" alt="image" src="https://github.com/user-attachments/assets/98974555-c460-4b9d-8712-c9698beb58b3" />

```python
sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count")
```
<img width="1608" height="780" alt="image" src="https://github.com/user-attachments/assets/479403a5-7b7b-40ad-aa00-8ac424738ee8" />

```python
corr=dt.select_dtypes(include=['number']).corr()
sns.heatmap(corr,annot=True)
```
<img width="1152" height="674" alt="image" src="https://github.com/user-attachments/assets/12635ffa-f2f5-4e25-bb16-5fcd460d6c58" />

```python
sns.pairplot(dt)
```
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/859e13b0-e951-4ef7-8cac-c173ce375953" />





# RESULT
    To perform Exploratory Data Analysis on the given data is successfully completed.

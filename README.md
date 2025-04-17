# Exno:1
Data Cleaning Process

# AIM
To read the given data and perform data cleaning and save the cleaned data to a file.

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

# Algorithm
STEP 1: Read the given Data

STEP 2: Get the information about the data

STEP 3: Remove the null values from the data

STEP 4: Save the Clean data to the file

STEP 5: Remove outliers using IQR

STEP 6: Use zscore of to remove outliers

# Coding and Output
```
REG NO: 212224110045
NAME: A PRANEYA
```

```
import pandas as pd
df=pd.read_csv("/content/SAMPLEIDS.csv")
df
```
![Screenshot 2025-03-19 141050](https://github.com/user-attachments/assets/220e1b94-1a46-4ff6-b4dc-f2541de18a4b)

```
df.shape
```
![Screenshot 2025-03-19 141057](https://github.com/user-attachments/assets/d6aa1bb4-3e17-41b8-b80d-9ba29c581f6e)

```
df.describe()
```
![Screenshot 2025-03-19 141105](https://github.com/user-attachments/assets/bf578e29-6ac5-4788-8093-d9568b779303)

```
df.info()
```
![Screenshot 2025-03-19 141111](https://github.com/user-attachments/assets/ed1e7eb3-122f-4fd0-96fe-9972bfb69aae)

```
df.head(10)
```
![Screenshot 2025-03-19 141118](https://github.com/user-attachments/assets/5646c457-f762-4338-aa2b-6488a2c9e9d2)

```
df.tail(10)
```
![Screenshot 2025-03-19 141125](https://github.com/user-attachments/assets/b83b0237-5e79-4bdb-8ba0-858266261795)

```
df.isna().sum()
```
![Screenshot 2025-03-19 141132](https://github.com/user-attachments/assets/f7f87bb6-f9bf-4be3-a300-362768003c70)

```
df.dropna(how='any').shape
```
![Screenshot 2025-03-19 141138](https://github.com/user-attachments/assets/ee790cad-f579-4e71-867a-8616fcc6ab2e)

```
df.shape
```
![Screenshot 2025-03-19 141142](https://github.com/user-attachments/assets/ed878d1c-0d82-4cb4-8b1c-6419ac51cf9b)

```
x=df.dropna(how='any')
x
```
![Screenshot 2025-03-19 141152](https://github.com/user-attachments/assets/64ea2a2a-9551-4b2b-8ebb-19e889a3c664)

```
mn=df.TOTAL.mean()
mn
```
![Screenshot 2025-03-19 141204](https://github.com/user-attachments/assets/7852f899-7718-4127-9bff-ef5d8c423ccf)

```
df.TOTAL.fillna(mn,inplace=True)
df
```
![Screenshot 2025-03-19 141214](https://github.com/user-attachments/assets/e4abcd17-b028-4314-9089-cb93aa0524c2)

```
df.isnull().sum()
```
![Screenshot 2025-03-19 141221](https://github.com/user-attachments/assets/69478f4f-684d-43a3-b711-7ea2c2aef1fb)

```
df.M1.fillna(method='ffill',inplace=True)
df
```
![Screenshot 2025-03-19 141232](https://github.com/user-attachments/assets/afc27a78-482c-46b5-aa0a-a1530380070d)

```
df.isnull().sum()
```
![Screenshot 2025-03-19 141238](https://github.com/user-attachments/assets/fb0bab59-f5a7-4cdd-a654-8ff6b1ef1d7f)

```
df.M2.fillna(method='ffill',inplace=True)
df
```
![Screenshot 2025-03-19 141246](https://github.com/user-attachments/assets/28cd7461-579d-47ec-b20d-690d01516ca5)

```
df.isnull().sum()
```
![Screenshot 2025-03-19 141253](https://github.com/user-attachments/assets/65938002-4a5a-436d-a122-ab32e1bd2ba4)

```
df.M3.fillna(method='ffill',inplace=True)
df
```
![Screenshot 2025-03-19 141302](https://github.com/user-attachments/assets/3d25e3b2-cafc-4f17-9702-10839c0fde90)

```
df.isna().sum()
```
![Screenshot 2025-03-19 141310](https://github.com/user-attachments/assets/2d5f3e70-8805-46bd-9552-b97e4b8653ad)

```
df.drop_duplicates(inplace=True)
df
```
![Screenshot 2025-03-19 141319](https://github.com/user-attachments/assets/6d7b351c-8ae5-4d6b-896b-5b0d88642cb3)

```
df.duplicated()
```
![Screenshot 2025-03-19 141326](https://github.com/user-attachments/assets/a52a423b-f89b-42fd-b5e2-0ae33ffd0f32)

```
df['DOB']
```
![Screenshot 2025-03-19 141336](https://github.com/user-attachments/assets/b608f0d6-7fd7-4d7c-8ea2-2d5a59e920cf)

```
import seaborn as sns
sns.heatmap(df.isnull(),yticklabels=False,annot=True)
```
![Screenshot 2025-03-19 141345](https://github.com/user-attachments/assets/b0c8c13e-c072-4efc-b71e-9ace105c1038)

```
df.dropna(inplace=True)
sns.heatmap(df.isnull(),yticklabels=False,annot=True)
```
![Screenshot 2025-03-19 141351](https://github.com/user-attachments/assets/2e8863ee-5fb8-44fe-a869-86b15e14f9eb)

```
age=[1,3,28,27,25,92,30,39,40,50,26,24,29,94]
df=pd.DataFrame(age)
df
```
![Screenshot 2025-03-19 141357](https://github.com/user-attachments/assets/cce2b0ae-7a10-4fa4-9c53-a0159172c7d8)

```
sns.boxplot(data=df)
```
![Screenshot 2025-03-19 141404](https://github.com/user-attachments/assets/5d50f63e-9bff-4d6c-91f5-415789f302e7)

```
sns.scatterplot(data=df)
```
![Screenshot 2025-03-19 141410](https://github.com/user-attachments/assets/a2142d7f-ec4e-40b8-8c83-d31761205d91)

```
q1=df.quantile(0.25)
q2=df.quantile(0.5)
q3=df.quantile(0.75)
iqr=q3-q1
iqr
```
![Screenshot 2025-03-19 141416](https://github.com/user-attachments/assets/d2b5e924-7b15-4efc-b9e4-cfbd05b2c8a5)

```
import numpy as np
Q1=np.percentile(df,25)
Q3=np.percentile(df,75)
IQR=Q3-Q1
IQR
```
![Screenshot 2025-03-19 141421](https://github.com/user-attachments/assets/ddc74387-040b-49f9-af3b-6502316d0f99)

```
lower_bound=Q1-1.5*IQR
upper_bound=Q3+1.5*IQR
lower_bound
```
![Screenshot 2025-03-19 141425](https://github.com/user-attachments/assets/295f58c0-ddef-40a0-bc98-092219299762)

```
upper_bound
```
![Screenshot 2025-03-19 141432](https://github.com/user-attachments/assets/e5081062-d940-4e7a-afed-882b1d919202)

```
outliers=[x for x in age if x<lower_bound or x>upper_bound]
print("Q1:",Q1)
print("Q3:",Q3)
print("IQR:",IQR)
print("Lower Bound:",lower_bound)
print("Upper Bound:",upper_bound)
print("Outliers:",outliers)
```
![Screenshot 2025-03-19 141443](https://github.com/user-attachments/assets/e7c16415-a093-4803-9b0a-707b31eecdf5)

```
df=df[((df>=lower_bound)&(df<=upper_bound))]
df
```
![Screenshot 2025-03-19 141449](https://github.com/user-attachments/assets/48aad863-cede-4092-8d5b-218af518f3f3)

```
df=df.dropna()
df
```
![Screenshot 2025-03-19 141455](https://github.com/user-attachments/assets/f4ada5c7-4396-45f9-8d18-ef48cc4ba733)

```
sns.boxplot(data=df)
```
![Screenshot 2025-03-19 141502](https://github.com/user-attachments/assets/c4e635b1-45f3-489a-84dd-5b2aae2162dc)

```
sns.scatterplot(data=df)
```
![Screenshot 2025-03-19 141508](https://github.com/user-attachments/assets/fd4b9856-3618-444b-af52-03d1e5799a11)

```
data=[1,2,2,2,3,1,1,15,2,2,2,3,1,1,2]
mean=np.mean(data)
std=np.std(data)
print('mean of the dataset is',mean)
print('std.deviation is',std)
```
![Screenshot 2025-03-19 141520](https://github.com/user-attachments/assets/92afbf0c-c344-4c4a-86b2-7b93a18172b4)

```
threshold=3
outlier=[]
for i in data:
  z=(i-mean)/std
  if z>threshold:
    outlier.append(i)
print('outlier in dataset is',outlier)
```
![Screenshot 2025-03-19 141525](https://github.com/user-attachments/assets/8ce002f6-78ae-4c61-91b1-e1d19b0c095a)

```
from scipy import stats
data={'weight':[12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,
                66,69,202,72,75,78,81,84,232,87,90,93,96,99,258]}
df=pd.DataFrame(data)
df
```
![Screenshot 2025-03-19 141545](https://github.com/user-attachments/assets/78d63409-6058-47cb-bf21-70b93618e30c)
![Screenshot 2025-03-19 141550](https://github.com/user-attachments/assets/c1f5eaf0-8b55-4bd4-a22d-0e32a7920f26)


```
z=np.abs(stats.zscore(df))
print(df[z['weight']>3])
```
![Screenshot 2025-03-19 141556](https://github.com/user-attachments/assets/630f5ec4-8916-4a85-ac39-a56a82cde38a)

# Result
        Thus the data is cleaned and the outliers are removed by detection using IQR and Z-Score.

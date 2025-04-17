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
![Screenshot 2025-03-19 141050](https://github.com/user-attachments/assets/1f6d3ff3-a24f-45c8-af35-8f2f30c32a83)


```
df.shape
```
![Screenshot 2025-03-19 141057](https://github.com/user-attachments/assets/d6aa1bb4-3e17-41b8-b80d-9ba29c581f6e)

```
df.describe()
```
![Screenshot 2025-03-19 141105](https://github.com/user-attachments/assets/5fe25682-a13f-46fc-a4d3-d3be068fb153)

```
df.info()
```
![Screenshot 2025-03-19 141111](https://github.com/user-attachments/assets/ed1e7eb3-122f-4fd0-96fe-9972bfb69aae)

```
df.head(10)
```
![Screenshot 2025-03-19 141118](https://github.com/user-attachments/assets/8762ba96-0471-425c-8919-e2dc65359541)


```
df.tail(10)
```
![Screenshot 2025-03-19 141125](https://github.com/user-attachments/assets/333cc1a5-ddee-458d-8713-2aaaff4015c6)


```
df.isna().sum()
```
![Screenshot 2025-03-19 141132](https://github.com/user-attachments/assets/2ce67569-54e9-415d-9038-23f2b18c4018)


```
df.dropna(how='any').shape
```
![Screenshot 2025-03-19 141138](https://github.com/user-attachments/assets/580b3a33-6a6f-4324-9820-376b701291f7)

```
df.shape
```
![Screenshot 2025-03-19 141142](https://github.com/user-attachments/assets/b9a23bbc-b54b-47f2-902b-b44a386665e7)


```
x=df.dropna(how='any')
x
```
![Screenshot 2025-03-19 141152](https://github.com/user-attachments/assets/14788a2c-177a-481c-8224-98b2a5aff773)


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
![Screenshot 2025-03-19 141253](https://github.com/user-attachments/assets/f9554923-5eef-4263-b7a9-7fa7d918d101)


```
df.M3.fillna(method='ffill',inplace=True)
df
```
![Screenshot 2025-03-19 141302](https://github.com/user-attachments/assets/3d25e3b2-cafc-4f17-9702-10839c0fde90)

```
df.isna().sum()
```
![Screenshot 2025-03-19 141310](https://github.com/user-attachments/assets/fa1e0014-02f5-4853-969c-d1f438c3a237)


```
df.drop_duplicates(inplace=True)
df
```
![Screenshot 2025-03-19 141319](https://github.com/user-attachments/assets/9fbde571-172a-49a3-9b6e-d42135b1e70c)

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
![Screenshot 2025-03-19 141345](https://github.com/user-attachments/assets/ec346e5f-2287-4f97-9de0-8704f6254e68)


```
df.dropna(inplace=True)
sns.heatmap(df.isnull(),yticklabels=False,annot=True)
```
![Screenshot 2025-03-19 141351](https://github.com/user-attachments/assets/5b59e9eb-6521-4115-8afc-e87f7f3a2a2e)

```
age=[1,3,28,27,25,92,30,39,40,50,26,24,29,94]
df=pd.DataFrame(age)
df
```
![Screenshot 2025-03-19 141357](https://github.com/user-attachments/assets/10150e02-170d-4f0c-963e-90060f037fca)


```
sns.boxplot(data=df)
```
![Screenshot 2025-03-19 141404](https://github.com/user-attachments/assets/33a36521-4f1d-41cc-b28e-ad81d99a9f66)


```
sns.scatterplot(data=df)
```
![Screenshot 2025-03-19 141410](https://github.com/user-attachments/assets/88bdb989-bc8a-4976-89e0-a56f2f186806)

```
q1=df.quantile(0.25)
q2=df.quantile(0.5)
q3=df.quantile(0.75)
iqr=q3-q1
iqr
```
![Screenshot 2025-03-19 141416](https://github.com/user-attachments/assets/57fa3239-cbbe-405e-b552-e0d931a101b3)


```
import numpy as np
Q1=np.percentile(df,25)
Q3=np.percentile(df,75)
IQR=Q3-Q1
IQR
```
![Screenshot 2025-03-19 141421](https://github.com/user-attachments/assets/1e3051e5-9f17-4a97-81ff-4d1c0b966645)


```
lower_bound=Q1-1.5*IQR
upper_bound=Q3+1.5*IQR
lower_bound
```
![Screenshot 2025-03-19 141425](https://github.com/user-attachments/assets/e72e066c-018e-4a33-88f1-e77c78a5f1a7)


```
upper_bound
```
![Screenshot 2025-03-19 141432](https://github.com/user-attachments/assets/676c0630-6b42-43cd-b1bb-0ff0a75fb0a0)


```
outliers=[x for x in age if x<lower_bound or x>upper_bound]
print("Q1:",Q1)
print("Q3:",Q3)
print("IQR:",IQR)
print("Lower Bound:",lower_bound)
print("Upper Bound:",upper_bound)
print("Outliers:",outliers)
```
![Screenshot 2025-03-19 141443](https://github.com/user-attachments/assets/6d73a51e-61fb-4203-9fc3-a03ac3a99f80)


```
df=df[((df>=lower_bound)&(df<=upper_bound))]
df
```
![Screenshot 2025-03-19 141449](https://github.com/user-attachments/assets/1a6bb012-217d-4d3a-bb2b-68ae0a37ceba)

```
df=df.dropna()
df
```
![Screenshot 2025-03-19 141455](https://github.com/user-attachments/assets/0f81b6a2-6fb0-4cca-9a8c-11b209a2ccbb)


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
![Screenshot 2025-03-19 141525](https://github.com/user-attachments/assets/f2b379d3-589a-43d6-bcdc-142b84f86fce)


```
from scipy import stats
data={'weight':[12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,
                66,69,202,72,75,78,81,84,232,87,90,93,96,99,258]}
df=pd.DataFrame(data)
df
```
![Screenshot 2025-03-19 141545](https://github.com/user-attachments/assets/97cce8b9-c601-4d20-b9dd-442254da195b)

![Screenshot 2025-03-19 141550](https://github.com/user-attachments/assets/7467d8e5-376d-4373-81af-3faad2ae0ad0)



```
z=np.abs(stats.zscore(df))
print(df[z['weight']>3])
```
![Screenshot 2025-03-19 141556](https://github.com/user-attachments/assets/d0486ceb-cc20-4148-bdcc-0d70b89e8588)


# Result
Thus the data is cleaned and the outliers are removed by detection using IQR and Z-Score.

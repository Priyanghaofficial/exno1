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
import pandas as pd
df=pd.read_csv("/content/SAMPLEIDS.csv")
df
```
![image](https://github.com/user-attachments/assets/89ef2e0a-749f-4247-bca9-d13b53f367a4)

```
df.shape
```
![image](https://github.com/user-attachments/assets/9899c9d8-4cbe-47ae-87eb-1677ef5d5ddf)
```
df.descride()
```
![image](https://github.com/user-attachments/assets/f6d79cda-c8e8-452a-9f9c-c3552b385604)

```
df.info
```
![image](https://github.com/user-attachments/assets/df2511d1-ea99-41f2-9a3d-403ece6d0885)

```
df.head(3)
```
![image](https://github.com/user-attachments/assets/b7ef700b-183f-4c07-aef7-10f57f44948d)
```
df.tail(3)
```
![image](https://github.com/user-attachments/assets/4dd9561e-d1b3-4552-8d1d-c128d647d416)
```
df.isnull().sum()
```
![image](https://github.com/user-attachments/assets/d6f3d63e-2457-427e-bd82-cd58a3809c7a)

![image](https://github.com/user-attachments/assets/61e56603-93a9-4763-9046-657bd7b3e423)
```
mn=df.TOTAL.mean()
mn
```
![image](https://github.com/user-attachments/assets/9b6d412c-6e08-4920-b076-d1c90c76192b)
```
df.TOTAL.fillna(mn,inplace=True)
df
```
![image](https://github.com/user-attachments/assets/3d359297-ee6a-44d4-bde7-e7804b23774b)
```
df['M1']
```
![image](https://github.com/user-attachments/assets/3ada5548-53d3-493d-9bdb-03b69372d104)
```
df['M1'].fillna('ffill',inplace=True)
df
```
![image](https://github.com/user-attachments/assets/2041602a-edd4-478f-aa7d-4b38621ced11)
```
df.duplicated()
```
![image](https://github.com/user-attachments/assets/d2027405-46b4-4b35-8f1c-83d821434596)
```
df.drop_duplicates(inplace=True)
df
```
![image](https://github.com/user-attachments/assets/eaba2d3e-cfd4-4bff-9abb-f36da593a0b3)
```
df.duplicated()
```
![image](https://github.com/user-attachments/assets/fa2499ec-d0d5-4573-819e-fe9c88d8a753)

-----------------------------------------------------------------------------------------------
```
import seaborn as sns
sns.heatmap(df.isnull(),yticklabels=False,annot=True)
```
![image](https://github.com/user-attachments/assets/d4a3f1e9-effd-4d18-907c-438d9baf1f2e)

```
df.dropna(inplace=True)
df
```
![image](https://github.com/user-attachments/assets/dfbe4ae8-2110-4f0e-8b73-999f16b9476c)

![image](https://github.com/user-attachments/assets/4ef4a40c-13f4-45a4-9950-8f649798a806)

-----------------------------------------------------------------------------------------------
```
import pandas as pd
import seaborn as sns
import numpy as np

age=[1,3,28,27,25,92,30,39,40,50,26,24,29,94]
af=pd.DataFrame(age)
af
```
![image](https://github.com/user-attachments/assets/f36d86c2-0f7c-44d1-98a6-b87e5f751366)
```
sns.boxplot(data=af)
```
![image](https://github.com/user-attachments/assets/f6a9af09-b621-4724-8986-c9953ba4d9ab)
```
sns.scatterplot(data=af)
```
![image](https://github.com/user-attachments/assets/5aeaa075-6dbf-441e-8939-146423597d17)
```
q1=af.quantile(0.25)
q2=af.quantile(0.50)
q3=af.quantile(0.75)
iqr=q3-q1
iqr

or

Q1=np.percentile(af,25)
Q2=np.percentile(af,50)
Q3=np.percentile(af,75)
IQR=Q3-Q1
IQR
```
![image](https://github.com/user-attachments/assets/fbb7d867-cdb5-4647-88cd-3b095baa77a2)
```
lower_bound=Q1-(1.5*IQR)
upper_bound=Q3+(1.5*IQR)
lower_bound,upper_bound
```
![image](https://github.com/user-attachments/assets/935580ba-ab1a-481d-9dab-0a641ff6f97d)
```
print("Q1:",Q1)

print("Q3:",Q3)
print("IQR:",IQR)
print("Lower Bound:",lower_bound)
print("Upper Bound:",upper_bound)
print("Outliers:",outliers)
```
![image](https://github.com/user-attachments/assets/2c82ce5b-9c53-4e89-8f95-04b15a049555)
```
af=af[(af>lower_bound)&(af<upper_bound)]
af
```
![image](https://github.com/user-attachments/assets/9588f09e-e563-4a1d-8703-d107d99fa4c6)


![image](https://github.com/user-attachments/assets/7ce8d15e-197a-4aac-9ffd-b624fbdb0eb3)


![image](https://github.com/user-attachments/assets/273d0718-7cbc-46f3-be99-e78463c659a4)


![image](https://github.com/user-attachments/assets/df45ed05-1b46-4840-a30c-f2fd3b301bc8)

# Result
Thus the given program executed successfully.


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
~~~
NAME : VASU VIGNESHWARAN P
REG NO : 212224220119
~~~
~~~
import pandas as pd
df=pd.read_csv("/content/SAMPLEIDS.csv")
df
~~~
![Screenshot 2025-04-21 221109](https://github.com/user-attachments/assets/dbff194a-7a70-49e7-870b-499b09b60437)


~~~
df.shape
~~~
![Screenshot 2025-04-21 221602](https://github.com/user-attachments/assets/b066fb79-4fec-4303-a6e2-6a5f4e523fb6)


~~~
df.describe()
~~~

~~~
df.info()
~~~
![Screenshot 2025-04-21 221623](https://github.com/user-attachments/assets/8a3d3b46-41ec-42ce-8b47-19f7027daac7)

~~~
df.shape
~~~
![Screenshot 2025-04-21 221642](https://github.com/user-attachments/assets/15ccc635-93dd-4f59-9923-9602c62e4ddb)


~~~
df.head(10)
~~~
![Screenshot 2025-04-21 221658](https://github.com/user-attachments/assets/a0879cbd-feba-4e05-ace8-5c5b631cd504)

~~~
df.tail(10)
~~~
![Screenshot 2025-04-21 221737](https://github.com/user-attachments/assets/cd0db8c6-3d48-4e64-aeec-ba59472dc742)

~~~
df.isna().sum()
~~~
![Screenshot 2025-04-21 221746](https://github.com/user-attachments/assets/5a973e17-f5e3-49f9-a0d9-80a5ea9e4967)

~~~
df.dropna(how='any').shape
~~~
![Screenshot 2025-04-21 221754](https://github.com/user-attachments/assets/52d45c3f-29e4-4427-82ca-b6f030a137c8)

~~~
d=df.dropna(how='any')
d
~~~
![Screenshot 2025-04-21 221817](https://github.com/user-attachments/assets/5047c7c4-d986-4814-ae70-fb932e3708f7)

~~~
mn=df.TOTAL.mean()
mn
~~~
![Screenshot 2025-04-21 221828](https://github.com/user-attachments/assets/de2a121b-d39a-47fc-b031-1a353ef6a3dc)

~~~
df.TOTAL.fillna(mn,inplace=True)
df
~~~
![Screenshot 2025-04-21 221905](https://github.com/user-attachments/assets/3f1fca2c-f46d-4ef4-a851-7abd487c7e0d)

~~~
df.isnull().sum()
~~~
![Screenshot 2025-04-21 221914](https://github.com/user-attachments/assets/364b45a7-3ec3-4d15-bf1f-1af34eb47efc)

~~~
df.M1.fillna(method='ffill',inplace=True)
df
~~~
![Screenshot 2025-04-21 221931](https://github.com/user-attachments/assets/f180afd7-f775-422a-b6ff-98e0524fd4c2)

~~~
df.isnull().sum()
~~~
![Screenshot 2025-04-21 221939](https://github.com/user-attachments/assets/e31a050b-fc23-4100-ade4-942897cd8b5b)

~~~
df.M2.fillna(method='ffill',inplace=True)
df
~~~
![Screenshot 2025-04-21 221955](https://github.com/user-attachments/assets/d2f7f5de-ca98-4411-b99e-f1114b9ea68b)

~~~
df.isnull().sum()
~~~
![Screenshot 2025-04-21 222003](https://github.com/user-attachments/assets/9b8fb9ae-7ebd-48b3-8cee-9ec1abbc708e)

~~~
df.M3.fillna(method='ffill',inplace=True)
df
~~~
![Screenshot 2025-04-21 222019](https://github.com/user-attachments/assets/21017de1-cbc5-49dd-a6f9-4dc87474c95e)

~~~
df.isnull().sum()
~~~
![Screenshot 2025-04-21 222040](https://github.com/user-attachments/assets/4efe8ffc-b0f4-43b5-bf88-f4494f39cd05)

~~~
df.duplicated()
~~~
![Screenshot 2025-04-21 222046](https://github.com/user-attachments/assets/379dae85-de79-41da-83a9-f7fcc482270c)

~~~
df.drop_duplicates(inplace=True)
df
~~~
![Screenshot 2025-04-21 222053](https://github.com/user-attachments/assets/611bfe02-3391-4781-8eb3-bdc9e89b1c64)

~~~
df.duplicated()
~~~
![Screenshot 2025-04-21 222100](https://github.com/user-attachments/assets/a6b34bf9-99cd-4448-bdc2-5cf0260a4094)

~~~
df['DOB']
~~~
![Screenshot 2025-04-21 222107](https://github.com/user-attachments/assets/4c7eb7ea-23b4-4b11-aaa4-033e1d748d61)

~~~
import seaborn as sns
sns.heatmap(df.isnull(),yticklabels=False,annot=True)
~~~
![Screenshot 2025-04-21 222114](https://github.com/user-attachments/assets/78fdb56b-7379-42cc-88da-b601b0eba24b)

~~~
df.dropna(inplace=True)
sns.heatmap(df.isnull(),yticklabels=False,annot=True)
~~~
![Screenshot 2025-04-21 222119](https://github.com/user-attachments/assets/044ea87b-3a45-45d0-9956-81a7cc58db98)

~~~
import pandas as pd
import seaborn as sns
import numpy as np
ans=[1,3,28,27,25,92,30,39,40,50,26,24,29,94]
df=pd.DataFrame(ans)
df
~~~
![Screenshot 2025-04-21 222125](https://github.com/user-attachments/assets/c49b4bee-eb21-44e5-a395-b5efda066900)

~~~
age=[1,3,28,27,25,92,30,39,40,50,26,24,29,94]
df=pd.DataFrame(age)
df
~~~
![Screenshot 2025-04-21 222130](https://github.com/user-attachments/assets/cb7e0a76-b108-4284-a4d4-6dae96e43089)

~~~
sns.boxplot(data=ans)
~~~
![Screenshot 2025-04-21 222136](https://github.com/user-attachments/assets/75396a7c-530a-47b1-b6b7-ecbc0d3cfb6a)

~~~
sns.scatterplot(data=df)
~~~
![Screenshot 2025-04-21 222141](https://github.com/user-attachments/assets/ab3a0b3e-556e-4460-bbb6-2c41fd5c405e)

~~~
q1=df.quantile(0.25)
q2=df.quantile(0.5)
q3=df.quantile(0.75)
iqr=q3-q1
iqr
~~~
![Screenshot 2025-04-21 222147](https://github.com/user-attachments/assets/75d9f50e-11d9-4b55-bdc5-e83cc7e0a2b3)

~~~
upper_bound=q3+1.5*iqr
lower_bound=q1-1.5*iqr
upper_bound
~~~
![Screenshot 2025-04-21 222152](https://github.com/user-attachments/assets/20fb522b-69b0-4b21-81f2-6268b4cedfde)

~~~
lower_bound
~~~
![Screenshot 2025-04-21 222156](https://github.com/user-attachments/assets/6ff97525-1f61-448c-a076-64d548eb354d)

~~~
outliers=[x for x in age if x<lower_bound or x>upper_bound]
print("Q1:",q1)
print("Q3:",q3)
print("IQR:",iqr)
print("Lower Bound:",lower_bound)
print("Upper Bound:",upper_bound)
print("Outliers:",outliers)
~~~
![Screenshot 2025-04-21 222204](https://github.com/user-attachments/assets/0c9b86e7-53dd-474d-bbc5-176a45363758)

~~~
df=df[(df>=lower_bound)&(df<=upper_bound)]
df
~~~
![Screenshot 2025-04-21 222208](https://github.com/user-attachments/assets/55373e63-7ac3-4a79-acde-cd0468b7582c)

~~~
df=df.dropna()
df
~~~
![Screenshot 2025-04-21 222214](https://github.com/user-attachments/assets/47086cb2-466d-4f16-ac1c-faf427311099)

~~~
sns.boxplot(data=df)
~~~
![Screenshot 2025-04-21 222219](https://github.com/user-attachments/assets/fe5deedd-b75f-4406-b47a-6716136c9fcc)

~~~
data=[1,2,2,2,3,1,1,15,2,2,2,3,1,1,2]
mean=np.mean(data)
std=np.std(data)
print('mean of the dataset is',mean)
print('std.deviation is',std)
~~~
![Screenshot 2025-04-21 222225](https://github.com/user-attachments/assets/1116ba16-4d9f-4573-95f2-52daee7e6160)

~~~
 threshold=3
 outlier=[]
 for i in data:
  z=(i-mean)/std
  if z>threshold:
    outlier.append(i)
 print('outlier in dataset is :',outlier)
~~~
![Screenshot 2025-04-21 222231](https://github.com/user-attachments/assets/bf9a913e-3d0a-4aa7-b0a0-c6f17633f73d)

~~~
import pandas as pd
 import numpy as np
 import seaborn as sns
 from scipy import stats
 data={'weight':[12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,
66,69,202,72,75,78,81,84,232,87,90,93,96,99,258]}
 df=pd.DataFrame(data)
 df
~~~
![Screenshot 2025-04-21 222255](https://github.com/user-attachments/assets/d445399f-8c68-412b-ba9f-68cbc74a0bd6)

~~~
w=np.abs(stats.zscore(df))
print(df[w['weight']>3])
~~~
![Screenshot 2025-04-21 222308](https://github.com/user-attachments/assets/6f8e5387-5ba7-4d9d-b959-16666e24c510)


# Result
Thus we have cleaned the data and removed the outliers by detection using IQR and Z-score

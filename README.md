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
df=pd.read_csv("Data_set.csv")
df.head(5)
```
![image](https://github.com/SanjithaBolisetti/exno1/assets/119393633/e5ee2149-73f3-49b5-afb5-02ce88b26f8a)

```
df.tail(3)
```
![image](https://github.com/SanjithaBolisetti/exno1/assets/119393633/a3f27304-586b-4d9e-b349-f37a6c8b0b8b)

```
df.info()
```
![image](https://github.com/SanjithaBolisetti/exno1/assets/119393633/dbb6ddd0-38ff-469b-9136-bfb622cee6cb)

```
df.describe()
```
![image](https://github.com/SanjithaBolisetti/exno1/assets/119393633/aa9cf5df-ed12-40f4-a0a0-2a9ac7e4d10b)

```
df.isnull()
```
![image](https://github.com/SanjithaBolisetti/exno1/assets/119393633/df6323ee-fbb5-4183-80ff-c7cc04bff548)

```
df.dropna(axis=1)
#df.dropna(axis=0)
```
![image](https://github.com/SanjithaBolisetti/exno1/assets/119393633/4eebd25c-b2be-4ba4-8ece-a62928bfd038)

```
df.fillna(method='bfill')
#df.fillna(method='ffill')
```
![image](https://github.com/SanjithaBolisetti/exno1/assets/119393633/ea314ab4-1af3-4fdb-b99e-c2c493cdb5f1)

```
import seaborn as sns
sns.heatmap(df.isnull(),yticklabels=False,annot=True)
```
![image](https://github.com/SanjithaBolisetti/exno1/assets/119393633/1a89a3a4-6ea1-46f2-aae8-8dfd5822dd2f)

```
df.dropna(inplace=True)
sns.heatmap(df.isnull(),yticklabels=False,annot=True)
```
![image](https://github.com/SanjithaBolisetti/exno1/assets/119393633/d12ac9ef-219f-426b-b8fd-bc0b9308284b)

```
import pandas as pd
import seaborn as sns
import numpy as np
from scipy import stats
df=pd.read_csv("heights.csv")
df
```
![image](https://github.com/SanjithaBolisetti/exno1/assets/119393633/8feaca32-efb6-4a23-a1ee-4607d6628f1c)

```
sns.boxplot(data=df)
```
![image](https://github.com/SanjithaBolisetti/exno1/assets/119393633/a64b5776-827b-4e0d-be1b-87ebcabaa16c)

```
sns.scatterplot(data=df)
```
![image](https://github.com/SanjithaBolisetti/exno1/assets/119393633/87961d5e-d834-4fd9-a6a3-5bd5ce5f7d81)

```
qm=df[((df['height']>=low)&(df['height']<=high))]
qm
```
![image](https://github.com/SanjithaBolisetti/exno1/assets/119393633/66477c7f-9d10-4566-a7a6-8c8d0d00b9a0)

```
sns.boxplot(data=qm)
```
![image](https://github.com/SanjithaBolisetti/exno1/assets/119393633/0dd34661-bb72-4aea-95c0-f7d3dfcfaa43)

```
sns.scatterplot(data=qm)
```
![image](https://github.com/SanjithaBolisetti/exno1/assets/119393633/0941b0c5-8093-425c-b219-39b0a3fed0fa)

# Result
Cleaning of Data and Removing of Outline executed successfully.

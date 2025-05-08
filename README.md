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
 df=pd.read_csv("SAMPLEIDS.csv")
 df.isnull()
  ```
![image](https://github.com/user-attachments/assets/eefaca7b-a22a-4e61-8c9e-11f2e0cbf25d)

```
df.notnull()
```
![image](https://github.com/user-attachments/assets/750c0bd8-4bb4-477c-a19f-7dd478aab928)

```
df.dropna(axis=0)
```

![image](https://github.com/user-attachments/assets/e7a03261-8826-40d9-abd5-b17aa6320f62)

```
df.dropna(axis=1)
```
![image](https://github.com/user-attachments/assets/fe704ef5-7be9-483b-b5fa-08e60a6b2aad)

```
df.shape[1]
```
![image](https://github.com/user-attachments/assets/c2542a05-58db-4eca-8cd3-9a0806c37b98)

```
df.shape[0]
```
![image](https://github.com/user-attachments/assets/9e2d8f7c-7da4-4621-a4c8-d5f92ea48cae)

```
df.shape
```
![image](https://github.com/user-attachments/assets/38217bdb-dcb2-4c13-b983-2d68ccdbc9c7)

```
df.describe()
```
![image](https://github.com/user-attachments/assets/0b48575d-e3d1-4e76-83e3-620d52094390)

```
df.info()
```
![image](https://github.com/user-attachments/assets/9f1c22af-1a0a-4b2b-985c-80a77d526b6d)

```
df.isnull().sum()
```
![image](https://github.com/user-attachments/assets/733d5fac-452d-4303-88db-19296f7b5eae)

```
M = df.TOTAL.mean()
M
df.fillna(M)
```
![image](https://github.com/user-attachments/assets/27008b06-3b4d-4c40-ad6a-0fe75e268e4c)

```
df.nunique()
```
![image](https://github.com/user-attachments/assets/27873f0c-4dcc-49ba-b853-35c91eca08f8)
```
import pandas as pd
import seaborn as sns
import numpy as np
age = [1,3,28,27,25,92,30,39,40,50,26,24,29,94]
af = pd.DataFrame(age)
af
sns.boxplot(data=af)
sns.scatterplot(data=af)
```
![image](https://github.com/user-attachments/assets/fa30a87f-cb2b-4f22-af7c-c67213f92615)

```
import pandas as pd
import seaborn as sns
import numpy as np
age = [1,3,28,27,25,92,30,39,40,50,26,24,29,94]
af = pd.DataFrame(age)
Q1=np.percentile(af,25)
print("Q1=",Q1)
Q3=np.percentile(af,75)
print("Q3=",Q3)
IQR = Q3-Q1
print("IQR=",IQR)
lower_bound = Q1- 1.5*IQR
print("lower bound=",lower_bound)
upper_bound= Q3 + 1.5*IQR
print("upper bound=",upper_bound)
outliers = [x for x in age if  x <  lower_bound  or x  > upper_bound]
print("outliers=",outliers)
af= af [((af>=lower_bound)&(af<=upper_bound))]
sns.boxplot(data=af)
sns.scatterplot(data=af)
```
![image](https://github.com/user-attachments/assets/406b88b0-4b88-4e62-9930-ad43923eb22f)

```
import pandas as pd
import seaborn as sns
import numpy as np
from scipy import stats
id=pd.read_csv("student_scores.csv")
sns.boxplot(x='Hours',data=id)
```
![image](https://github.com/user-attachments/assets/2ac17879-a1a0-4bbf-bb48-56bac172f166)



# Result
Thus the data cleaning process on the given dataset is executed successfully.

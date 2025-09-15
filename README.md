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
```
import pandas as pd
import numpy as np
import seaborn as sns
df=pd.read_csv("/titanic_dataset.csv")
df
```
<img width="1530" height="667" alt="image" src="https://github.com/user-attachments/assets/f6829b33-4a44-489d-80dd-1528bc579a6f" />

```
df.info()
```

<img width="533" height="478" alt="image" src="https://github.com/user-attachments/assets/e881179d-614f-4edd-a6eb-bcefa227d4d4" />

```
df.describe()
```

<img width="914" height="417" alt="image" src="https://github.com/user-attachments/assets/78baac72-7e81-4dfc-8cd6-d563e2c2e3a1" />

```
df.dtypes
```

<img width="273" height="601" alt="image" src="https://github.com/user-attachments/assets/2b9a77bf-02db-4b63-943b-cdc89a913fd5" />

```
df.shape
```

<img width="128" height="86" alt="image" src="https://github.com/user-attachments/assets/fdf7a3fe-ee84-452a-9474-f231f6223408" />

```
df.value_counts()
```

<img width="1554" height="606" alt="image" src="https://github.com/user-attachments/assets/22db45f4-ac93-4182-a0e7-46ed6137c3b5" />

```
df['Age'].value_counts()
```

<img width="373" height="648" alt="image" src="https://github.com/user-attachments/assets/99c29dc5-a78b-4e0b-93b5-ba30c339f52a" />

```
df.set_index("PassengerId",inplace=True)
df
```

<img width="1442" height="631" alt="image" src="https://github.com/user-attachments/assets/b971959d-60d5-4c72-99f5-e885af612eb2" />

```
df.nunique()
```

<img width="260" height="575" alt="image" src="https://github.com/user-attachments/assets/38a8b510-4226-4dcf-92cc-848f9677f654" />

```
sns.countplot(data=df,x="Age")
```

<img width="790" height="619" alt="image" src="https://github.com/user-attachments/assets/e3527774-950f-43f3-98bc-38b3d62f2371" />

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```

<img width="1501" height="610" alt="image" src="https://github.com/user-attachments/assets/87564ab5-f8a7-4607-8efc-780b03149acb" />

```
sns.catplot(x="Age",col="Survived",kind="count",data=df,height=5,aspect=.7)
```

<img width="931" height="676" alt="image" src="https://github.com/user-attachments/assets/53d5552e-39fd-465e-a91a-2be492595677" />

```
df.boxplot(column="Age",by="Survived")
```

<img width="779" height="661" alt="image" src="https://github.com/user-attachments/assets/f8335b2b-0a4b-4979-b9ab-427fb6b0203c" />

```
sns.scatterplot(x=df["Age"],y=df['Fare'])
```

<img width="774" height="629" alt="image" src="https://github.com/user-attachments/assets/321a5032-ac5c-405a-a41b-22f61aca7c68" />

```
plt=sns.boxplot(x='Pclass',y='Age',hue='Gender',data=df)
```


<img width="715" height="596" alt="image" src="https://github.com/user-attachments/assets/b3fb3ad3-a91e-4496-8f45-b2a8153dbd87" />

```
sns.catplot(x='Pclass',y='Age',hue='Gender',col='Survived',kind='box',data=df)
```

<img width="1434" height="699" alt="image" src="https://github.com/user-attachments/assets/5cf16986-550e-4a40-bfe3-cb10173bef34" />

```
corr=df.corr(numeric_only=True)
sns.heatmap(corr,annot=True)
```


<img width="807" height="637" alt="image" src="https://github.com/user-attachments/assets/4c8faa45-a86a-4889-99c4-db6fb0570f97" />

# RESULT
Thus, Exploratory Data Analysis on the given data set is successfully performed.

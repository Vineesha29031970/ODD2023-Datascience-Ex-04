# Ex-04: Multivariate Analysis

# AIM:

To perform Multivariate EDA on the given data set.

# EXPLANATION:

Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

# ALGORITHM:

STEP 01:
Import the built libraries required to perform EDA and outlier removal.

STEP 02:
Read the given csv file

STEP 03:
Convert the file into a dataframe and get information of the data.

STEP 04:
Return the objects containing counts of unique values using (value_counts()).

STEP 05:
Plot the counts in the form of Histogram or Bar Graph.

STEP 06:
Use seaborn the bar graph comparison of data can be viewed.

STEP 07:
Find the pairwise correlation of all columns in the dataframe.corr()

STEP 08:
Save the final data set into the file.

# PROGRAM:

# Superstore CSV File:

```
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
data=pd.read_csv("/content/SuperStore (1).csv")
df=pd.DataFrame(data)
df.head()
df.info()
df.describe()
df.isnull().sum()
df['Postal Code']=df['Postal Code'].fillna(df['Postal Code'].mode()[0])
df.isnull().sum()

sns.scatterplot(x=df['Region'],y=df['Sales'])

states=df.loc[:,["State","Sales"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Sales")
plt.figure(figsize=(12,5))
plt.xticks(rotation=90)
sns.barplot(x=states.index,y="Sales",data=states)

states=df.loc[:,["Ship Mode","Row ID"]]
states=states.groupby(by=["Ship Mode"]).sum().sort_values(by="Row ID")
sns.barplot(x=states.index,y="Row ID",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("SHIP MODE")
plt.ylabel=("ROW ID")
plt.show()

sns.boxplot(x=df['Ship Date'],y=df['Sales'])
sns.displot(df, x="Region", hue="Category")
df.corr()
sns.heatmap(df.corr(),annot=True)
Diabetes CSV File:
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
df=pd.read_csv("/content/diabetes (1).csv")
df
df.describe()
df.info
df.isnull().sum()

sns.scatterplot(x=df['Glucose'],y=df['BloodPressure'])

sns.scatterplot(x=df['Glucose'], y=df['BloodPressure'], hue=df['Outcome'])

Age=df.loc[:,["Age","BMI"]]
Age=Age.groupby(by=["Age"]).sum().sort_values(by="BMI")
plt.figure(figsize=(12,5))
plt.xticks(rotation=90)
sns.barplot(x=Age.index,y="BMI",data=Age)

Age=df.loc[:,["BloodPressure","Glucose"]]
Age=Age.groupby(by=["BloodPressure"]).sum().sort_values(by="Glucose")
sns.barplot(x=Age.index,y="Glucose",data=Age)
plt.xticks(rotation = 90)
plt.xlabel=("BloodPressure")
plt.ylabel=("Glucose")
plt.show()

sns.boxplot(x=df['DiabetesPedigreeFunction'],y=df['Insulin'])

sns.displot(df, x="Glucose", hue="Outcome")

df.corr()

sns.heatmap(df.corr(),annot=True)
```
# Output:

# SUPERSTORE OUTPUT:


<img width="548" alt="image" src="https://github.com/Vineesha29031970/ODD2023-Datascience-Ex-04/assets/133136880/20dcf804-d218-4d9e-a025-244c719cd91a">


<img width="642" alt="image" src="https://github.com/Vineesha29031970/ODD2023-Datascience-Ex-04/assets/133136880/11d7d840-622a-41ac-8c7a-b1a1a2ac92b2">


<img width="545" alt="image" src="https://github.com/Vineesha29031970/ODD2023-Datascience-Ex-04/assets/133136880/6845e99e-0122-401e-a70c-a96b020f7ef6">


<img width="491" alt="image" src="https://github.com/Vineesha29031970/ODD2023-Datascience-Ex-04/assets/133136880/128edf9b-b3eb-412f-838a-1be6ddd0ab13">


<img width="493" alt="image" src="https://github.com/Vineesha29031970/ODD2023-Datascience-Ex-04/assets/133136880/67d3ca1c-7d56-43d5-afad-323621fdc2ea">


<img width="626" alt="image" src="https://github.com/Vineesha29031970/ODD2023-Datascience-Ex-04/assets/133136880/e09d35f3-1cdd-41bf-b740-64544375ca56">


<img width="608" alt="image" src="https://github.com/Vineesha29031970/ODD2023-Datascience-Ex-04/assets/133136880/bb8daa54-57a1-4fc0-bd8e-afaf3f548a83">


# DIABETES OUTPUT:

<img width="594" alt="image" src="https://github.com/Vineesha29031970/ODD2023-Datascience-Ex-04/assets/133136880/8a7cfa13-f795-492b-a2a1-0e98de0ea5e0">


<img width="617" alt="image" src="https://github.com/Vineesha29031970/ODD2023-Datascience-Ex-04/assets/133136880/40510904-bb2e-435a-b548-cd2857b08759">


<img width="598" alt="image" src="https://github.com/Vineesha29031970/ODD2023-Datascience-Ex-04/assets/133136880/553ecf59-8d71-4469-8be1-58f9cc022fb5">


<img width="577" alt="image" src="https://github.com/Vineesha29031970/ODD2023-Datascience-Ex-04/assets/133136880/08c9640a-9226-47e1-897b-d3a0cabef2f5">


<img width="564" alt="image" src="https://github.com/Vineesha29031970/ODD2023-Datascience-Ex-04/assets/133136880/55b27a17-5ef8-468a-a75a-d1537f5faf22">


<img width="512" alt="image" src="https://github.com/Vineesha29031970/ODD2023-Datascience-Ex-04/assets/133136880/43349fdb-fe17-4819-a9a9-c58b1cab980c">


<img width="623" alt="image" src="https://github.com/Vineesha29031970/ODD2023-Datascience-Ex-04/assets/133136880/4ad4cfeb-7e28-4a8a-8269-9ce7760a23e7">


<img width="563" alt="image" src="https://github.com/Vineesha29031970/ODD2023-Datascience-Ex-04/assets/133136880/5da841e3-1e55-4689-9cdc-e4f9eeda7f52">


# Result:

Thus we have read the given data and performed the multivariate analysis with different types of plots.

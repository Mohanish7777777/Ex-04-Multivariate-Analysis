# Ex-04-Multivariate-Analysis

## AIM :

To perform Multivariate EDA on the given data set.

## EXPLANATION :

Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

## ALGORITHM :

### STEP1
Import the built libraries required to perform EDA and outlier removal.

### STEP2
Read the given csv file.

### STEP3
Convert the file into a dataframe and get information of the data.

### STEP4
Return the objects containing counts of unique values using (value_counts()).

### STEP5
Plot the counts in the form of Histogram or Bar Graph.

### STEP6
Use seaborn the bar graph comparison of data can be viewed.

### STEP7
Find the pairwise correlation of all columns in the dataframe.corr() .

### STEP8
Save the final data set into the file.

## PROGRAM:

Developed by : Mohanish K

Register number : 212220043004

```
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt

data=pd.read_csv("SuperStore.csv")
data

data.head()

data.info()

data.describe()

data.isnull().sum()

data.dtypes

sns.scatterplot(data['Postal Code'],data['Sales'])

states=data.loc[:,["State","Sales"]] 
states=states.groupby(by=["State"]).sum().sort_values(by="Sales") 
plt.figure(figsize=(17,7)) 
sns.barplot(x=states.index,y="Sales",data=states) 
plt.xticks(rotation = 90) 
plt.xlabel=("STATES")
plt.ylabel=("SALES") 
plt.show()

states=data.loc[:,["State","Postal Code"]] 
states=states.groupby(by=["State"]).sum().sort_values(by="Postal Code") 
plt.figure(figsize=(17,7)) 
sns.barplot(x=states.index,y="Postal Code",data=states) 
plt.xticks(rotation = 90) 
plt.xlabel=("STATES") 
plt.ylabel=("Postal Code") 
plt.show()

states=data.loc[:,["Segment","Sales"]] 
states=states.groupby(by=["Segment"]).sum().sort_values(by="Sales") 
plt.figure(figsize=(10,7)) 
sns.barplot(x=states.index,y="Sales",data=states) 
plt.xticks(rotation = 90) 
plt.xlabel=("SEGMENT") 
plt.ylabel=("SALES") 
plt.show()

sns.barplot(data['Postal Code'],data['Ship Mode'],hue=data['Region'])

data.corr()

sns.heatmap(data.corr(),annot=True)
```

## OUTPUT :

### DATASET
![image](https://user-images.githubusercontent.com/119560261/229704284-f08c9e98-00fd-48eb-8c75-8d481fbb14bd.png)

### HEAD DATA 
![image](https://user-images.githubusercontent.com/119560261/229704426-f0fc9389-b7c5-4992-b8b2-b563d5f2969f.png)

### INFORMATION
![image](https://user-images.githubusercontent.com/119560261/229704532-b4866a85-eda8-4ada-8a6e-7c932655bb60.png)

### DESCRIPTION
![image](https://user-images.githubusercontent.com/119560261/229704620-cf9ffcba-8dcd-4b11-9b29-0933864f9da1.png)

### DATATYPE
![image](https://user-images.githubusercontent.com/119560261/229704723-6a897352-4aab-49f6-ae16-75932e119b40.png)

### NULL DATA
![image](https://user-images.githubusercontent.com/119560261/229704833-371480f4-3e70-478d-a119-e12644d42fd5.png)

### SCATTER PLOT
![image](https://user-images.githubusercontent.com/119560261/229704942-7f5c2794-e712-454a-b466-45122c987bc0.png)

### BAR PLOT - State and Sales
![image](https://user-images.githubusercontent.com/119560261/229705109-293bb859-cc81-4353-aef2-c89ac3387400.png)

### BAR PLOT - State and Postal code
![image](https://user-images.githubusercontent.com/119560261/229705233-00a9d405-6b8f-4a5f-ba47-00bd78d13b0e.png)

### BAR PLOT- Segment and Sales
![image](https://user-images.githubusercontent.com/119560261/229705324-12ee1a7c-ff77-40a4-8cb1-fabc3e4547b9.png)

### BAR PLOT - Postal code and Ship mode
![image](https://user-images.githubusercontent.com/119560261/229705431-290154b1-84ac-49ca-a3b2-58c8ecc4403c.png)

### CORRELATION COEFFICIENT
![image](https://user-images.githubusercontent.com/119560261/229705628-049c6fa1-03f7-4b14-927b-58b51e33a64c.png)

### HEATMAP
![image](https://user-images.githubusercontent.com/119560261/229705727-5db4df43-3246-43d8-904c-41f59f768e4b.png)

## RESULT:
Thus the program to perform Multivariate EDA on the given data set is successfully executed.

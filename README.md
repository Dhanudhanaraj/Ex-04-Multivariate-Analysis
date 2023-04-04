# Ex-04-Multivariate-Analysis
## AIM:

To perform Multivariate EDA on the given data set.

## EXPLANATION:
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

## ALGORITHM:
### STEP 1
Import the built libraries required to perform EDA and outlier removal.

### STEP 2
Read the given csv file.

### STEP 3
Convert the file into a dataframe and get information of the data.

### STEP 4
Return the objects containing counts of unique values using (value_counts()).

### STEP 5
Plot the counts in the form of Histogram or Bar Graph.

### STEP 6
Use seaborn the bar graph comparison of data can be viewed.

### STEP 7
Find the pairwise correlation of all columns in the dataframe.corr() .

### STEP 8
Save the final data set into the file.

## PROGRAM:
```
NAME:D.Dhanumalya.
REG NO:212222230030.

import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
data=pd.read_csv("SuperStore.csv")
data

data.head()

data.info()

data.describe()

data.dtypes

data.isnull().sum()

data['Postal Code']=data['Postal Code'].fillna(data['Postal Code'].mode()[0])
data.isnull().sum()

sns.scatterplot(x=data['Country'],y=data['Sales'],data=data)

states=data.loc[:,["Region","Sales"]] 
states=states.groupby(by=["Region"]).sum().sort_values(by="Sales") 
plt.figure(figsize=(17,7)) 
sns.barplot(x=states.index,y="Sales",data=states) 
plt.xticks(rotation = 90) 
plt.xlabel=("REGION")
plt.ylabel=("SALES") 
plt.show()

states=data.loc[:,["State","Sales"]] 
states=states.groupby(by=["State"]).sum().sort_values(by="Sales") 
plt.figure(figsize=(17,7)) 
sns.barplot(x=states.index,y="Sales",data=states) 
plt.xticks(rotation = 90) 
plt.xlabel=("SALES") 
plt.ylabel=("STATES") 
plt.show()

states=data.loc[:,["Category","Sales"]] 
states=states.groupby(by=["Category"]).sum().sort_values(by="Sales") 
plt.figure(figsize=(10,7)) 
sns.barplot(x=states.index,y="Sales",data=states) 
plt.xticks(rotation = 90) 
plt.xlabel=("CATEGORY") 
plt.ylabel=("SALES") 
plt.show()

sns.barplot(data['Postal Code'],data['Ship Mode'],hue=data['Region'])

data.corr()

sns.heatmap(data.corr(),annot=True)
```

## OUTPUT:

### DATASET
![DS1](https://user-images.githubusercontent.com/119218812/229864110-5c475eaa-ebee-47b5-804a-70d1cc9523ce.png)


### HEAD()
![DS2](https://user-images.githubusercontent.com/119218812/229864140-5903d2be-0291-45f1-acf9-650ac42a7022.png)


### INFO()
![DS3](https://user-images.githubusercontent.com/119218812/229864159-75765a8f-a225-4519-a3f6-c26b744bfb13.png)


### DESCRIBE()
![DS4](https://user-images.githubusercontent.com/119218812/229864180-b432768a-c79a-46b1-b269-1442b99c5588.png)


### DATATYPE()
![DS5](https://user-images.githubusercontent.com/119218812/229864232-5c7824db-7b82-49f6-989e-ce97c3315b29.png)


### ISNULL()
![DS6](https://user-images.githubusercontent.com/119218812/229864270-8828cc8f-7a97-47a6-b499-8910690dae1b.png)

![DS7](https://user-images.githubusercontent.com/119218812/229864310-6ed370be-22c2-4608-8c4e-ed930c86182d.png)


## MULTIVARIATE ANALYSIS
### SCATTER PLOT
![DS8](https://user-images.githubusercontent.com/119218812/229864328-a772c465-b317-49f6-b437-b7cdcab6966b.png)


### BARPLOT
![DS9](https://user-images.githubusercontent.com/119218812/229864346-64738ede-651a-4262-9ec4-290add5f5771.png)

![DS10](https://user-images.githubusercontent.com/119218812/229864366-48d94b3f-fee9-45c2-ba3d-bc4840c14b62.png)




### SEGMENTATION
![DS11](https://user-images.githubusercontent.com/119218812/229864484-c36f4533-f0ff-4540-a12d-e13116fe36cc.png)


### SUBPLOTS
![DS12](https://user-images.githubusercontent.com/119218812/229864506-89a90717-c194-4123-a6e3-6966fee79d21.png)


### CORRESSION
![DS13](https://user-images.githubusercontent.com/119218812/229864537-27cd3a5f-aae1-4833-b05f-9c8aed1360e1.png)


### HEATMAP()
![DS14](https://user-images.githubusercontent.com/119218812/229864569-d21dbd31-1c32-41bb-9d5a-d00e24434dd2.png)


## RESULT

Hence The Performance of the Multivariate EDA on the given data set is verified.

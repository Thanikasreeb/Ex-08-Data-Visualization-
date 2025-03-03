# Ex-08-Data-Visualization-

## AIM

To Perform Data Visualization on the given dataset and save the data to a file. 

# Explanation

Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# ALGORITHM

### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature generation and selection techniques to all the features of the data set
### STEP 4
Apply data visualization techniques to identify the patterns of the data.

# CODE
NAME:Thanika sree B
REGISTER NUMBER:212222100055
```
# DATA:

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
import seaborn as sbn
df=pd.read_csv("/content/Superstore.csv",encoding='windows-1252')
df.head()

# DATA CLEANING
df.info()

df.isnull().sum()

1.Which Segment has Highest sales?
sbn.barplot(x=df['Segment'],y=df['Sales'])
plt.title("Highest Sales of the segment")

2.Which City has Highest profit?
sbn.barplot(x=df['City'],y=df['Profit'])
plt.title("Highest Profit of cities")

City=df.loc[:,["City","Profit"]]
df.head(5)
City=City.groupby(by=["City"]).sum().sort_values(by="Profit")
plt.figure(figsize=(10,10))
sbn.barplot(x=City.index,y="Profit",data=City)
plt.xticks(rotation = 90)
plt.xlabel=("City")
plt.ylabel=("Profit")
plt.show()

3.Which ship mode is profitable?
sbn.barplot(x=df['Ship Mode'],y=df['Profit'])
plt.title("Profitable Ship Mode")

4.Sales of the product based on region.
sbn.barplot(x=df['Sales'], y=df['Region'])
plt.title("Sales of Product based on Region")

5.Find the relation between sales and profit.
sbn.lineplot(x=df['Sales'], y=df['Profit'])
plt.title("Relation between Sales and Profit")

6.Find the relation between sales and profit based on the following category. i) Segment ii)City iii)States iv)Segment and Ship Mode v)Segment, Ship mode and Region

## i) Segment
grouped_data = df.groupby('Segment')[['Sales', 'Profit']].mean()
# Create a bar chart of the grouped data
fig, ax = plt.subplots()
ax.bar(grouped_data.index, grouped_data['Sales'], label='Sales')
ax.bar(grouped_data.index, grouped_data['Profit'], bottom=grouped_data['Sales'], label='Profit')
ax.set_xlabel('Segment')
ax.set_ylabel('Value')
ax.legend()
plt.show()

## ii) City
grouped_data = df.groupby('City')[['Sales', 'Profit']].mean()
# Create a bar chart of the grouped data
fig, ax = plt.subplots()
ax.bar(grouped_data.index, grouped_data['Sales'], label='Sales')
ax.bar(grouped_data.index, grouped_data['Profit'], bottom=grouped_data['Sales'], label='Profit')
ax.set_xlabel('City')
ax.set_ylabel('Value')
ax.legend()
plt.show()

## iii) States
grouped_data = df.groupby('State')[['Sales', 'Profit']].mean()
# Create a bar chart of the grouped data
fig, ax = plt.subplots()
ax.bar(grouped_data.index, grouped_data['Sales'], label='Sales')
ax.bar(grouped_data.index, grouped_data['Profit'], bottom=grouped_data['Sales'], label='Profit')
ax.set_xlabel('State')
ax.set_ylabel('Value')
ax.legend()
plt.show()

## iv)Segment and Ship Mode
grouped_data = df.groupby(['Segment', 'Ship Mode'])[['Sales', 'Profit']].mean()
pivot_data = grouped_data.reset_index().pivot(index='Segment', columns='Ship Mode', values=['Sales', 'Profit'])
# Create a bar chart of the grouped data
fig, ax = plt.subplots()
pivot_data.plot(kind='bar', ax=ax)
ax.set_xlabel('Segment')
ax.set_ylabel('Value')
plt.legend(title='Ship Mode')
plt.show()

## v)Segment, Ship mode and Region
grouped_data = df.groupby(['Segment', 'Ship Mode','Region'])[['Sales', 'Profit']].mean()
pivot_data = grouped_data.reset_index().pivot(index=['Segment', 'Ship Mode'], columns='Region', values=['Sales', 'Profit'])
sns.set_style("whitegrid")
sns.set_palette("Set1")
pivot_data.plot(kind='bar', stacked=True, figsize=(10, 5))
plt.legend(title='Region')
plt.show()
```
# OUPUT:

![image](https://github.com/Thanikasreeb/Ex-08-Data-Visualization-/assets/119557910/2e3ed39b-dd70-422c-9c86-bb346be9ee3a)
![image](https://github.com/Thanikasreeb/Ex-08-Data-Visualization-/assets/119557910/752309f3-517c-43dc-9d30-136233bf41f7)

## data info :

![image](https://github.com/Thanikasreeb/Ex-08-Data-Visualization-/assets/119557910/c1eef725-cfbc-4338-a189-3692ab90959a)

## DATA SET:

![image](https://github.com/Thanikasreeb/Ex-08-Data-Visualization-/assets/119557910/f204d717-6a35-42e4-b0c7-7f43e2ad1ef7)
![image](https://github.com/Thanikasreeb/Ex-08-Data-Visualization-/assets/119557910/8e4533f6-42a3-4af7-bf5d-5f12a78ce42e)

![image](https://github.com/Thanikasreeb/Ex-08-Data-Visualization-/assets/119557910/76e1ffe8-169a-494a-b37e-8d430eda8696)
![image](https://github.com/Thanikasreeb/Ex-08-Data-Visualization-/assets/119557910/4f6b2354-2afe-4db4-9ee1-be18d041f9b5)
![image](https://github.com/Thanikasreeb/Ex-08-Data-Visualization-/assets/119557910/b1dbf67f-8890-4f3d-bd77-00e4cae44964)
![image](https://github.com/Thanikasreeb/Ex-08-Data-Visualization-/assets/119557910/9b644245-e907-4f2e-8aff-ab015ea2d21a)
![image](https://github.com/Thanikasreeb/Ex-08-Data-Visualization-/assets/119557910/25248d58-9f04-4ac3-97f2-5731487c8e0e)
![image](https://github.com/Thanikasreeb/Ex-08-Data-Visualization-/assets/119557910/fbf819f7-fe69-4893-b1f2-424ff3b76ab8)
![image](https://github.com/Thanikasreeb/Ex-08-Data-Visualization-/assets/119557910/65bc02ff-0fe2-454d-b757-592883f1463e)
![image](https://github.com/Thanikasreeb/Ex-08-Data-Visualization-/assets/119557910/aa3c47d6-e796-4f05-88e4-86673819d616)
![image](https://github.com/Thanikasreeb/Ex-08-Data-Visualization-/assets/119557910/25303bb7-8c0b-4991-8b6d-f2b0a4bee8d5)
![image](https://github.com/Thanikasreeb/Ex-08-Data-Visualization-/assets/119557910/b9713ba8-3434-41b7-9896-4dcabb6c9162)
![image](https://github.com/Thanikasreeb/Ex-08-Data-Visualization-/assets/119557910/a5aeef49-6e53-4ff7-aefc-35fd3977e9e8)

![image](https://github.com/Thanikasreeb/Ex-08-Data-Visualization-/assets/119557910/77d609ce-9ba2-4f7d-a629-5e290e1ff562)

![image](https://github.com/Thanikasreeb/Ex-08-Data-Visualization-/assets/119557910/6d4ceb36-4281-4ab2-8f4c-c2b8959b5ad2)

![image](https://github.com/Thanikasreeb/Ex-08-Data-Visualization-/assets/119557910/e3929888-be9b-4f57-9fca-080f025f7259)

![image](https://github.com/Thanikasreeb/Ex-08-Data-Visualization-/assets/119557910/329e4ced-96ef-4260-90aa-ff670b9d81e6)

![image](https://github.com/Thanikasreeb/Ex-08-Data-Visualization-/assets/119557910/a993fa5e-8f4d-4b6e-a468-aa6f6deec1ee)
![image](https://github.com/Thanikasreeb/Ex-08-Data-Visualization-/assets/119557910/5b61ba9a-f92b-4f9b-85d0-ee5f9f678a1e)
![image](https://github.com/Thanikasreeb/Ex-08-Data-Visualization-/assets/119557910/26ba686a-ba87-4712-be87-ace3870d725c)
![image](https://github.com/Thanikasreeb/Ex-08-Data-Visualization-/assets/119557910/f09d979f-3a89-44d4-ac4c-90a06965e282)
![image](https://github.com/Thanikasreeb/Ex-08-Data-Visualization-/assets/119557910/7faae9ef-a2b3-4fa6-aef0-2021a5d3052b)

## RESULT:

Hence the data visualization method for the given dataset applied successfully.





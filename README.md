# Ex-08-Data-Visualization-

## AIM
To Perform Data Visualization on the given dataset and save the data to a file. 

## EXPLANATION
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

## ALGORITHM

### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature generation and selection techniques to all the features of the data set
### STEP 4
Apply data visualization techniques to identify the patterns of the data.


## CODE
NAME: sivakumar A

REGISTER NUMBER:212220043004
```
# DATA
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

i) Segment
grouped_data = df.groupby('Segment')[['Sales', 'Profit']].mean()
# Create a bar chart of the grouped data
fig, ax = plt.subplots()
ax.bar(grouped_data.index, grouped_data['Sales'], label='Sales')
ax.bar(grouped_data.index, grouped_data['Profit'], bottom=grouped_data['Sales'], label='Profit')
ax.set_xlabel('Segment')
ax.set_ylabel('Value')
ax.legend()
plt.show()

ii) City
grouped_data = df.groupby('City')[['Sales', 'Profit']].mean()
# Create a bar chart of the grouped data
fig, ax = plt.subplots()
ax.bar(grouped_data.index, grouped_data['Sales'], label='Sales')
ax.bar(grouped_data.index, grouped_data['Profit'], bottom=grouped_data['Sales'], label='Profit')
ax.set_xlabel('City')
ax.set_ylabel('Value')
ax.legend()
plt.show()

iii) States
grouped_data = df.groupby('State')[['Sales', 'Profit']].mean()
# Create a bar chart of the grouped data
fig, ax = plt.subplots()
ax.bar(grouped_data.index, grouped_data['Sales'], label='Sales')
ax.bar(grouped_data.index, grouped_data['Profit'], bottom=grouped_data['Sales'], label='Profit')
ax.set_xlabel('State')
ax.set_ylabel('Value')
ax.legend()
plt.show()

iv)Segment and Ship Mode
grouped_data = df.groupby(['Segment', 'Ship Mode'])[['Sales', 'Profit']].mean()
pivot_data = grouped_data.reset_index().pivot(index='Segment', columns='Ship Mode', values=['Sales', 'Profit'])
# Create a bar chart of the grouped data
fig, ax = plt.subplots()
pivot_data.plot(kind='bar', ax=ax)
ax.set_xlabel('Segment')
ax.set_ylabel('Value')
plt.legend(title='Ship Mode')
plt.show()

v)Segment, Ship mode and Region
grouped_data = df.groupby(['Segment', 'Ship Mode','Region'])[['Sales', 'Profit']].mean()
pivot_data = grouped_data.reset_index().pivot(index=['Segment', 'Ship Mode'], columns='Region', values=['Sales', 'Profit'])
sns.set_style("whitegrid")
sns.set_palette("Set1")
pivot_data.plot(kind='bar', stacked=True, figsize=(10, 5))
plt.legend(title='Region')
plt.show()
```

## OUPUT
![image](https://github.com/Bmohamedathil/Ex-08-Data-Visualization-/assets/119560261/58408640-fb7c-45a1-be68-b03ef89b9f43)
![image](https://github.com/Bmohamedathil/Ex-08-Data-Visualization-/assets/119560261/cdd48e15-65ef-4b07-837c-094525ea07d5)
![image](https://github.com/Bmohamedathil/Ex-08-Data-Visualization-/assets/119560261/ca42de4b-4dea-4839-afca-1f0b0a0bb4a5)
![image](https://github.com/Bmohamedathil/Ex-08-Data-Visualization-/assets/119560261/254b8a67-a38e-41da-95ad-771e609bac94)
![image](https://github.com/Bmohamedathil/Ex-08-Data-Visualization-/assets/119560261/a85bec0e-1b76-42d5-9498-d2a55104051a)
![image](https://github.com/Bmohamedathil/Ex-08-Data-Visualization-/assets/119560261/6282ae34-d8e1-497a-8d27-6c44820dee32)
![image](https://github.com/Bmohamedathil/Ex-08-Data-Visualization-/assets/119560261/cbd44759-3c5e-46d9-bbf9-13090d262e70)
![image](https://github.com/Bmohamedathil/Ex-08-Data-Visualization-/assets/119560261/eabf04cf-7a79-40b5-b476-6e254d5b964c)
![image](https://github.com/Bmohamedathil/Ex-08-Data-Visualization-/assets/119560261/2c31140a-6902-46c3-a85b-ed3223a858d9)
![image](https://github.com/Bmohamedathil/Ex-08-Data-Visualization-/assets/119560261/2003e471-06c6-4f84-b9b5-60186a3a5a4b)
![image](https://github.com/Bmohamedathil/Ex-08-Data-Visualization-/assets/119560261/1b6b23c1-1d56-4b96-99bc-5b234b5e40de)
![image](https://github.com/Bmohamedathil/Ex-08-Data-Visualization-/assets/119560261/e8d566d1-0655-4f3c-a627-89e3e2d4b189)
![image](https://github.com/Bmohamedathil/Ex-08-Data-Visualization-/assets/119560261/1cbd0e1e-a22a-4d36-bc59-98a77bda61aa)
![image](https://github.com/Bmohamedathil/Ex-08-Data-Visualization-/assets/119560261/e6dcc866-4647-4496-9af2-76a77f67684b)
![image](https://github.com/Bmohamedathil/Ex-08-Data-Visualization-/assets/119560261/9e6b7e9f-2d3d-4241-b634-abae0be85a7f)
![image](https://github.com/Bmohamedathil/Ex-08-Data-Visualization-/assets/119560261/5e5fd531-b63c-4028-a92f-ed323ca8ae2e)

## RESULT:
Hence the data visualization method for the given dataset applied successfully.

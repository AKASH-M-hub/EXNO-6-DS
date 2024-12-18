# EXNO-6-DS-DATA VISUALIZATION USING SEABORN LIBRARY

# Aim:
  To Perform Data Visualization using seaborn python library for the given datas.

# EXPLANATION:
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# Algorithm:
STEP 1:Include the necessary Library.

STEP 2:Read the given Data.

STEP 3:Apply data visualization techniques to identify the patterns of the data.

STEP 4:Apply the various data visualization tools wherever necessary.

STEP 5:Include Necessary parameters in each functions.

# Coding and Output:

from google.colab import drive
drive.mount('/content/drive')

![image](https://github.com/user-attachments/assets/6d4fef4c-b105-4faf-8f77-9818171e8c84)

import seaborn as sns
!pip install matplotlib
import matplotlib.pyplot as plt

![image](https://github.com/user-attachments/assets/a18a24d3-2b5c-401d-9fea-161c28c8f317)

x=[1,2,3,4]
y=[2,4,6,8]
sns.lineplot(x=x,y=y)

![image](https://github.com/user-attachments/assets/9fa763ff-e740-4d7e-a897-590a0d8bb485)

df=sns.load_dataset("tips")
df

sns.lineplot(x="total_bill",y="tip",data=df,hue="sex",linestyle="solid",legend="auto")

![image](https://github.com/user-attachments/assets/67a66ee3-f2a5-4fb4-bffa-5146f9dbc517)

x=[1,2,3,4,5]
y1=[3,5,6,7,8]
y2=[1,4,3,4,5]
y3=[4,5,3,2,1]

sns.lineplot(x=x,y=y1)
sns.lineplot(x=x,y=y2)
sns.lineplot(x=x,y=y3)
plt.title("Multi_line plot")
plt.xlabel("X-label")
plt.ylabel("Y-label")

![image](https://github.com/user-attachments/assets/de891e2b-4c8b-4096-9017-3ce4bb663171)

import seaborn as sns
import matplotlib.pyplot as plt
#Load the tips dataset
tips =sns.load_dataset('tips')
#Calculate the average total bill and tip for each day of the week
avg_total_bill =tips.groupby('day') ['total_bill'].mean()
avg_tip =tips.groupby('day') ['tip'].mean()

![image](https://github.com/user-attachments/assets/639760c3-e456-4892-a863-c19b117d1edf)

plt.figure(figsize=(8, 6))
p1= plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill')
p2= plt.bar(avg_tip.index, avg_tip, bottom=avg_total_bill, label='Tip')
# Set the labels and title
plt.xlabel('Day of the Week')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Day')
plt.legend()

![image](https://github.com/user-attachments/assets/16473867-5d7c-4c5f-930b-86181deaa08d)

avg_total_bill =tips.groupby('time') ['total_bill'].mean()
avg_tip =tips.groupby('time') ['tip'].mean()
#Create a grouped bar chart
p1 = plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill', width=0.4)
p2 = plt.bar(avg_tip.index, avg_tip, bottom = avg_total_bill, label='Tip', width=0.4)
plt.xlabel('Time of Day')
plt.ylabel("Amount")
plt.title('Average Total Bill and Tip by Time of Day')
plt.legend()

![image](https://github.com/user-attachments/assets/4da884c9-8dc6-479c-978d-a3484bba84bd)

years =range (2000, 2012)
apples= [0.895, 0.91, 0.919, 0.926, 0.929, 0.931, 0.934, 0.936, 0.937, 0.9375, 0.9372, 0.939]
oranges = [0.962, 0.941, 0.930, 0.923, 0.918, 0.908, 0.907, 0.904, 0.901, 0.898, 0.9, 0.896,]
import seaborn as sns
dt= sns.load_dataset('tips')
#Bar plot with hue parameter
sns.barplot(x='day', y='total_bill', hue='sex', data=dt, palette='Set1')
#Set labels and title
plt.xlabel('Day of the week')
plt.ylabel('Total Bill')
plt.title('Total Bill by Day and Gender')

![image](https://github.com/user-attachments/assets/744abba5-0190-4137-8137-9bb7a5b01f0c)

import seaborn as sns
# Load the tips dataset
tips =sns.load_dataset('tips')
# Scatter plot of total bill vs. tip amount
sns.scatterplot(x='total_bill', y='tip', hue='sex',data=tips)
#Set labels and title
plt.xlabel('Total Bill')
plt.ylabel('Tip Amount')
plt.title('Scatter Plot of Total Bill vs. Tip Amount')

![image](https://github.com/user-attachments/assets/2e8edda1-788d-4fcf-88bb-4a115b39d27d)

import seaborn as sns
import numpy as np
import pandas as pd

np.random.seed (1)
num_var= np.random.randn(1000)
num_var = pd.Series (num_var, name = "Numerical variable")
num_var

![image](https://github.com/user-attachments/assets/b2ce6d20-e95b-43e1-b3b7-d61647e6fc16)

import seaborn as sns
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
np.random.seed(0)
marks = np.random.normal(loc=70, scale=10, size=100)
marks

![image](https://github.com/user-attachments/assets/ebf20158-e99a-4c18-95b9-28905e37ecfe)

sns.histplot(data=marks, bins=10, kde= True, stat='count', cumulative=False, multiple='stack', element='bars', palette='Set1', shrink=0.7)
plt.xlabel('Marks')
plt.ylabel('Density')
plt.title("Histogram of students Marks")

![image](https://github.com/user-attachments/assets/24a20ffd-3bf4-4fd4-a390-970e3f3ff393)

import seaborn as sns
import pandas as pd
tips =sns.load_dataset('tips')
sns.boxplot(x=tips['day'], y=tips['total_bill'], hue=tips['sex'])

![image](https://github.com/user-attachments/assets/a17d32c2-d7ae-4667-85cb-2ab986240680)

sns.boxplot(x="day", y="total_bill", hue="smoker", data =tips, linewidth=2, width=0.6, boxprops={"facecolor": "lightblue", "edgecolor": "darkblue"}, whiskerprops={"color": "black", "linestyle": "--", "linewidth": 1.5}, capprops={"color": "black", "linestyle": "--", "linewidth": 1.5})

![image](https://github.com/user-attachments/assets/bc2b2612-1d94-4682-b196-78d8247a982c)

sns.violinplot(x="day", y="total_bill", hue="smoker", data =tips, linewidth=2, width=0.6,
palette="Set3", inner ="quartile")
#Add labels and title
plt.xlabel("Day of the Week")
plt.ylabel("Total Bill")
plt.title("Violin Plot of Total Bill by Day and Smoker Status")

![image](https://github.com/user-attachments/assets/adad2e8f-c957-4166-995c-d3242df0d4bc)

import seaborn as sns
sns.set(style = 'whitegrid')
tip = sns.load_dataset('tips')
sns.violinplot(x = 'day', y ='tip', data = tip)

![image](https://github.com/user-attachments/assets/32f0c01d-10e5-457f-8b26-af52b4a3258e)

import seaborn as sns
# use to set style of background of plot
sns.set(style="whitegrid")
# loading data-set
tips = sns.load_dataset("tips")
sns.violinplot(x="tip", y="day", data=tip

![image](https://github.com/user-attachments/assets/3805ce71-7660-4b28-acaf-d436760f7b50)

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

data = np.random.randint(low = 1, high = 100, size = (10,10))
print("The data to be plotted: \n")
print(data)

![image](https://github.com/user-attachments/assets/604109c0-5382-406f-bb8d-ce5a8aec5bed)













# Result:
The abpve code is execueted successfully.

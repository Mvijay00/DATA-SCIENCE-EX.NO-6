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

# Coding And Ouput:
```
import seaborn as sns
import matplotlib.pyplot as plt
df=sns.load_dataset("tips")
df
```
![image](https://github.com/user-attachments/assets/f0e1175a-fa49-4203-98ad-70919b1cfb29)
```
sns.lineplot(x="total_bill",y="tip",data=df,hue="sex",linestyle='solid',legend="auto")
```
![image](https://github.com/user-attachments/assets/478889a9-02cf-4942-acb8-2f46fe9e399c)
```
avg_total_bill=df.groupby('day')['total_bill'].mean()
avg_tip=df.groupby('day')['tip'].mean()

plt.figure(figsize=(8,6))
p1=plt.bar(avg_total_bill.index, avg_total_bill, label='Total_bill')
p2=plt.bar(avg_tip.index, avg_tip, bottom=avg_total_bill ,label='Tip')

plt.xlabel('Day of the week')
plt.ylabel('Amount')
plt.title('Average Total Bill And Tip by day')
plt.legend()
```
![image](https://github.com/user-attachments/assets/ca5e03a3-5144-4f65-8b3c-21ab8f5a5863)
```
avg_total_bill =df.groupby('time')['total_bill'].mean()
avg_tip= df.groupby('time') ['tip'].mean()

p1= plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill', width=0.4)
p2=plt.bar(avg_tip.index, avg_tip, bottom = avg_total_bill, label='Tip', width=0.4) 
plt.xlabel('Time of Day')
plt.ylabel('Amount')

plt.title('Average Total Bill and Tip by Time of Day')

plt.legend()
```
![image](https://github.com/user-attachments/assets/e99b20b6-3567-4e56-970a-89b693b5fe3f)
```
import seaborn as sns
dt=sns.load_dataset('tips')
sns.barplot(x='day',y='total_bill',hue='sex',data=dt,palette='Set1')
plt.xlabel('Day of the week')
plt.ylabel('Total Bill')
plt.title('Total Bill by day and gender')
```
![image](https://github.com/user-attachments/assets/2127fa7b-98b9-4709-bed6-8c563f828139)
```
import seaborn as sns

df= sns.load_dataset('tips')

sns.scatterplot(x='total_bill', y='tip', hue='sex', data=df)

plt.xlabel('Total Bill')
plt.ylabel('Tip Amount')
plt.title('Scatter Plot of Total Bill vs. Tip Amount')
```
![image](https://github.com/user-attachments/assets/b490a5a2-8995-4a2c-bb4f-08ee742101ab)

```
sns.histplot(data=df,x='day',hue='time',kde=True)
```
![image](https://github.com/user-attachments/assets/91dd853d-9190-45d9-9f08-34ec8c52d55e)
```
sns.boxplot(x=df['day'],y=df['total_bill'],hue=df['sex'])
```
![image](https://github.com/user-attachments/assets/b7d6fd66-1e23-41a6-86e8-29eb4ed9b348)

```
sns.boxplot(x="day", y="total_bill", hue="smoker", data=df, linewidth=2, width=0.6,boxprops={'facecolor': 'pink', "edgecolor": 'darkgreen'},
          whiskerprops={"color": "black", "linestyle": "--", "linewidth": 1.5}, capprops={"color": "black", "linestyle": "--", "linewidth": 1.5})

```

![image](https://github.com/user-attachments/assets/f45fe22f-81c5-4aa8-b6d4-4860f76346e2)





# Result:
  The Perform Data Visualization using seaborn python library for the given datas is created

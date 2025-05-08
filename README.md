# EXNO-5-DS-DATA VISUALIZATION USING MATPLOT LIBRARY

# Aim:
  To Perform Data Visualization using matplot python library for the given datas.

# EXPLANATION:
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# Algorithm:
STEP 1:Include the necessary Library.

STEP 2:Read the given Data.

STEP 3:Apply data visualization techniques to identify the patterns of the data.

STEP 4:Apply the various data visualization tools wherever necessary.

STEP 5:Include Necessary parameters in each functions.

# Coding and Output:
``` py
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
```
``` py
x = [1, 2, 3, 4, 5]
y = [3, 6, 2, 7, 1]
```
``` py
plt.figure(figsize=(8, 5))
plt.plot(x, y, label='Line 1', marker='o', color='blue')
plt.xlabel('X Axis')
plt.ylabel('Y Axis')
plt.legend()
plt.title('Line Graph of X vs Y')
plt.show()
```
![image](https://github.com/user-attachments/assets/76333cb2-f820-47f7-b449-c12c22dce84a)
``` py
x1 = [1,2,3]
y1 = [2,4,1]
x2 = [1,2,3]
y2 = [4,1,3]
```
``` py
x1 = [1, 2, 3]
y1 = [2, 4, 1]
x2 = [1, 2, 3]
y2 = [4, 1, 3]
plt.figure(figsize=(8, 5))
plt.plot(x1, y1, label='Line 1', marker='o', color='blue')
plt.plot(x2, y2, label='Line 2', marker='s', color='green')
plt.xlabel('X Axis')
plt.ylabel('Y Axis')
plt.title('Line Graph of Line 1 and Line 2')
plt.legend()
plt.show()
```
![image](https://github.com/user-attachments/assets/71c7e122-ea80-4964-9497-8e7cab54f06a)
``` py

x1 = [1, 2, 3]
y1 = [2, 4, 1]
x2 = [1, 2, 3]
y2 = [4, 1, 3]
plt.figure(figsize=(8, 5))
plt.scatter(x1, y1, label='Line 1 Points', color='blue', marker='o')
plt.scatter(x2, y2, label='Line 2 Points', color='green', marker='s')
plt.xlabel('X Axis')
plt.ylabel('Y Axis')
plt.title('Scatter Plot of Line 1 and Line 2 Points')
plt.legend()
plt.show()
```
![image](https://github.com/user-attachments/assets/b9f50335-5091-4a8c-95b1-5c5cd86eede2)
``` py
x = [1, 2, 3, 4, 5]
y1 = [10, 12, 14, 16, 18]
y2 = [5, 7, 9, 11, 13]
y3 = [2, 4, 6, 8, 10]
```
``` py
x_values = [0,1,2,3,4,5]
y_values = [0,1,4,9,16,25]
```
``` py

x_values = [0, 1, 2, 3, 4, 5]
y_values = [0, 1, 4, 9, 16, 25]
plt.figure(figsize=(8, 5))
plt.plot(x_values, y_values, label='y = x^2', color='blue')
plt.fill_between(x_values, y_values, color='skyblue', alpha=0.4)
plt.xlabel('X Axis')
plt.ylabel('Y Axis')
plt.title('Line Graph with Fill Between (y = x² and x-axis)')
plt.legend()
plt.show()
```
![image](https://github.com/user-attachments/assets/f31f538b-e0fc-4c2a-ac15-839800fce380)
``` py
from scipy.interpolate import make_interp_spline
x = np.array([1, 2, 3, 4, 5, 6, 7, 8, 9, 10])
y = np.array([2, 4, 5, 7, 8, 8, 9, 10, 11, 12])
```
``` py
from scipy.interpolate import make_interp_spline
x = np.array([1, 2, 3, 4, 5, 6, 7, 8, 9, 10])
y = np.array([2, 4, 5, 7, 8, 8, 9, 10, 11, 12])
x_smooth = np.linspace(x.min(), x.max(), 300)
spl = make_interp_spline(x, y, k=3)
y_smooth = spl(x_smooth)
plt.plot(x, y, 'o', label='Original Data')
plt.plot(x_smooth, y_smooth, label='Cubic Spline')
plt.legend()
plt.xlabel("x")
plt.ylabel("y")
plt.title("Cubic Spline Interpolation")
plt.grid(True)
plt.show()
```
![image](https://github.com/user-attachments/assets/0ec56b62-83fc-451a-96e2-758e24f7a250)
``` py
values = [5, 6, 3, 7, 2]
names  = ["A", "B", "C", "D", "E"]
```
``` py
values = [5, 6, 3, 7, 2]
names = ["A", "B", "C", "D", "E"]
plt.bar(names, values, color='skyblue', edgecolor='black')
plt.xlabel('Names')
plt.ylabel('Values')
plt.title('Bar Graph Example')
plt.grid(axis='y', linestyle='--', alpha=0.7)
plt.show()
```
![image](https://github.com/user-attachments/assets/b9a65903-c60d-4544-9113-13a3da8c9f81)
`` py
c1 =['red', 'green']
c2 =['b', 'g']
```
``` py
names = ['Item 1', 'Item 2']
values = [10, 15]
c1 = ['red', 'green']
c2 = ['b', 'g']
plt.bar(names, values, color=c1, edgecolor='black')
plt.xlabel('Items')
plt.ylabel('Values')
plt.title('Bar Chart with Custom Colors')
plt.show()
```
![image](https://github.com/user-attachments/assets/ec12ca52-ad4e-43bf-b69f-38bbe78b1bf4)
``` py
df = sns.load_dataset("tips")
df
```
![image](https://github.com/user-attachments/assets/4ba68b00-0343-4a3c-b1f9-4b8b85a63c31)
``` py
df = sns.load_dataset("tips")

avg_total_bill = df.groupby("day")["total_bill"].mean()
avg_tip = df.groupby("day")["tip"].mean()

plt.figure(figsize=(8, 6))
p1 = plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill')
p2 = plt.bar(avg_tip.index, avg_tip, bottom=avg_total_bill, label='Tip')
plt.xlabel('Day of the Week')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Day')
plt.legend()
```
![image](https://github.com/user-attachments/assets/31de5e5b-f054-460e-ad33-7eef5e8f0556)
``` py
x_values = [0,1,2,3,4,5]
y_values = [0,1,4,9,16,25]
```
``` py
x_values = [0, 1, 2, 3, 4, 5]
y_values = [0, 1, 4, 9, 16, 25]
plt.scatter(x_values, y_values, color='blue', marker='o')
plt.xlabel('X Values')
plt.ylabel('Y Values')
plt.title('Scatter Plot of X vs Y')
plt.grid(True)
plt.show()
```
![image](https://github.com/user-attachments/assets/161b3b13-33a9-4de6-b3dd-0d39fb12cf5e)
``` py
# x-axis values
x = [1,2,3,4,5,6,7,8,9,10]
# y-axis values
y = [2,4,5,7,6,8,9,11,12,12]
```
``` py
x = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
y = [2, 4, 5, 7, 6, 8, 9, 11, 12, 12]
plt.scatter(x, y, label="stars", color="green", marker="*", s=30)
plt.xlabel('X Values')
plt.ylabel('Y Values')
plt.title('Scatter Plot of X vs Y')
plt.grid(True)
plt.show()

```
![image](https://github.com/user-attachments/assets/2f0e8d9c-afcc-4c0d-a891-b79935debc1a)
``` py
x = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
y = [2, 4, 5, 7, 6, 8, 9, 11, 12, 12]
plt.scatter(x, y, label="stars", color="green", marker="*", s=30)
plt.xlabel('X Values')
plt.ylabel('Y Values')
plt.title('Scatter Plot of X vs Y')
plt.legend()
plt.grid(True)
plt.show()
```
![image](https://github.com/user-attachments/assets/44f7ba60-2e30-4f05-b28b-e12f25e7a181)
``` py
x = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
y = [2, 4, 5, 7, 6, 8, 9, 11, 12, 12]
plt.scatter(x, y, label="stars", color="green", marker="*", s=30)
plt.xlabel('X Values')
plt.ylabel('Y Values')
plt.title('Scatter Plot of X vs Y')
plt.legend()
plt.grid(True)
plt.show()
```
![image](https://github.com/user-attachments/assets/7c81af29-86b0-4cd7-aa93-ebbd8d89e454)
``` py
# defining labels
activities = ['eat', 'sleep', 'work', 'play']
# portion covered by each label
slices = [3, 7, 8, 6]
# color for each label
colors = ['r', 'y', 'g', 'b']
```
``` py
plt.pie(slices, labels=activities, colors=colors, autopct='%1.1f%%', startangle=90)
plt.title('Activity Distribution')
plt.show()
```
![image](https://github.com/user-attachments/assets/ebb1febe-6a04-413d-bf6e-c47302af3917)



# Result:
Thus the program is executed successfully.

# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the necessary packages using import statement.
2. Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().
3. Import KMeans and use for loop to cluster the data.
4. Predict the cluster and plot data graphs.
5. Print the outputs and end the program

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: ROSHINI S
RegisterNumber:  212223240142
*/
```
```

import pandas as pd
import matplotlib.pyplot as plt

data = pd.read_csv('Mall_Customers.csv')

data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans
wcss = [] #Within-Cluster Sum of Square.
#It is the sum of squared distance between each point & the centroid in a cluster

for i in range(1,11):
    kmeans = KMeans(n_clusters = i, init = "k-means++")
    kmeans.fit(data.iloc[:, 3:])
    wcss.append(kmeans.inertia_)

plt.plot(range(1,11), wcss)
plt.xlabel("Number of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

km = KMeans(n_clusters = 5)
km.fit(data.iloc[:, 3:])
KMeans(n_clusters = 5)

y_pred = km.predict(data.iloc[:, 3:])
y_pred

data["cluster"] = y_pred
df0 = data[data["cluster"] == 0]
df1 = data[data["cluster"] == 1]
df2 = data[data["cluster"] == 2]
df3 = data[data["cluster"] == 3]
df4 = data[data["cluster"] == 4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```


## Output:
## Dataset:
![image](https://github.com/user-attachments/assets/86680613-0ec7-44a1-afb9-63ff7e1dc1bb)

## Dataset Information:
![image](https://github.com/user-attachments/assets/b6a14714-085c-4193-bc42-6cc95fe02883)
![image](https://github.com/user-attachments/assets/e8fd04ff-6f0d-4986-bdc0-2b2d7b53f3c9)

## Elbow Method Graph(wcss vs each iteration):
![image](https://github.com/user-attachments/assets/648a9232-3bc2-48ac-ba3b-586af27a1f6a)
![image](https://github.com/user-attachments/assets/243bcd44-dc36-476c-ad4a-14bc3855d473)
## Clustering representing customer segments-graph:
![image](https://github.com/user-attachments/assets/f93f150a-90d3-4360-8d5a-9285dc0496af)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.

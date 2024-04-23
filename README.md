# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm:

1.Import the necessary packages using import statement.

2.Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().

3.Import KMeans and use for loop to cluster the data.

4.Predict the cluster and plot data graphs.

5.Print the outputs and end the program

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: A. Kamal raj 
RegisterNumber:  212223040082
*/
```
```
import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("Mall_Customers.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss = []
for i in range(1,11):
  kmeans = KMeans (n_clusters = i, init ="k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("no of cluster")
plt.ylabel("wcss")
plt.title("Elbow Metthod")
km=KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])
y_pred = km.predict(data.iloc[:,3:])
y_pred
data["cluster"]=y_pred
df0=data[data["cluster"]==0]
df1=data[data["cluster"]==1]
df2=data[data["cluster"]==2]
df3=data[data["cluster"]==3]
df4=data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="pink",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="green",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="blue",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="black",label="cluster4")
plt.legend()
plt.title("Customer Segments")

```
## Output:
# Dataset:
![WhatsApp Image 2024-04-23 at 09 18 07_3a2a4547](https://github.com/Kamal-Raj-A/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/145742556/8822daa7-4b37-4e99-afc1-73b3add10050)
# Dataset information:
![WhatsApp Image 2024-04-23 at 09 18 07_61195ad9](https://github.com/Kamal-Raj-A/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/145742556/49ce1d48-7620-4980-a8c2-44a19e1fdcdb)

![WhatsApp Image 2024-04-23 at 09 18 06_ca8fdaf6](https://github.com/Kamal-Raj-A/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/145742556/d27973f4-20e5-4140-9a22-4bf7c103b2d2)

# Elbow method graph (wcss vs each iteration):
![WhatsApp Image 2024-04-23 at 09 18 07_8ababdd7](https://github.com/Kamal-Raj-A/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/145742556/c4034df5-6576-4d46-8ad0-0a5d9a257a36)

# Cluster represnting customer segments-graph:
![WhatsApp Image 2024-04-23 at 09 18 06_b938a441](https://github.com/Kamal-Raj-A/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/145742556/0909cd06-5c65-4db2-92d4-e87258bfe770)



## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.

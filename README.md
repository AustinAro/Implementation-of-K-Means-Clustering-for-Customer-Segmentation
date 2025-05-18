# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm

1. Import the necessary packages using import statement.

2.Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().

3. Import KMeans and use for loop to cluster the data.

4. Predict the cluster and plot data graphs.

5. Print the outputs and end the program.
## Program:

```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Austin Aro A
RegisterNumber:  212224040038
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

![Screenshot 2025-05-18 143308](https://github.com/user-attachments/assets/0c126bac-676e-4d24-b56d-d574a3527473)

![Screenshot 2025-05-18 143315](https://github.com/user-attachments/assets/9742b73e-708b-4145-bc9d-f28ea8c6b8ec)

![Screenshot 2025-05-18 143326](https://github.com/user-attachments/assets/569c98d3-bd8d-4e26-ad97-6e9b041e6556)

![Screenshot 2025-05-18 143338](https://github.com/user-attachments/assets/a135ac4a-2908-4419-8f49-9e9e95857557)

![Screenshot 2025-05-18 143348](https://github.com/user-attachments/assets/f72ba3d0-b801-4475-a222-28e1bad984a2)

![Screenshot 2025-05-18 143406](https://github.com/user-attachments/assets/1d5c8dca-a805-4129-86e5-ee77448d2b18)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.

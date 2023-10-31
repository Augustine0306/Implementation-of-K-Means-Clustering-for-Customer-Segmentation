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
5. Print the output and end the program.

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: AUGUSTINE J
RegisterNumber:  212222240015
*/
```
```python
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("/content/Mall_Customers (1) (1).csv")
```
```python
data.head()
```
```python
data.info()
```
```pyton
data.info()
```
```python
data.isnull().sum()
```
```pyhton
from sklearn.cluster import KMeans
wcss = []
```
```python
for i in range(1,11):
  kmeans = KMeans(n_clusters = i,init="k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)
```
```python
plt.plot(range(1,11),wcss)
plt.xlabel("No . of clusters")
plt.ylabel("wcss")
plt.title("Elbow method")
```
```python
km=KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])
```
```python
y_pred = km.predict(data.iloc[:,3:])
y_pred
```
```python
data["cluster"] = y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer Segments   ")
```
## Output:
![image](https://github.com/Augustine0306/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119404460/b165b2f3-80eb-47d8-8bc0-5251f9ed0c59)

![image](https://github.com/Augustine0306/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119404460/15062a68-f83f-4d3d-9ecc-2ebd0c68fe90)

![image](https://github.com/Augustine0306/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119404460/9918bd12-b6a2-4aa9-aa63-f8bdc4fcb4eb)

![image](https://github.com/Augustine0306/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119404460/9e829f94-5df1-4d70-9421-d33070f71dba)

![image](https://github.com/Augustine0306/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119404460/b53b16ab-46f4-4d6b-911b-71f5d8d2f215)

![image](https://github.com/Augustine0306/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119404460/ceabac79-2b27-45ad-bb96-f3000bacb7f2)

![image](https://github.com/Augustine0306/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119404460/44919dbf-4a5c-4be8-9322-356c1247edb6)

![image](https://github.com/Augustine0306/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119404460/9b4bab87-1f63-4264-84e7-e23be78f7a75)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.

# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import the necessary python packages using import statements.

2.Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().

3.Import KMeans and use for loop to cluster the data.

4.Predict the cluster and plot data graphs.

5.Print all the outputs.

## Program:
```py
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Sarankumar J
RegisterNumber: 212221230087


import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("/content/Mall_Customers (1).csv")

data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans
wcss=[]

for i in range(1,11):
   kmeans=KMeans(n_clusters=i,init="k-means++")
   kmeans.fit(data.iloc[:,3:])
   wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.xlabel("No.of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

km=KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])

y_pred=km.predict(data.iloc[:,3:])
y_pred

data["cluster"]=y_pred
df0=data[data["cluster"]==0]
df1=data[data["cluster"]==1]
df2=data[data["cluster"]==2]
df3=data[data["cluster"]==3]
df4=data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0");
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1");
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2");
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3");
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4");
plt.legend()
plt.title("Customer Segments")

```

## Output:
![image](https://user-images.githubusercontent.com/94778101/201476265-3e00421a-ad91-4b6e-af4c-ff54fe374c11.png)

![image](https://user-images.githubusercontent.com/94778101/201476275-6d615895-8483-4202-8721-76d82eca0140.png)

![image](https://user-images.githubusercontent.com/94778101/201476287-738c467c-293c-4966-9921-01b621fb59fa.png)

![image](https://user-images.githubusercontent.com/94778101/201476299-0550c04c-3ac6-46c0-a453-3e53b4eeb18d.png)

![image](https://user-images.githubusercontent.com/94778101/201476307-8471218d-ffc9-4d54-acb6-8755d252b89b.png)

![image](https://user-images.githubusercontent.com/94778101/201476329-86517315-e31d-43d0-9c06-a640df397e2e.png)

![image](https://user-images.githubusercontent.com/94778101/201476335-18229f39-7300-49e3-9e55-d7997e03693a.png)



## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.

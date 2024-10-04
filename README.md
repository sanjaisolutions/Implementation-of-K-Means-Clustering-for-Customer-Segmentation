# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the necessary packages using import statement.

2.Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().

3.Import KMeans and use for loop to cluster the data.

4.Predict the cluster and plot data graphs.

5.Print the outputs and end the program


## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: SANJAI.R
RegisterNumber:  212223040180
*/
```
```py
import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("Mall_Customers.csv")
data.head()
data.info()
null=data.isnull().sum()
null
from sklearn.cluster import KMeans
wcss=[]
for i in range(1,11):
    kmeans=KMeans(n_clusters=i,init="k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("No. of clusters")
plt.ylabel("wcss")
plt.title("elbow method")
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
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```


## Output:
![Screenshot 2024-10-04 144219](https://github.com/user-attachments/assets/81820c99-630a-45cf-a1ed-c859ccce6e80)
![Screenshot 2024-10-04 144224](https://github.com/user-attachments/assets/e7c69d57-bcdb-4e53-8806-af937a922495)
![Screenshot 2024-10-04 144228](https://github.com/user-attachments/assets/ef2de72d-8d3b-4db3-93ad-07f2f7af9000)
![Screenshot 2024-10-04 144239](https://github.com/user-attachments/assets/c057cf0a-0d86-476e-ab49-6ba7f6c8bcd2)
![Screenshot 2024-10-04 144246](https://github.com/user-attachments/assets/943c8117-cbb1-4d89-999a-f80a67807ea6)
![Screenshot 2024-10-04 144251](https://github.com/user-attachments/assets/292fcf5f-0d1d-43da-b05a-392e657ceb87)
![Screenshot 2024-10-04 144256](https://github.com/user-attachments/assets/e2080c39-adba-4bc5-9bee-dffe061f46ab)



## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.

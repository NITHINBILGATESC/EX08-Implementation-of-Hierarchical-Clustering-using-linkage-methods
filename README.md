# EX8-Implementation of Hierarchical Clustering using linkage methods
## DATE:
## AIM:
To implement Hierarchical Clustering using single and complete linkage method

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
Each data point starts in its own cluster, and pairs of clusters are merged as one moves up the hierarchy.
All data points start in one cluster, and splits are performed recursively as one moves down the hierarchy.
## Program:
```
/*
Program to implement Hierarchical Clustering using single and complete linkage method
Developed by: NITHIN BILGATES C
RegisterNumber:2305001022  
*/
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from scipy.cluster.hierarchy import dendrogram, linkage,fcluster
from sklearn.preprocessing import StandardScaler
df = pd.read_csv("/content/Hclus_EX8.csv")
df.head()
x = df[['StudentID','Marks']].values
x
z=linkage(x,method='complete')
plt.figure(figsize=(5,2))
plt.title("Dendogram for student segmentation")
labels=range(1,len(df)+1)
dendrogram(z,labels=labels)
plt.xlabel("Student ID")
plt.ylabel("Marks")
plt.show()
max_cluster=2
clusters=fcluster(z,max_cluster,criterion='maxclust')
clusters
plt.figure(figsize=(5,2))
plt.scatter(x[:,0],x[:,1],c=clusters,cmap='rainbow',s=100)
plt.title("Student segmented(Hierarchical clustering)")
plt.xlabel("Student ID")
plt.ylabel("Marks")
plt.show()
z=linkage(x,method='single')
plt.figure(figsize=(5,2))
plt.title("Dendogram for student segmentation")
labels=range(1,len(df)+1)
dendrogram(z,labels=labels)
plt.xlabel("Student ID")
plt.ylabel("Marks")
plt.show()
## Output:
![image](https://github.com/user-attachments/assets/adaece79-9d9e-48ef-bc52-9b06a3631414)
![image](https://github.com/user-attachments/assets/5c79ada8-5def-44bf-a94b-cb4c127a3303)
![image](https://github.com/user-attachments/assets/9af99c7d-9db3-45fa-b0e1-e5c2d728efb3)
![image](https://github.com/user-attachments/assets/ec8e6c37-ed51-4684-aad0-f7c7a320c5d3)
![image](https://github.com/user-attachments/assets/317096d0-748e-4963-90ae-cded14b741bd)
![image](https://github.com/user-attachments/assets/e65f94f5-a681-42eb-a8e2-b6b46b3e7131)








## Result:
Thus the implementation of Hierarchical Clustering using single and complete linkage method in python programming and verified successfully.

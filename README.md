# EX8-Implementation of Hierarchical Clustering using linkage methods
## DATE:
## AIM:
To implement Hierarchical Clustering using single and complete linkage method

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
step1:Ensure your data is organized properly. Each row represents a data point, and each
column represents a feature.
step2: Use one of the linkage methods (e.g., single, complete, average, or ward) to calculate
the distance between clusters and generate the linkage matrix.
step3: A dendrogram helps visualize the hierarchical structure and merge process of clusters.
step4 : Decide the number of clusters by cutting the dendrogram at a certain height or by
specifying a maximum distance. This step gives the final cluster assignments.

## Program:
```
/*
Program to implement Hierarchical Clustering using single and complete linkage method
Developed by: NITHIN BILGATES C
RegisterNumber:  2305001022
*/
```import pandas as pd
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
```
## Output:
![image](https://github.com/user-attachments/assets/7636fd0a-79d8-408d-b245-d99b9869cc6f)
![image](https://github.com/user-attachments/assets/587925d6-eb9f-4d51-8fae-14b11568e24e)
![Screenshot 2024-10-17 143956](https://github.com/user-attachments/assets/3ba3bc0e-7ee0-411b-8b76-139684cc9869)
![image](https://github.com/user-attachments/assets/793afb89-29f5-46d1-99c7-a92baf37aa74)
![image](https://github.com/user-attachments/assets/12df477f-e211-4504-b35a-d2b90d9275c9)
![image](https://github.com/user-attachments/assets/2809fff6-880d-4aab-af27-24b6e8e62113)




## Result:
Thus the implementation of Hierarchical Clustering using single and complete linkage method in python programming and verified successfully.

# Exp 4 Elbow Method using K-Means Clustering

### Nandavelan SPS (212223060182)

## AIM:
To implement the Elbow Method using K-Means Clustering in Python to determine the optimal number of clusters for customers based on their Annual Income and Spending Score by plotting WCSS against different values of K.

## DESIGN STEPS:

### Step 1:
Clone the repository from GitHub.

### Step 2:
Create a Python project in the preferred IDE (VS Code/PyCharm/Jupyter Notebook).

### Step 3:
Create the Python program for implementing the Elbow Method using the Scikit-learn library.

### Step 4:
Load the customer dataset and select the features **Annual Income** and **Spending Score**.

### Step 5:
Run the K-Means algorithm for different values of **K** (number of clusters).

### Step 6:
Calculate the **Within-Cluster Sum of Squares (WCSS)** for each value of **K**.

### Step 7:
Plot the WCSS values against the corresponding values of **K** to identify the optimal number of clusters using the Elbow Method.

### Step 8:
Execute the program and analyze the elbow point in the graph.

## PROGRAM:

``` python
# Elbow Method
# Royce Niran George A (212223060231)

# Step 1: Import libraries
import pandas as pd
import matplotlib.pyplot as plt
from sklearn.cluster import KMeans

# Step 2: Load dataset
data = pd.read_csv("/Users/dhana/Documents/BDA/Even 25-26 T1/Lab/customers_large_dataset.csv")

# Step 3: Select numeric columns (important)
X = data[["AnnualIncome", "SpendingScore"]]
# Step 4: Calculate WCSS for different K values
wcss = []   # empty list to store values

for k in range(1, 11):   # trying K from 1 to 10
    kmeans = KMeans(n_clusters=k, random_state=42)
    kmeans.fit(X)
    wcss.append(kmeans.inertia_)   # inertia_ gives WCSS
# Step 5: Plot the Elbow Graph
plt.figure()
plt.plot(range(1, 11), wcss)
plt.xlabel("Number of Clusters (K)")
plt.ylabel("WCSS")
plt.title("Elbow Method")
plt.show()

```

## OUTPUT:

<img width="667" height="387" alt="image" src="https://github.com/user-attachments/assets/8fe32914-a5e4-4e5a-a285-d3517cb2ed02" />

## RESULT:

The Elbow Method using K-Means Clustering was implemented successfully. The optimal number of clusters was determined by analyzing the WCSS plot and identifying the elbow point, which can be used for effective customer segmentation based on Annual Income and Spending Score.

# Customer_Segmentation_Clustering

### Customer Segmentation using Clustering

Segmenting mall customers into meaningful groups using unsupervised Machine Learning — built as a Data Mining course project


### Project Overview
This project applies unsupervised learning to segment mall customers based on their Annual Income and Spending Score. The goal is to identify distinct customer groups that can be targeted with different marketing strategies.
Two clustering algorithms are implemented and compared: K-Means and Agglomerative (Hierarchical) Clustering.

### Dataset

Source: Mall Customers Dataset (Mall_Customers.csv)
Samples: 200 customers
Features used for clustering:

Annual Income (k$) — customer's annual income in thousands
Spending Score (1-100) — score assigned by the mall based on spending behavior


Other columns available: CustomerID, Gender, Age
Missing values: None


### Pipeline
Load Data → EDA → Select Features → Find Optimal K → Apply Clustering → Visualize → Compare

### Part A — K-Means Clustering
Finding Optimal K
Two methods were used to determine the best number of clusters:

Elbow Method — plots inertia (WCSS) for K = 1 to 10; the curve bends at K = 5
Silhouette Method — computes silhouette score for K = 2 to 10; best score also at K = 5
Both methods agree: optimal K = 5

Training

Algorithm: KMeans with k-means++ initialization
n_init=10, random_state=42
Fitted on Annual Income and Spending Score

Visualizations

Scatter plot: Spending Score vs Age, colored by cluster
Scatter plot: Spending Score vs Annual Income, colored by cluster with centroids marked


### Part B — Agglomerative (Hierarchical) Clustering
Finding Optimal K

A Dendrogram was built using Ward linkage
A horizontal cut at distance ~200 produces 5 branches → 5 clusters
K = 5 chosen to stay consistent with K-Means for a fair comparison

Training

Algorithm: AgglomerativeClustering with linkage='ward', n_clusters=5

Visualizations

Scatter plot: Spending Score vs Age, colored by cluster
Scatter plot: Spending Score vs Annual Income, colored by cluster


### Part C — Comparison
Both algorithms are compared using the Silhouette Score — a metric that measures how well-separated the clusters are (higher is better):

K-Means Silhouette Score vs Agglomerative Silhouette Score are printed side by side
The algorithm with the higher score is declared the winner for this dataset

### Project Structure
├── Customer_Segmentation_Clustering.ipynb   # Full clustering pipeline notebook
├── Mall_Customers.csv                       # Dataset

# Customer Segmentation using Clustering (K-Means & DBSCAN)

## Overview

This project applies unsupervised machine learning techniques to segment customers based on their annual income and spending behavior. The goal is to identify distinct customer groups that can support data-driven marketing strategies.

Two clustering algorithms were explored:

* K-Means
* DBSCAN

---

##  Dataset

* Source: Kaggle – Mall Customer Segmentation Dataset
* Features used:

  * Annual Income (k$)
  * Spending Score (1–100)

The dataset contains information about customers' demographics and purchasing behavior.

---

## 🧠 Methodology


### 1. Data Understanding

* No missing or duplicate values were identified.
* Exploratory analysis was performed using **ydata-profiling**.
* Correlation analysis showed that Annual Income and Spending Score are nearly independent (correlation = 0.008), making them suitable for clustering.
* The low correlation between features suggests that each variable contributes unique information, supporting effective segmentation.


### 2. Data Preprocessing

* Removed non-informative columns (e.g., CustomerID)
* Selected relevant features for clustering
* Applied feature scaling to ensure fair distance computation

### 3. Clustering Algorithms

#### 🔹 K-Means

* Used to identify well-defined customer segments
* Optimal number of clusters determined using the Elbow Method
* Evaluated using Silhouette Score

#### 🔹 DBSCAN

* Used to explore density-based clustering
* Identified potential outliers (noise points)
* Compared against K-Means performance

---

## Results

### K-Means

* Number of clusters: 5
* Silhouette Score: **0.55**
* Produced clear and well-separated clusters

### DBSCAN

* Silhouette Score: **0.42**
* Identified outliers effectively
* Less effective in overall cluster separation for this dataset

---

## Visualizations

* Customer segmentation scatter plots
* Cluster centroids (K-Means)
* DBSCAN clustering with highlighted outliers

---

## Insights

The clustering analysis revealed distinct customer segments:

* High income & high spending → Premium customers
* High income & low spending → Potential growth segment
* Low income & high spending → Impulsive buyers
* Low income & low spending → Low-value customers
* Mid income & mid spending → Standard customers

---

## Model Comparison

| Model   | Strengths                         | Limitations                                |
| ------- | --------------------------------- | ------------------------------------------ |
| K-Means | Clear clusters, easy to interpret | Requires number of clusters                |
| DBSCAN  | Detects outliers, no need for K   | Sensitive to parameters, weaker separation |

K-Means performed better due to the roughly spherical structure of the data.

---

## Conclusion

K-Means proved to be the most suitable algorithm for this dataset, providing clear and actionable customer segments. DBSCAN was useful for identifying outliers but less effective for global clustering.

This project highlights the importance of selecting the appropriate clustering algorithm based on the structure of the data.

---

## Technologies Used

* Python
* pandas
* numpy
* scikit-learn
* matplotlib
* seaborn
* Jupyter Notebook
* ydata-profilling

---

## Project Structure

```
customer-segmentation-clustering/
│
├── data/
├── notebooks/
│   └── clustering_analysis.ipynb
├── requirements.txt
└── README.md
```

---

## Future Improvements

* Include additional features (e.g., Age)
* Apply dimensionality reduction (PCA)
* Test other clustering algorithms (Hierarchical Clustering)
* Use real-world datasets with more complexity

---


# Customer Segmentation using Clustering (K-Means & DBSCAN & HDBSCAN)

## Overview

This project applies unsupervised machine learning techniques to segment customers based on their annual income and spending behavior. The goal is to identify distinct customer groups that can support data-driven marketing strategies.

Three clustering algorithms were explored:

* K-Means
* DBSCAN
* HDBSCAN

---

##  Dataset

* Source: Kaggle – Mall Customer Segmentation Dataset
* Features used:

  * Annual Income (k$)
  * Spending Score (1–100)

The dataset contains information about customers' demographics and purchasing behavior.

---

## Methodology


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
* Does not require specifying the number of clusters
* Identifies outliers (noise points)
* Sensitive to parameter selection (eps, min_samples)

#### 🔹 HDBSCAN

* Extension of DBSCAN that handles variable density clusters
* Automatically determines the number of clusters
* More robust to parameter tuning compared to DBSCAN
* Better suited for real-world data with uneven density

---

## Results

### K-Means

* Number of clusters: 5
* Silhouette Score: **0.55**
* Produced clear and well-separated clusters

### DBSCAN

* Silhouette Score: **0.44**
* Identified outliers effectively
* Lower overall cluster separation compared to K-Means

### HDBSCAN

* Silhouette Score for HDBSCAN: **0.38**
* Identified meaningful clusters and outliers
* More robust than DBSCAN in handling variable density clusters
* Produced lower separation compared to K-Means, but demonstrated robustness in handling variable density

---

## Visualizations

* Elbow Method for K-Means
* Customer segmentation scatter plots
* Cluster centroids (K-Means)
* DBSCAN clustering with highlighted outliers
* HDBSCAN clustering with automatic cluster detection and outliers

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
| HDBSCAN | Handles variable density, no need for K | Slightly more complex        |

K-Means performed better due to the roughly spherical structure of the data, while HDBSCAN provided a more flexible and robust alternative, particularly for handling clusters with varying density.

---

## Conclusion

K-Means proved to be the most suitable algorithm for this dataset, providing clear and actionable customer segments. DBSCAN and HDBSCAN added value by identifying outliers and demonstrating how density-based methods behave differently from centroid-based approaches.
Although HDBSCAN achieved a lower silhouette score, it demonstrated greater robustness in handling clusters with varying density, making it more suitable for real-world scenarios where cluster structures are not well-defined.

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
* ydata-profiling
* hdbscan

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


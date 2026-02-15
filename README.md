# Wine Dataset Clustering: K-Means vs K-Medoids

## Overview
In this lab, we explored **clustering** using the **Wine Dataset** from the `sklearn` Python library. We applied two clustering methods:

- **K-Means**
- **K-Medoids** (implemented using **manual PAM** in Google Colab)

We compared the clustering quality using:
- **Silhouette Score** (how well-separated the clusters are)
- **Adjusted Rand Index (ARI)** (how well the clusters match the real Wine classes)

We also visualized the clusters using **PCA (2D)** and marked the **centroids/medoids**.

---

## Dataset
- **Source:** `sklearn.datasets.load_wine`
- **Classes:** 3 (so we used **k = 3** for both algorithms)
- **Features:** 13 numeric features

---

## What We Did (Lab Steps)

### Step 1: Load and Prepare the Dataset
- Loaded the Wine dataset from `sklearn`.
- Checked feature names, dataset shape, and class distribution.
- Standardized the features using **z-score normalization** (`StandardScaler`) because clustering is distance-based.

### Step 2: K-Means Clustering (k = 3)
- Trained **K-Means** with `k = 3`.
- Computed:
  - Silhouette Score
  - ARI

### Step 3: K-Medoids Clustering (k = 3)
- Trained **K-Medoids** with `k = 3`.
- Computed the same metrics:
  - Silhouette Score
  - ARI

> Note: In Colab, `scikit-learn-extra` failed due to NumPy 2.x compatibility, so K-Medoids was implemented using a manual **PAM** approach.

### Step 4: Visualize and Compare Results
- Reduced the scaled data to **2D using PCA**.
- Created **side-by-side scatter plots**:
  - K-Means clusters + centroid markers
  - K-Medoids clusters + medoid markers
- Wrote a brief comparison of cluster separation and when to prefer each method.

---

## Results

### K-Medoids (Manual PAM)
- **Silhouette Score:** 0.1548  
- **ARI:** 0.3413  

Interpretation (simple):
- The Silhouette Score is **low**, which means the clusters are **not very clearly separated**.
- The ARI shows the clustering matches the true labels **somewhat**, but not perfectly.

### K-Means
- **Silhouette Score:** *(fill in from your notebook output)*  
- **ARI:** *(fill in from your notebook output)*  

> In our PCA plots, K-Means looked more clearly separated than K-Medoids, with less mixing between clusters.

---

## When to Use Which Method?
- **K-Means** is usually a good choice when clusters are fairly clean and roughly round, and you want a fast method.
- **K-Medoids** is often better when there are **outliers or noisy points**, because it uses real data points as cluster centers (medoids).

---

## How to Run (Google Colab or Jupyter)

### Install / Import Requirements
Most are already available in Colab. If needed:

```bash
pip install numpy pandas matplotlib scikit-learn
```

### Run the Notebook
1. Open the notebook in Colab/Jupyter.
2. Run cells in order:
   - Load + standardize
   - K-Means + metrics
   - K-Medoids (manual PAM) + metrics
   - PCA plots + comparison

---

## Files
- `Wine_Clustering_KMeans_KMedoids.ipynb` *(your notebook name)*
- `README.md`

---

## Notes (Colab Compatibility)
`scikit-learn-extra` did not work in this Colab setup because it was compiled for NumPy 1.x, while Colab uses NumPy 2.x.  
To avoid downgrading NumPy, we used a manual **PAM** implementation for K-Medoids.

---

## Author
Sai Venkata Bharath Reddy Singareddy - MSCS 634

# Breast Cancer Clustering 

## Project Overview

This project implements an **unsupervised clustering analysis** on the **Wisconsin Breast Cancer Dataset**. The goal is to explore patterns in the dataset, reduce dimensionality using PCA, 
and perform clustering using **K-Means** and **DBSCAN**. The app provides interactive visualizations and evaluates cluster quality using **Silhouette Score** and **Adjusted Rand Index (ARI)**.

## Dataset Description

* **Dataset:** Wisconsin Breast Cancer Dataset (Diagnostic)
* **Format:** .data file (comma-separated values without header)
* **Number of Instances:** 569
* **Number of Features:** 32 (ID, Diagnosis, and 30 real-valued features)
* **Target Column:** Diagnosis(Malignant = M, Benign = B)

**Features include:**

* Mean, standard error (SE), and worst measurements of:
  `radius`, `texture`, `perimeter`, `area`, `smoothness`, `compactness`, `concavity`, `concave points`, `symmetry`, `fractal dimension`.

## Data Preprocessing Steps
1. **Load Data:** Read `.data` file and assign proper column names.
2. **Mapping Diagnosis:** Convert `M → 1` and `B → 0`.
3. **Power Transformation:** Apply **Yeo-Johnson** transformation to reduce skewness.
4. **Outlier Capping:** Clip extreme values using **IQR** method.
5. **Standard Scaling:** Standardize all features to zero mean and unit variance.
6. **Dimensionality Reduction:** Apply **PCA** to reduce features to 2 components for visualization.

## Model Development

### K-Means Clustering
* Number of clusters (`k`) is adjustable by the user.
* Performs clustering on **PCA-transformed data**.

### DBSCAN Clustering
* Density-based clustering with adjustable **eps** and **min_samples**.
* Works on scaled feature data to detect core and noise points.

## Evaluation
* **Silhouette Score:** Measures cluster cohesion and separation.
* **Adjusted Rand Index (ARI):** Compares predicted clusters to true Diagnosis labels.

## Results & Insights

* **K-Means (k=2)** typically produces well-separated clusters with high Silhouette Score.
* **DBSCAN (eps=1.7, min_samples=3)** identifies core clusters while marking noise points.
* Outlier capping and power transformation improve clustering stability and silhouette score.

## How to Run

1. Clone the repository:
- git clone <repo>
- cd <repo>
2. Install dependencies:
- pip install -r requirements.txt
3. Run the Streamlit app:
- streamlit run app.py

## Conclusion
* Preprocessing (scaling, outlier handling, and transformation) significantly improves clustering.
* PCA is essential for visualizing high-dimensional data.
* K-Means and DBSCAN provide complementary insights: K-Means for fixed clusters, DBSCAN for density-based structure and noise detection.


Would you like me to also **write a `requirements.txt`** file for this project so it’s ready to run?

# Task 8 — K-Means Clustering

This repository implements unsupervised learning with K-Means clustering on the Mall Customer Segmentation dataset, including the elbow method, silhouette score analysis, and cluster visualization.

## Objective

Perform K-Means clustering to segment mall customers, determine the optimal number of clusters using the elbow method and silhouette score, visualize clusters, and interpret customer segments.

## Dataset

- File: Mall_Customers.csv
- Features: CustomerID, Gender, Age, Annual Income (k$), Spending Score (1-100)
- Use case: Customer segmentation for marketing strategies
- Note: CustomerID is dropped; Gender is optionally encoded for clustering.

## Environment

- Python 3.8+
- Libraries: pandas, numpy, scikit-learn, seaborn, matplotlib

Install:
pip install pandas numpy scikit-learn seaborn matplotlib


## How to run

- Open the notebook and set INPUT_CSV to Mall_Customers.csv or the full path.
- Run cells top-to-bottom to scale features, perform elbow method, compute silhouette scores, fit K-Means with optimal K, and visualize clusters.

## Workflow

### Data loading and preparation
- Load Mall_Customers.csv and drop CustomerID.
- Optionally encode Gender (Male=1, Female=0) or exclude it for numeric-only clustering.
- Select features: Age, Annual Income (k$), Spending Score (1-100), and optionally Gender_enc.

### Feature scaling
- Standardize features with StandardScaler (critical for distance-based K-Means).

### Elbow method
- Fit K-Means for K in range 1-10 and plot inertia (WCSS) vs K.
- Identify the "elbow point" where inertia decrease slows, suggesting optimal K.

### Silhouette score
- Compute silhouette score for K in range 2-10.
- Higher scores indicate better-defined clusters; select K with the best score or combine with elbow insights.

### Fit K-Means with optimal K
- Train final K-Means model with chosen K (e.g., K=5 based on elbow + silhouette).
- Assign cluster labels to each customer.

### Cluster visualization
- 2D scatter plot using Annual Income vs Spending Score with color-coded clusters and centroids.
- PCA projection to 2D for higher-dimensional feature sets.

### Cluster profiling
- Compute mean feature values per cluster to interpret customer segments (e.g., high income + high spending, low income + low spending).

## Outputs

- Elbow curve: inertia vs K.
- Silhouette score plot: silhouette score vs K.
- Cluster scatter plots: 2D visualization with centroids.
- Cluster profiles: summary statistics per segment.


## Configuration

- INPUT_CSV: path to Mall_Customers.csv.
- OPTIMAL_K: set based on elbow method and silhouette score analysis.
- RANDOM_STATE: for reproducibility.

## Interview-ready notes

- How K-Means works: iteratively assigns points to nearest centroid and updates centroids until convergence, minimizing within-cluster variance (inertia).
- Elbow method: plots inertia vs K; the "elbow" is where adding more clusters yields diminishing returns.
- Limitations of K-Means: sensitive to initialization, assumes spherical clusters, requires K to be specified, and can be affected by outliers.
- Initialization: K-Means++ improves initial centroid selection to speed convergence and avoid poor local minima.
- Inertia: sum of squared distances from each point to its assigned centroid; lower is better but decreases with more clusters.
- Silhouette score: measures how similar a point is to its own cluster vs other clusters; ranges from -1 to 1, with higher values indicating better-defined clusters.
- Choosing K: combine elbow method, silhouette score, domain knowledge, and validation to select a stable and interpretable K.
- Clustering vs classification: clustering is unsupervised (no labels), finds natural groupings; classification is supervised, predicts known labels.

## Submission checklist

- Code runs end-to-end and generates elbow curve, silhouette plot, and cluster visualizations.
- README.md present at repository root.
- Dataset path configured correctly.
- Cluster profiles and interpretations documented.

## License and acknowledgments

- Educational use for internship Task 8.
- Dataset: Mall_Customers.csv for customer segmentation analysis.

<img width="603" height="291" alt="image" src="https://github.com/user-attachments/assets/1b6441fe-5fdd-489f-8744-b14137a271d2" />
<img width="805" height="630" alt="image" src="https://github.com/user-attachments/assets/0eece237-e681-4bdc-88f5-904a50adb770" />
<img width="800" height="623" alt="image" src="https://github.com/user-attachments/assets/6f6add9a-fd98-4674-a35a-3bff4d34ab81" />
<img width="221" height="193" alt="image" src="https://github.com/user-attachments/assets/79974d07-c36b-4a7f-90bb-65a1190e5189" />



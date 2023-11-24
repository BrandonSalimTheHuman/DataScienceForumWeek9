# Data Science Forum Week 9

# Unsupervised Machine Learning Algorithms and Evaluation
## Dataset: Iris dataset
## Algorithms: KMeans Clustering, Mean shift clustering, Agglomerative Clustering, Spectral Clustering
## Evaluation methods: Silhoutte score, Davies-Bouldin index, Rand score, Calinski and Harabasz score

### 1. KMeans Clustering

  - <p align="justify">KMeans is a partitioning algorithm that divides the dataset into clusters.
    The number of clusters is first determined, which is K, and the dataset will be divided into K number of clusters. 
    To start, K number of centroids are randomly intialized, and data points that are closest to the centroids
    are continuouly assigned to that centroid's cluster. Afterwards, the centroid is recalculated based on the newly assigned data point. 
    This process repeats until the centroid's change is under a certain amount, which shows that it is sufficiently stable 
    (also called convergence). When this happens, the clusters are formed.</p>
  - Results:
    - Silhouette Score: 0.55
    - Davies-Bouldin Index: 0.66 
    - Rand Score: 0.73 
    - Calinski and Harabasz Score: 560.40

### 2. Mean Shift Clustering

  - <p align="justify">MeanShift is a density-based algorithm that identifies clusters based on data density. Unlike KMeans, this algorithm
    doesn't need the number of clusters to be specified at the start (but is computationally expensive). Mean shift clustering calcualtes the mean
    of all data points within a certain radius for every data point, then shifts that data point towards the mean in its radius. This continuously 
    happens until convergence happens, at which point the data point that didn't move after convergence is the cluster centroid. Afterwards, data points
    are assigned to the cluster centroids.</p>
  - Results:
    - Silhouette Score: 0.69 
    - Davies-Bouldin Index: 0.39
    - Rand Score: 0.56 
    - Calinski and Harabasz Score: 508.88 

### 3. Agglomerative Clustering

  - <p align="justify">Agglomerative Clustering is a hierarchical clustering algorithm that iteratively merges clusters. It starts by putting each observation
    into its own cluster. The end goal is to continuously merge pairs of clusters that are closest to each other until there is only one cluster left,
    which encapsulates all the observations. Several different criteria can be used to determine which two clusters are closest to each other. In the code, I didn't
    specify the criteria, and the default is the Ward criteria, which works by minimizing the sum of squared differences within all clusters (minimizes variance). 
    The hierarchy of clusters can be visualized as a dendrogram, which is a tree-like diagram that shows the order and distances at which clusters are merged.</p>
  - Results:
    - Silhouette Score: 0.55 
    - Davies-Bouldin Index: 0.66 
    - Rand Score: 0.73
    - Calinski and Harabasz Score: 556.84 

### 4. Spectral Clustering

  - <p align="justify">Spectral Clustering uses the eigenvectors of the similarity matrix to perform clustering. It reduces the number of dimensions first before performing clustering.
    It does this by first creating a similarity graph based on the similarity between data points, then using this to calculate the similarity matrix. Afterwards, the eigenvectors
    of the similarity matrix is calculated, and these eigenvalues are used to form a new matrix. This step reduces the dimension, and the resulting matrix is a low-dimensional representation
    of the data points. Since the number of dimensions has been reduced, clustering is now performed with the aid of standard clustering algorithms (example: Kmeans). 
    
  - Results:
    - Silhouette Score: 0.56 
    - Davies-Bouldin Index: 0.65
    - Rand Score: 0.75 
    - Calinski and Harabasz Score: 554.91
  

### Overall Findings:

  - Silhoutte score from best to worst: Mean shift -> Spectral -> Agglomerative -> Kmeans

  - DBI from best to worst: Mean shift -> Spectral -> Agglomerative -> Kmeans

  - Rand score from best to worst: Spectral -> Agglomerative -> Kmeans -> Mean shift

  - Calinksi and Harabasz score from best to worst: Kmeans -> Agglomerative -> Spectral -> Mean shift

  - <p align="justify">All algorithms performed reasonably well. However, Spectral Clustering is generally better than the others, and Kmeans is generally the worst (or at least, on the iris dataset).
    This does align with the fact that spectral clustering performs well when the number of clusters is small, and in this case, there are only 3.</p>
    


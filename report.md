# final.ipynb

This script is a flexible and adaptable tool for applying and analyzing various clustering techniques to data, focusing on word contour data in this particular context. 

The script is organized into three main parts: data preparation, helper function definition, and clustering application through a `Clustering` class. It makes use of various libraries such as pandas, numpy, matplotlib, sklearn, and cv2 to manipulate data, visualize results, and apply clustering techniques.

## Data Preparation

The script starts with importing necessary libraries, followed by loading CSV and JSON data. The data are then merged to form the primary dataframe used throughout the script.

## Helper Function Definition

Helper functions are defined for operations such as scaling contour points and calculating areas. These functions are applied to the dataframe to generate new features (e.g., `scaled_contour` and `scaled_contour_area`).

## Clustering

The main part of the script involves defining a `Clustering` class, which provides functionalities for applying clustering, validating results, plotting clusters, and saving cluster results. This class utilizes scikit-learn's `KMeans` and `GaussianMixture` classes to perform the actual clustering.

The `Clustering` class requires a `config` dictionary during initialization. This dictionary specifies:
- `df`: the primary dataframe used for clustering,
- `features`: the features to be used for clustering, 
- `clusters_range`: the number of clusters to be used, 
- `label_indices`: the labeled indices of data points.

The flexibility of the script is reflected in the ability to specify these options in the `config` dictionary. By modifying this dictionary, users can perform clustering with different features, different numbers of clusters, and different labeled data.

Once the `Clustering` object is created, various clustering algorithms can be applied by calling `apply_clustering('gmm')` or `apply_clustering('kmeans')`. The validation results for each algorithm and cluster number are printed.

Cluster visualizations can be created using the `plot_clusters()` function, which generates scatter plots of the clusters. The `save_contours()` function saves individual contour images into separate directories for each cluster.

The `plot_labelled_data()` function can be used to visualize the original labeled data.

## Output

The script generates several outputs:
- Cluster validation tables for each clustering algorithm and cluster number, printed to the console.
- Scatter plots of the clusters, saved as PNG files in directories named after the used features and the clustering algorithm.
- Contour images, saved in directories named after the cluster they belong to.
- A scatter plot of the original labeled data.

These outputs provide a comprehensive view of the clustering results, which can be used for further analysis or report generation. 

As a final note, this script offers a robust and flexible solution to applying clustering techniques to data, providing users with the ability to easily adapt the code to different data, different features, and different clustering algorithms.
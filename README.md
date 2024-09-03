Affinity Propagation is a clustering algorithm that is commonly used in Machine Learning and data analysis. Unlike other traditional clustering algorithms which require specifying the number of clusters beforehand, Affinity Propagation discovers cluster centres and assigns data points to clusters autonomously. It is particularly useful when the number of clusters is not known in advance or when the data doesn’t conform to spherical or convex cluster shapes. In this article, we will discuss about Affinity propagation, its parameters and implementation with evaluation.
What is Affinity Propagation?
Affinity Propagation is based on the concept of “message-passing” between data points to identify cluster centres and assign data points to these centres automatically. It utilizes “exemplars,” which are typical data points representing other data points within the same cluster. The objective of the algorithm is to identify the most representative exemplars of the overall data and employ them to cluster the data into compatible groups. This algorithm is especially suitable for data with numerous clusters or data exhibiting intricate, non-linear distribution patterns.
Key-steps of Affinity propagation
Affinity Propagation clustering algorithm has several step which are discussed below

Similarity Computation: This algorithm first calculates a similarity (or dissimilarity) matrix which quantifies the similarity between pairs of data points. The choice of similarity metric depends on the data and the problem what we’re working on. There are some common metrics like Euclidean distance, negative squared Euclidean distance etc.
Responsibility Update: Then this algorithm initializes the responsibility matrix (R), where R(i, k) represents the responsibility of data point i to be the exemplar for data point k. We have already discussed about it previously in this article. Here data points compete to be exemplars based on their similarity and the responsibility which they receive from other data points.
Availability Update: Then it initializes the availability matrix (A), where A(i, k) represents the availability of data point k to choose data point i as its exemplar. This step is also already discussed in this article. Here data points consider the availability of other data points to be their exemplars. If a data point has high availability from other data points then it is more likely to be chosen as an exemplar.
Update Responsibility and Availability: Then it updates the responsibility and availability matrices iteratively until convergence which is reached when the matrices no longer change significantly between iterations.
Net Responsibility Calculation: Then it calculates the net responsibility for each data point by summing its responsibility and availability.
Exemplar Selection: Then a crucial task is to identify exemplars as data points with high net responsibility. These exemplars represent the cluster centers.
Cluster Assignment: Finally it assigns each data point to the nearest exemplar (based on similarity) to form clusters.
Working Principals of Affinity Propagation
The algorithm begins by initializing the “responsibility” and “availability” matrices to zero.

Similarity Matrix: All similarities between data points are represented in a similarity matrix. This matrix does not need to contain all the similarity values to ensure a reasonable number of clusters.

Message Passing: Each data point is treated as a potential exemplar. Real-valued messages are exchanged between data points until a high-quality set of exemplars and corresponding clusters gradually emerges. The algorithm involves passing two kinds of messages:

Responsibility Messages: These messages are sent from data point i to candidate exemplar k and reflect the accumulated evidence for how well-suited point k is to serve as the exemplar for point i, taking into account other potential exemplars for point i.
Availability Messages: These messages are sent from candidate exemplar k to point i and reflect the accumulated evidence for how appropriate it would be for point i to choose point k as its exemplar, taking into account the support from other points that point k should be an exemplar.
Convergence: The algorithm iteratively updates the responsibility and availability matrices until a stopping criterion is met. This could be a predefined number of iterations or until the algorithm converges.

Exemplars and Clusters: At the end of the process, the algorithm provides a set of exemplars and the assignment of all other data points to these exemplars, effectively partitioning the data into clusters.

The steps are implemented in the algorithm to iteratively find the best exemplars and form clusters around them.

Benefits of using Affinity Propagation
Using Affinity Propagation for clustering has several benefits which are listed below:

Automatic Cluster Center Detection: Affinity Propagation automatically identifies cluster centers and total number of clusters which makes it suitable for datasets with an unknown or variable number of clusters and useful for large complex real-world datasets.
Robust to Noise and Outliers: Affinity Propagation is relatively robust to noise and outliers in the data which makes it useful in various applications like image segmentation, document clustering and biological dataset analysis etc.
Handles Non-Spherical Clusters: Unlike some traditional clustering algorithms, Affinity Propagation can handle clusters of various shapes and sizes.
Scalability: It can be applied to large datasets, although it may require optimization for computational efficiency.

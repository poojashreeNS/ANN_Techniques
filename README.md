# ANN_Techniques

## LHS
LSH construct a hash table as their data structure by mapping points that are nearby into the same bucket.
In LSH, in order to construct the index, we apply multiple hash functions to map data points into buckets so that data points near each other are located in the same buckets with high probability, while data points far from each other are likely to fall into different buckets.
In order to search the constructed index, the query point is hashed in order to obtain the closest buckets (a set of candidate points) from which the closest to the query points are returned.

## Exhaustive search
Comparing each point to every other point, which will require Linear query time depending on the size of dataset.

## Product Quantization
In Product Quantization we can increase drastically the number of centroids by dividing each vector into many vectors and run our quantizer on all of these and thus improves accuracy.
Construct a table with the calculated distance between each sub-vector and each of the centroids for that sub-vector.
Calculating approximate distance values for each of the vectors in the dataset, we just use those centroids id’s to look up the partial distances in the table and sum those up!

## Trees Based ANN
They construct forests (collection of trees) as their data structure by splitting the dataset into subsets.
Each tree is constructed in the following way, we pick two points at random and split the space into two by their hyperplane, we keep splitting into the subspaces recursively until the points associated with a node is small enough.
In order to search the constructed index, the forest is traversed in order to obtain a set of candidate points from which the closest to the query point is returned.

## HNSW
The algorithm examines the distances from a query to the neighbors of a current base node and then selects as the next base node the adjacent node that minimizes the distance, while constantly keeping track of the best-discovered neighbors. The search is terminated when some stopping condition is met.

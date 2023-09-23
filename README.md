# K-Nearest-Neighbors.
As you can see from the chart above, k-Nearest Neighbors belongs to the supervised branch of Machine Learning algorithms, which means that it requires labeled data for training.
However, suppose you only want to find similar data points (i.e., find neighbors) instead of making predictions. In that case, it is possible to use kNN in an unsupervised manner (see sklearn’s NearestNeighbors implementation of such unsupervised learner).
It is worth noting that kNN is a very flexible algorithm and can be used to solve different types of problems. Hence, in this article, I will take you through its use for classification and regression.

Note, typically, Euclidean distance is used, but some implementations allow alternative distance measures (e.g., Manhattan).

Once the neighbors are found, one of the two things will happen depending on whether you are performing classification or regression analysis.
For our first python example in this repository:
Classification: the algorithm uses simple majority voting to assign the label to the new data point. In our example, the majority consists of 3 neighbors with a price<$1M. Hence, the predicted label for the new data point is <$1M.
Regression: the algorithm calculates the average value of all the neighbors. In our example this would be: ($900K + $950K + $980K + $1M + $1.1M) / 5 = $986K. So, the predicted price of a house (new data point) is $986K.
One final thing to add, the explanation above showed what happens when uniform weights are being used. I.e., each neighbor carries the same weight in the calculation. However, in some cases (e.g., when you have sparse data), it may be beneficial to use distance-based weights.

Distance weighting assigns weights proportional to the inverse of the distance from the query point, which means that neighbors closer to your data point will carry proportionately more weight than neighbors that are further away.
Pros: There are only two parameters required to work with KNN, i.e. the value of K and the distance function to use. It is a lazy learning algorithm and therefore doesn't require training on all data points,less computation, only using the K-Nearest neighbors to predict. This makes the KNN algorithm much faster than other algorithms that require training with the whole dataset such as Support Vector Machines, linear regression, etc. 
Cons: Finally, the KNN algorithm doesn't work well with categorical features since it is difficult to find the distance between dimensions with categorical features. The X values.
Also it is very sensitive to OUTLIERS. 

The KNN algorithm doesn't work well with high dimensional data,a lot of columns, because with a large number of dimensions, the distance between points gets "weird". That is why it is really important to do regularization after split the data. to use the same scale and avoid weighted distances giving more importance to one neighbour to the other.

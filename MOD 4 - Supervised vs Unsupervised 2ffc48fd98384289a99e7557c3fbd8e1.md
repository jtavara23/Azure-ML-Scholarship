# MOD 4 - Supervised vs Unsupervised

Lab:

[Two-Class Classifiers Performance](https://www.notion.so/Two-Class-Classifiers-Performance-94499b49a5b34426b66f97cf6dd3866b)

[Compare the performance of various multiclass classifiers](https://www.notion.so/Compare-the-performance-of-various-multiclass-classifiers-12e7d632dab44b5d8d83b00be38499a3)

[Lab: Train a Classifier Using Automated Machine Learning](https://www.notion.so/Lab-Train-a-Classifier-Using-Automated-Machine-Learning-06b1795b203d4a1c9db0d4a93bc8c813)

[Compare the performance of various regressors](https://www.notion.so/Compare-the-performance-of-various-regressors-654baff6e9cf4c0c9d8e1ed0453a6a75)

[Lab: Train a Regressor using Automated Machine Learning](https://www.notion.so/Lab-Train-a-Regressor-using-Automated-Machine-Learning-28ac18a5586549aaa4be74966f2bc0c8)

[Lab: Train a Simple Clustering Model](https://www.notion.so/Lab-Train-a-Simple-Clustering-Model-652215f1650b4c3c8c436e4ccdfcd588)

# Supervised Classification

![MOD%204%20-%20Supervised%20vs%20Unsupervised%202ffc48fd98384289a99e7557c3fbd8e1/Untitled.png](MOD%204%20-%20Supervised%20vs%20Unsupervised%202ffc48fd98384289a99e7557c3fbd8e1/Untitled.png)

## Supervised Classification metrics:

- Roc
- Precision
- Confusion Matrix

---

# Supervised Regression

Common machine learning algorithms for regression problems include:

- Linear Regression
    - Fast training, linear model
- Decision Forest Regression
    - Accurate, fast training times
- Neural Net Regression
    - Accurate, long training times

## Supervised Regression metrics:

- Mean Absolute Error

---

The default behavior in Automated Machine Learning to **deal with missing values** for categorical features is impute with most frequent value, and impute with average for numeric values.

# Unsupervised Learning

## Clustering

Organize data in finite number of groups/clusters. E.g K-means.

- Density-based clustering: Groups members based on how closely they are packed together; can learn clusters of arbitrary shape.
- Hierarchical clustering: Builds a tree of clusters.
- Centroid-based clustering: Groups members based on their distance from the center of the cluster.
- Distribution-based clustering: Groups members based on the probability of a member belonging to a particular distribution.

K-Means is a centroid-based, unsupervised clustering algorithm. It creates up to a target (K) number of clusters and groups similar members together in a cluster.

## Feature Learning (Representational Learning)

Transforms sets of inputs into other inputs that are potentially more useful in solving a given problem.

EG PCA, T-SNE, Autoencoders(o learn a representation (encoding) for a set of data)

## Anomaly Detection

Identifies two groups: normal and abnormal.

---

# Semi-Supervised Learning

it may be possible to get partially labeled data. This is where semi-supervised learning is useful.

Self-training: The model is trained with the labeled data, then used to make predictions for the unlabeled data (resulting in a dataset that is fully labeled).
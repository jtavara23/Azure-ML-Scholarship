# MOD 5 - Applications of ML

![MOD%205%20-%20Applications%20of%20ML%20eab2d21f8f364aa8bb6d9897c7fb9c1d/Untitled.png](MOD%205%20-%20Applications%20of%20ML%20eab2d21f8f364aa8bb6d9897c7fb9c1d/Untitled.png)

### Benefits of Deep Learning

- A key benefit of deep learning algorithms is the ability to learn arbitrarily complex functions.
- They can be distributed for parallel training.
- They can learn complex patterns without explicitly seeing those patterns.
- They can be used on very large sets of data.

### Applications

- Language Translation
- Image Recognition
- Speech Recognition, translating into a time series base information.
- Time series based as Forecasting
- Predictive Analysis / Anomalies

# Lab: Train a Simple Neural Net

[Lab: Train a Simple Neural Net](https://www.notion.so/Lab-Train-a-Simple-Neural-Net-320f183bdd144551a115db9ca3962af8)

# Lab: Simple Recommender

[Lab: Simple Recommender ](https://www.notion.so/Lab-Simple-Recommender-e510fd8cd6684a62a07865487ed7f379)

# Lab: Text Classifier

[Lab: Text Classifier](https://www.notion.so/Lab-Text-Classifier-766f2353429f459ba8d01f12e7ca5025)

# **Feature Learning**

As we've discussed previously, *feature engineering* is one of the core techniques that can be used to increase the chances of success in solving machine learning problems. As a part of feature engineering, **feature learning** (also called **representation learning**) is a technique that you can use to derive new features in your dataset. Let's have a look at how this technique works.

There are supervised and unsupervised approaches to learn new features. These are a set of methods that can extract hidden information in data:

- Convolutional neural networks: this is a deep learning neural network consisting of stacks of 3 sets of layers: convolution layer, max-polling layer and a densely connected layer.

    In CNN, the convolutional layer is used to learn local patterns, the max-polling layer enables features detected by the convolutional layer to be translation invariant and the densely connected layers are used to detect global features

- Autoencoders: this is a special type of unsupervised neural network that aims to reproduce the input layer in the output layer but with an internal bottleneck layer. Autoencoders, among other things can be used for feature extraction by taping into the result of the bottleneck layer which, if well designed, has sufficient information to encode the input to be reproduced to a certain degree in the output.

## Anomaly Detection

- Anomaly detection is a machine learning technique concerned with finding data points where the number of anomalous cases are much less than the number of normal cases.   They may be the result of bad data, unusual behavior, or important exceptions to the typical trends. This unbalance makes some of the traditional algorithms to fail.
- The use of autoencoders for anomaly detection: Basically, the autoencoder is trained with the normal cases and the error between the input and outputs is measured. After being trained, when it sees an anomalous case, the error grows and it can be detected over certain threshold.

    • Supervised anomaly detection: Binary classification where entities must be classified as either normal or anomaly.

    • Unsupervised anomaly detection: Identifying two major groups/clusters of entities - normal and abnormal.

    • Applications: Condition monitoring and failure prevention, Fraud detection, Intrusion section, Anti-virus/malware protection, Outlier detection, etc.

# Forecasting

A class of problems dealing with predictions with orderable datasets (which can be time-series datasets but optional)

Types of forecasting algorithms: 

- ARIMA
- Multi-variate regression
- Prophet
- ForecastTCN
- RNN

[**Train a time-series forecasting model using Automated Machine Learning**](https://www.notion.so/Train-a-time-series-forecasting-model-using-Automated-Machine-Learning-86c3660ae8e74828a1124f9f6cd78458)

Key concepts from the lab:

• **normalized_root_mean_squared_error**: RMSE divided by the range of data

• k-fold cross validation: A resampling procedure used to evaluate ML models on limited data. Specifically, the training data is randomly split equally into n folds, which are used one by one for validating the model trained on the remaining folds until each fold is used at least once as validation set. The scores are then averaged and the model is retrained on the whole training data.

---
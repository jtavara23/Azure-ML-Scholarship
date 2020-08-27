# MOD 2 - Introducction

# Intro to ML

## Approaches to Scaling

### Standardization

- Rescales the data to have MEAN = 0 and Variance = 1 →
- $(Individual_Data - Mean ) / StandardDeviation$

### Normalization

- Rescales the data into range [0-1]

$$X' = \frac{X_{old} - X_{min}}{X_{max} - X_{min}} $$

### One hot Encoding

### Original Encoding ( 0,1,2, etc)


## Text Data

### Normalization

- Process of transforming a piece of text into a canonical form.

### Lemmatization

- Process of reducing multiple inflections to that single dictionary form.

    [Examples](https://www.notion.so/01b8b56ec0c24723b6a6e91763bf597d)

### Steaming ✅

### Stop Words ✅

### Tokenization

- Split each string of text into a list of smaller parts or tokens

### TF-IDF ✅


In summary, a typical pipeline for text data begins by **pre-processing or *normalizing*** the text.

This step typically includes tasks such as breaking the text into sentence and word *tokens*, standardizing the spelling of words, and removing overly common words (called *stop words*).

The next step is ***feature extraction and vectorization***, which creates a numeric representation of the documents. Common approaches include [TF-IDF vectorization](https://en.wikipedia.org/wiki/Tf-idf), [Word2vec](https://en.wikipedia.org/wiki/Word2vec), and [Global Vectors (GloVe)](https://nlp.stanford.edu/pubs/glove.pdf).

![MOD%202%20-%20Introducction%20c102bb49c3c54f45a129e69f6b871329/Untitled.png](MOD%202%20-%20Introducction%20c102bb49c3c54f45a129e69f6b871329/Untitled.png)

---


## Computer science vs. Statistical perspective

> We are using input features to create a program that can generate the desired output. For the rows in the table, we might call each row an entity/ instance/ an observation about an entity. Columns are referred as feature/attribute.

In contrast, someone with a background in statistics might be inclined to say something more like:

> We are trying to find a mathematical function that, given the values of the independent variables can predict the values of the dependent variables.


---

## The Machine Learning Ecosystem

**1. Libraries.** When you're working on a machine learning project, you likely will not want to write all of the necessary code yourself—instead, you'll want to make use of code that has already been created and refined. That's where libraries come in. A *library* is a collection of pre-written (and compiled) code that you can make use of in your own project. *NumPy* is an example of a library popularly used in data science, while *TensorFlow* is a library specifically designed for machine learning. Read this [article](https://www.geeksforgeeks.org/best-python-libraries-for-machine-learning/) for some other useful library. 

Examples: Scikit-Learn. 

- [TensorFlow](https://www.tensorflow.org/) is a free, open-source software library for machine learning built by [Google Brain](https://en.wikipedia.org/wiki/Google_Brain).
- [Keras](https://keras.io/) is a Python deep-learning library. It provide an Application Programming Interface (API) that can be used to interface with other libraries, such as TensorFlow, in order to program neural networks. Keras is designed for rapid development and experimentation.
- [PyTorch](https://pytorch.org/) is an open source library for machine learning, developed in large part by [Facebook's AI Research lab](https://ai.facebook.com/). It is known for being comparatively easy to use, especially for developers already familiar with Python and a [Pythonic code style](https://stackoverflow.com/questions/25011078/what-does-pythonic-mean).

**2. Development environments.** A *development environment* is a software application (or sometimes a group of applications) that provide a whole suite of tools designed to help you (as the developer or machine learning engineer) build out your projects. *Jupyter Notebooks* and *Visual Studio* are examples of development environments that are popular for coding many different types of projects, including machine learning projects. 

Example: Apache Spark is an open-source analytics engine that is designed for cluster-computing and that is often used for large-scale data processing and big data.

**3. Cloud services.** A *cloud service* is a service that offers data storage or computing power over the Internet. In the context of machine learning, you can use a cloud service to access a server that is likely far more powerful than your own machine, or that comes equipped with machine learning models that are ready for you to use. Read more information about different cloud services from this [article](https://medium.com/appanion/machine-learning-as-a-service-the-top-cloud-platform-and-ai-vendors-2df45d51374d)

[Assets Components](https://www.notion.so/b2c338ca69ff4f04b13f4d4f11460093)

[Managing Components](https://www.notion.so/e0d182512ee440ffa2403ed80c7c24de)

For each of these components, there are multiple options you can choose from. Let's have a look at some examples.

![MOD%202%20-%20Introducction%20c102bb49c3c54f45a129e69f6b871329/Untitled%201.png](MOD%202%20-%20Introducction%20c102bb49c3c54f45a129e69f6b871329/Untitled%201.png)

[Features in Azure ML workspace](https://www.notion.so/d43649f1d21545ac998f6184dad1443e)

---


## L**inear Regression in Machine Learning**

The equation we used above was:

y = mx + b*y*=*mx*+*b*

In algebraic terms, we may refer to m*m* as the **coefficient** of x or simply the **slope** of the line, and we may call *b* the **y-intercept**. In machine learning, you will typically see the y-intercept referred to as the **bias**. In machine learning, you will also often see the equation represented using different variables, as in:

$$y = B_0 + B_1*xy=B0​+B1​∗x$$

## Cost Error

The most commonly used cost function for linear regression is the root mean squared error (RMSE)

![MOD%202%20-%20Introducction%20c102bb49c3c54f45a129e69f6b871329/Untitled%202.png](MOD%202%20-%20Introducction%20c102bb49c3c54f45a129e69f6b871329/Untitled%202.png)

## Deep Learning vs Classical ML advantages/disadvantages

**Deep learning advantages:**

- Suitable for high complexity problems
- Better accuracy, compared to classical ML
- Better support for big data
- Complex features can be learned

**Deep learning disadvantages:**

- Difficult to explain trained data
- Require significant computational power

**Classical ML advantages:**

- More suitable for small data
- Easier to interpret outcomes
- Cheaper to perform
- Can run on low-end machines
- Does not require large computational power

**Classical ML disadvantages:**

- Difficult to learn large datasets
- Require feature engineering
- Difficult to learn complex functions

## **Bias vs. Variance**

**Bias:**

measures how *inaccurate* the model prediction is in comparison with the true output. It is due to *erroneous **assumptions*** made in the machine learning process to simplify the model and make the target function easier to learn. High model complexity tends to have a low bias.

*Low bias* means *fewer* assumptions about the target function.

**Variance:**

Measures how much the target function will *change* if different training data is used. Variance can be caused by modeling the *random noise* in the training data. High model complexity tends to have a high variance.

The **prediction error** can be viewed as the sum of *model error* (error coming from the model) and the *irreducible error* (coming from data collection).

```
prediction error = Bias error + variance + error + irreducible error

```

As a general trend:

- Parametric and linear algorithms often have high bias and low variance,
- whereas non-parametric and non-linear algorithms often have low bias and high variance.

> The goal of training machine learning models is to achieve low bias and low variance. The optimal model complexity is where bias error crosses with variance error.
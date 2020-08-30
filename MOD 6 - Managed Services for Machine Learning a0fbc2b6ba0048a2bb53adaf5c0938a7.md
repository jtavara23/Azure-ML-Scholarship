# MOD 6 - Managed Services for Machine Learning

You will learn about various types of **computing resources** made available through managed services, including:

- Training compute
- Inferencing compute
- Notebook environments

You will also study the main concepts involved in the **modeling process**, including:

- Basic modeling
- How parts of the modeling process interact when used together
- More advanced aspects of the modeling process, like automation via pipelines and end-to-end integrated processes (also known as DevOps for Machine Learning or simply, MLOps)
- How to move the results of your modeling work to production environments and make them operational

Finally, you will be introduced to the world of programming the managed services via the **Azure Machine Learning SDK for Python**.

---

---

# INTRO

Machine learning requires a number of tools to prepare the data, train the models, and deploy the models. Typically, this involves installing several applications and libraries on a machine, configuring the environment settings, and then loading any additional resources required to begin working within notebooks or integrated development environments (IDEs).

This is the advantage of managed services for machine learning, which provide a ready-made environment that is pre-optimized for your machine learning development.

A **compute target** is a designated compute resource or environment where you run training scripts or host your service deployment.

## **Training Compute**

- **Training Clusters** Primary choice
- **Compute Instances** - Primarily intended for notebook environments, but you could also train your model here.
- **Local Compute** - It uses your local machine for small scale tasks.

### **Training Cluster**

- For training and batch inferencing.
- You may have a single or multi node cluster.
- Being fully managed means you don't need to provision resources, adjust server settings or schedule jobs. It is auto scaled.
- It supports automatic cluster management and job scheduling,
- It supports both CPU and GPU resources.

[Managing a Compute instance](https://www.notion.so/Managing-a-Compute-instance-6d9add32d3a54fc984db9e2e22f5b67b)

# **Inferencing Compute**

You need to deploy your trained model for inferencing.

Real time inferencing you need to make new inferences for each row of data in real time, whereas in batch inferencing on multiple roles of data. One should go for a web service or IoT device for the former. Azure provides inferencing compute. Virtually any compute resource can be used for batch inferencing.

### **Compute targets for production workload**

- Azure Kubernetes Service
- Azure machine learning training cluster.

### **Compute targets for specialised deployments**

- Azure Functions
- Azure IoT edge
- Azure Data Box Edge

![MOD%206%20-%20Managed%20Services%20for%20Machine%20Learning%20a0fbc2b6ba0048a2bb53adaf5c0938a7/Untitled.png](MOD%206%20-%20Managed%20Services%20for%20Machine%20Learning%20a0fbc2b6ba0048a2bb53adaf5c0938a7/Untitled.png)

# Managing Notebook Environments

we can use a notebook environment to perform the five primary stages of model development:

![https://video.udacity-data.com/topher/2020/May/5ebd7e47_managed-notebooks/managed-notebooks.png](https://video.udacity-data.com/topher/2020/May/5ebd7e47_managed-notebooks/managed-notebooks.png)

[https://youtu.be/ZF33SyTMGNA?t=129](https://youtu.be/ZF33SyTMGNA?t=129)

# Basic Modeling

In essence, training a machine learning model is the process through which a mathematical model is built through data that contains inputs and might also have expected outputs. Basic concepts for making a model are:

- **Experiment** - It is a generic context of *handling organiser runs.* It organises all artefacts in your model training process.
- **Runs** - A Run is a *single execution of your training script*. Model Training Runs are used to build a train model. A run contains all artefacts associated with a training process, like output files, metrics, logs and snapshots of the directory that contains your script.
- **Model** - It is a piece of code that *takes input and produces output*.
- **Model Registry** - The model registry *keeps track of all the models* in Azure Machine Learning workspace.

## **Experiment**

***It is a logical entity that organises the process***. It organises runs such that you can keep track of hundreds of them. When you submit a run, the experiment name is asked for, as the run is stored under that experiment.

![MOD%206%20-%20Managed%20Services%20for%20Machine%20Learning%20a0fbc2b6ba0048a2bb53adaf5c0938a7/Untitled%201.png](MOD%206%20-%20Managed%20Services%20for%20Machine%20Learning%20a0fbc2b6ba0048a2bb53adaf5c0938a7/Untitled%201.png)

You can observe all runs such that

- Parameters such as alpha value and RMSE are handy.
- How were they trained? How unique metrics have changed overtime?
- Click on each run for more detailed information. You may download the model file instead of retraining it manually.

## **Runs**

*It is a set of instructions that define how a script should be run in a specified compute target.*

Once you have an experiment, you can create **runs** within that experiment. A run contains all artefacts associated with the training process, like output files, metrics, logs, and a snapshot of the directory that contains your scripts.

You produce a run when you submit a script for training. A run may also have child runs.

After submitting a run you can view the progress live as a completed activity in your experiment.

## **Models**

A run is used to produce a *model*. Essentially, a **model** is a piece of code that takes an input and produces output. To get a model, we start with a more general algorithm. By combining this algorithm with the training data—as well as by tuning the hyperparameters—we produce a more specific function that is optimized for the particular task we need to do. Put concisely:

> Model = algorithm + data + hyperparameters

## **Model Registry**

Once we have a trained model, we can turn to the **model registry**, which keeps track of all models in an Azure Machine Learning workspace. Note that models are either produced by a Run or originate from outside of Azure Machine Learning (and are made available via model registration).

[https://youtu.be/dRB4fj3LD4o](https://youtu.be/dRB4fj3LD4o)

An experiment is a generic context for handling and organizing runs. Once you have an experiment, you'll want to create one or more runs within it, until you identify the best model. You then register the final model in a model registry. After registration, you can then download or deploy the registered model and receive all the files that were registered.

[Train a machine learning model from a managed notebook environment](https://www.notion.so/Train-a-machine-learning-model-from-a-managed-notebook-environment-d69b8d2ca26144008fc970cce08fc080)

# **Machine Learning Pipelines - Advanced Modeling**

As the process of building your models becomes more complex, it becomes more important to get a handle on the steps to prepare your data and train your models in an organized way. In these scenarios, there can be many steps involved in the end-to-end process, including:

- Data ingestion
- Data preparation
- Model building & training
- Model deployment.

These steps are organized into *machine learning pipelines*.

![MOD%206%20-%20Managed%20Services%20for%20Machine%20Learning%20a0fbc2b6ba0048a2bb53adaf5c0938a7/Untitled%202.png](MOD%206%20-%20Managed%20Services%20for%20Machine%20Learning%20a0fbc2b6ba0048a2bb53adaf5c0938a7/Untitled%202.png)

## MLOps: Creating Automatic End-to-End Integrated Processes

we want to develop processes that use automated builds and deployments.

![MOD%206%20-%20Managed%20Services%20for%20Machine%20Learning%20a0fbc2b6ba0048a2bb53adaf5c0938a7/Untitled%203.png](MOD%206%20-%20Managed%20Services%20for%20Machine%20Learning%20a0fbc2b6ba0048a2bb53adaf5c0938a7/Untitled%203.png)

The process flow can be observed as:

- **Collaboration** - Code, dataset and environment versioning.
- **Build and Test App** - Model validation and profiling
- **Deploy model** - Model packaging, simple deployment across cloud and edge

    ![MOD%206%20-%20Managed%20Services%20for%20Machine%20Learning%20a0fbc2b6ba0048a2bb53adaf5c0938a7/Untitled%204.png](MOD%206%20-%20Managed%20Services%20for%20Machine%20Learning%20a0fbc2b6ba0048a2bb53adaf5c0938a7/Untitled%204.png)

# **Operationalizing Models**

After you have trained your machine learning model and evaluated it to the point where you are ready to use it outside your own development or test environment, **you need to deploy it somewhere**. Another term for this is **operationalization**.

## **Real-time Inferencing**

The model training process can be very compute-intensive, with training times that can potentially spann across many hours, days, or even weeks. A trained model, on the other hand, is used to make decisions on new data quickly. In other words, it infers things about new data it is given based on its training. Making these decisions on new data on-demand is called **real-time inferencing.**

[https://youtu.be/bM9wpLEE3YQ](https://youtu.be/bM9wpLEE3YQ)

## B**atch Inferencing**

Unlike real-time inferencing, which makes predictions on data as it is received, **batch inferencing** is run on large quantities (batches) of existing data. Typically, batch inferencing is run on a recurring schedule against data stored in a database or other data store.

![MOD%206%20-%20Managed%20Services%20for%20Machine%20Learning%20a0fbc2b6ba0048a2bb53adaf5c0938a7/Untitled%205.png](MOD%206%20-%20Managed%20Services%20for%20Machine%20Learning%20a0fbc2b6ba0048a2bb53adaf5c0938a7/Untitled%205.png)

A **hot path** tries to *make predictions against the data in real time*, and **cold path** in a *batch fashion*. Batch layers stores data in raw form and performs inferencing in batches. In speed layer predictions are made as quickly as it arrives.

***Prediction results are stored within a serving laye***r, which is typically a database for later use by the analytics client.

Eventually they both ***converge to an analytics client application.***

**Example** - Fraud detection in Banking

[Deploy a Trained Model as a Webservice](https://www.notion.so/Deploy-a-Trained-Model-as-a-Webservice-ac0ab4185dfe4fa0800cfaf3be159f80)

---

---

# Programmatically Accessing Managed Services - A**zure Machine Learning Python SDK**

This is a service if you require Python to run and use your model on the Azure Machine Learning Studio. You can interact with the service using any environment like Jupyter, VS Code etc. It also supports many of the popular Machine Learning and deep Learning Python Packages like Sci-kit learn, Tensorflow, Pytorch, Keras.

Key areas include

- Prepare and manage the lifecycle of the datasets used in the Machine Learning Experiments.
- Organize and Monitor experiments - Manage cloud resources for monitoring login and organizing your machine learning experiments.
- Model Training
- Automated Machine Learning
- Model Deployment - Convert your model to any RESTful service for application.

You can also manage your model training runs through python code and query runs and also mark them complete. Typically the model training scripts is going to generate output and log metrics to run as the model is trained. you can monitor this from your notebook in the following two ways.

[https://lh5.googleusercontent.com/STCZJ6Ag8z17VNgAtP83nommTjXDjDDOlENHT1zAR6ERlm1CVYuASJeIGPoguRBKma-LiHzoZ2D4yzsJA6Fps6hVXTsJ-9K0Tsan3vYZlc8_ROTdV48=w1280](https://lh5.googleusercontent.com/STCZJ6Ag8z17VNgAtP83nommTjXDjDDOlENHT1zAR6ERlm1CVYuASJeIGPoguRBKma-LiHzoZ2D4yzsJA6Fps6hVXTsJ-9K0Tsan3vYZlc8_ROTdV48=w1280)

[https://lh4.googleusercontent.com/01BF00ysFgX92Y5mKSe6668DMlXI5e3_FiSbU-DVxTN4eqVZehJLszMePSc_xys2IgsSPkhqTyJBhjnhTxEAl8Y9F6tXyPGjFOrhrfA8p70GMI3LRu7j=w1280](https://lh4.googleusercontent.com/01BF00ysFgX92Y5mKSe6668DMlXI5e3_FiSbU-DVxTN4eqVZehJLszMePSc_xys2IgsSPkhqTyJBhjnhTxEAl8Y9F6tXyPGjFOrhrfA8p70GMI3LRu7j=w1280)

Note how the widget allows you to interact with the generated content.

### ***This lesson walked us through what it actually takes to use our models beyond our files. It brought our knowledge gained so far to action, and also displayed how did Microsoft Azure Machine Learning Services makes our lives as Machine Learning enthusiasts easier. It made me look forward to use it more!***

[Training and deploying a model from notebook running in compute instance](https://www.notion.so/Training-and-deploying-a-model-from-notebook-running-in-compute-instance-03b8ad52f17640e796b024b4a047b41b)
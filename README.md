# Amazon-Sagemaker

## Lab Overview

This lab focuses on leveraging Amazon SageMaker, a fully managed service that provides every developer and data scientist with the ability to build, train, and deploy machine learning (ML) models quickly. The lab is designed for the QFM – Data Engineering major and offers practical experience with the AWS cloud environment for ML tasks.

## Official Documentation

The official SageMaker SDK documentation is a valuable resource for this lab and can be found here: [SageMaker SDK Documentation](https://sagemaker.readthedocs.io).

## 1. Data Processing using SageMaker

We begin by familiarizing ourselves with a dataset for a marketing campaign. The goal is to analyze the data to determine effective strategies for future campaigns. The initial steps are as follows:

- Run the provided “Bank-Marketing.ipynb” notebook to understand the dataset.
- Access your Amazon Academy space for the “AWS Academy Machine Learning Foundations” course.
- Start Lab 3.1 - Amazon SageMaker - Creating and importing data.

### Steps for Setting Up a SageMaker Notebook Instance:

1. On the Amazon Web Services console, navigate to Amazon SageMaker and create a new notebook instance.
2. Once the instance is 'InService', launch JupyterLab and create a new notebook called “Bank-Marketing-processing.ipynb”.

### Data Processing Steps in the Notebook:

1. Download and extract the dataset.
2. Load the data with Pandas.
3. Upload the dataset to Amazon S3 using SageMaker's default bucket.
4. Focus on creating a preprocessing script without worrying about infrastructure and S3 paths.
5. Run the preprocessing script using SKLearnProcessor on a selected instance.
6. Review the output and save processed datasets to S3.
7. Verify the job status and examine the script outputs.
8. Use the AWS CLI to retrieve the processed datasets.

## 2. Training a Model using SageMaker SDK with Built-in Algorithms

The second part of the lab involves training a regression model using SageMaker's built-in algorithms on the Boston Housing dataset.

### 2.1 Data Preparation:

- Load the dataset.
- Reformat it as required by SageMaker (CSV without headers and target variable in front).
- Split the dataset into training and testing partitions.
- Save the partitions as CSV files.
- Upload the CSV files to Amazon S3.

### 2.2 Configure the Training Job:

- Find the SageMaker container for the algorithm (Linear Learner) using boto3.
- Set up the Estimator object with the container, specifying the instance type and output path.
- Define hyperparameters and data channels for training and validation.

### 2.3 Running the Training Job:

- Execute the training job using the `fit()` method.
- Monitor the job in the SageMaker console.
- View the trained model artifact in the output location on S3.

### 2.4 Deploy the Model:

- Create a unique endpoint name and deploy the model.
- Predict outputs using the `predict()` method.
- Alternatively, use the `runtime` object and `invoke_endpoint()` function for predictions.
- Clean up resources by deleting the endpoint to avoid additional charges.

## XGBoost Notebook Description
The lab also includes training an XGBoost model, a powerful and efficient implementation of gradient-boosted trees designed for speed and performance. The notebook demonstrates:

- Loading the housing dataset and preparing it following SageMaker's data format requirements.
- Uploading the processed data to Amazon S3.
- Configuring the XGBoost model with appropriate hyperparameters for the regression task.
- Running the training job and deploying the model to a SageMaker endpoint.
- Using the model to make predictions and evaluating its performance.

---

This lab provides hands-on experience with Amazon SageMaker for processing data, training models, and making predictions. It is designed to guide you through using SageMaker's powerful features to ease the machine learning lifecycle process from data preprocessing to model deployment.

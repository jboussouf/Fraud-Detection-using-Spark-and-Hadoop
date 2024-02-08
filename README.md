# Fraud Detection using Spark and Hadoop
## Overview
This project aims to develop a machine learning model for fraud detection using Apache Spark, Hadoop, and Scala. The implementation includes setting up a scalable environment, pre-processing massive datasets, and training a Logistic Regression model to identify fraudulent activities.
## Table of Contents
- Introduction
- Technologies Used
- Environment Setup
- Data Pre-processing and Analysis
- Model Training
- Evaluation Metrics
- Usage
- Contributing
## Introduction

Fraud detection is a critical aspect of data analytics, especially when dealing with massive datasets. This project utilizes Apache Spark, Hadoop, and Scala to create an environment capable of handling large-scale data processing. The machine learning model is implemented using Spark's MLlib library, and Logistic Regression is chosen as the classification algorithm for fraud detection.

## Technologies Used
- Apache Spark
- Hadoop
- Scala
- Docker

## Environment Setup

To set up the environment, follow these steps:
1. Pull the Docker image:
   
   ```bash
    docker pull liliasfaxi/spark-hadoop:hv-2.7.2
  ```

2. Create Docker network:

   ```bash
    docker network create --driver=bridge hadoop
  ```
3. Run Hadoop containers::

   ```bash
    docker run -itd --net=hadoop -p 50070:50070 -p 8088:8088 -p 7077:7077 -p 16010:16010 --name hadoop-master --hostname hadoop-master liliasfaxi/spark-hadoop:hv-2.7.2
  ```
4. Access Hadoop master container:

   ```bash
    docker exec -it hadoop-master bash
  ```
## Data Pre-processing and Analysis
The Spark Scala script (preprocessing_and_modeling.scala) reads a CSV dataset, performs data pre-processing, and trains a Logistic Regression model for fraud detection. It includes steps for data conversion, indexing, feature engineering, downsampling, and model training.

## Model Training
The chosen algorithm for fraud detection is Logistic Regression, implemented using Spark MLlib. The model is trained on a downsampled dataset to handle class imbalance.
## Evaluation Metrics
Evaluation metrics such as precision, recall, false positive rate, and F1-score are calculated to assess the model's performance. The confusion matrix and micro/macro-level metrics are printed for detailed analysis.
## Usage
1. Ensure that Docker, Spark, Hadoop, and Scala are installed.
2. Run the provided Spark Scala script:
   ```bash
     spark-shell -i preprocessing_and_modeling.scala
   ```
## Contributing
Contributions are welcome! Feel free to open issues or submit pull requests.




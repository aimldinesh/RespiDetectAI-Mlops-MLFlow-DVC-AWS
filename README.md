# RespiDetectAI-MLFlow-DVC-AWS
## Introduction
I'm excited to share a project I worked on that addresses a critical challenge in healthcare: early and accurate diagnosis of chest cancer. I developed a tool that leverages the power of artificial intelligence to classify CT scan images, potentially improving patient outcomes.
## Problem Statement
Chest cancer is a leading cause of cancer deaths worldwide. Early detection is crucial for effective treatment, but traditional methods of analyzing CT scans can be time-consuming and prone to human error. My goal was to create a more efficient and accurate diagnostic tool.
## Approach
I used a technique called deep learning, which excels at recognizing patterns in images. I trained a model on a dataset of CT scans, teaching it to distinguish between normal and cancerous tissue. I also incorporated MLOps principles to streamline the model's development, deployment, and monitoring.
## Key Accomplishments
I'm proud to say that my model achieved an accuracy of 84% in classifying adenocarcinoma, a common type of chest cancer. This is a significant improvement over traditional methods. It also demonstrates the potential of AI to transform healthcare.
![Alt text](https://github.com/dsml917/RespiDetectAI-Mlops-MLFlow-DVC-AWS/blob/main/prediction_images/data_pipeline.PNG)
![Alt text](https://github.com/dsml917/RespiDetectAI-Mlops-MLFlow-DVC-AWS/blob/main/prediction_images/capture1.PNG)
![Alt text](https://github.com/dsml917/RespiDetectAI-Mlops-MLFlow-DVC-AWS/blob/main/prediction_images/Capture2.PNG)
![Alt text](https://github.com/dsml917/RespiDetectAI-Mlops-MLFlow-DVC-AWS/blob/main/prediction_images/experiment.PNG)
![Alt text]

## Steps
### Data Collection :
#### Download data :
The initial step involved downloading images. This dataset served as the foundation for our training and testing sets.

#### Transfer to Google Drive :
Recognizing the importance of centralized and collaborative data storage, the dataset was then transferred to Google Drive. This approach not only enhanced accessibility for team members but also streamlined the integration of the dataset into our MLOps pipeline.

### Data Ingestion :
Extracted data, organized it by labeling or categorizing it, and stored the processed dataset as a versioned data artifact. This structured approach ensures consistency for subsequent stages in our MLOps pipeline.

### Model Building :
Base Model with Transfer Learning:
To establish a robust foundation for our adenocarcinoma cancer classification model, we adopted a transfer learning approach using the VGG16 architecture with pre-trained weights from ImageNet. Leveraging the knowledge encoded in these weights enhances the model's ability to extract relevant features from histopathological images.

### Training on Dataset:
The base model was then fine-tuned and trained on our carefully prepared dataset. This process involved optimizing the model's parameters to adapt it specifically to the task of adenocarcinoma classification. The transfer learning strategy, coupled with training on our dataset, enables the model to learn intricate patterns and features associated with adenocarcinoma pathology.

### Model Evaluation:
#### Loss:
The loss metric gauges the disparity between predicted and actual values during the model training process. Lower values indicate better alignment between predicted and ground truth labels. We get  "loss": 1.1983329057693481

#### Accuracy:
Accuracy measures the model's correctness in predicting adenocarcinoma classification. It is the ratio of correctly predicted samples to the total number of samples. we get "accuracy": 0.843137264251709.

### Logging with MLflow and DVC:
#### MLFlow:
MLflow was employed to track and log key metrics, hyperparameters, and model artifacts during the evaluation phase. This ensures comprehensive visibility into the model's performance and facilitates experiment reproducibility.
+ MLFLOW_TRACKING_URI=
+ MLFLOW_TRACKING_USERNAME=
+ MLFLOW_TRACKING_PASSWORD=
+ python script.py
+ Run this to export as env variables:
 + export MLFLOW_TRACKING_URI=
 + export MLFLOW_TRACKING_USERNAME=
 + export MLFLOW_TRACKING_PASSWORD=

#### DVC (Data Version Control)
DVC played a crucial role in version controlling the datasets, ensuring that the evaluation metrics were associated with specific dataset versions. This enhances traceability and reproducibility, fundamental aspects of a robust MLOps workflow.
#### DVC Commond
 + dvc init
 + dvc repro
 + dvc dag

## User Interface:
WE build a user-friendly interface for the adenocarcinoma cancer classification project using Flask.

### Dockerizing the Web App
Package the Flask web app and its dependencies into a Docker container for consistent deployment. Making it easier to manage dependencies and deploy the application across different environments.

# Deployment AWS-CICD-with-Github-Actions
## 1. Login to AWS console.
## 2. Create IAM user for deployment
## Deployment:
+ 1. EC2 access : It is virtual machine
+ 2. ECR: Elastic Container registry to save your docker image in aws
### Amazon Elastic Container Registry (ECR):
Build the Docker image for the Flask web app, and push it to AWS ECR for storage and easy access.

### Amazon EC2 Instances:
Launch one or more EC2 instances, specifying the Amazon Machine Image (AMI) and instance type suitable for your application.

### Docker Installation on EC2:
Connect to the EC2 instances and install Docker to enable them to run the Dockerized Flask web app.

### Run Docker Container on EC2:
Pull the Docker image from ECR onto the EC2 instance and run the Flask web app.
## 3. Create ECR repo to store/save docker image
## 4. Create EC2 machine (Ubuntu)
## 5. Open EC2 and Install docker in EC2 Machine:
### It is optional

+ sudo apt-get update -y

+ sudo apt-get upgrade

### It is required

+ curl -fsSL https://get.docker.com -o get-docker.sh

+ sudo sh get-docker.sh

+ sudo usermod -aG docker ubuntu

+ newgrp docker

## 6. Configure EC2 as self-hosted runner:
setting>actions>runner>new self hosted runner> choose os> then run command one by one
## 7. Setup github secrets:
+ AWS_ACCESS_KEY_ID=

+ AWS_SECRET_ACCESS_KEY=

+ AWS_REGION = us-east-1

+ AWS_ECR_LOGIN_URI = demo>>  566373416292.dkr.ecr.ap-south-1.amazonaws.com

+ ECR_REPOSITORY_NAME = simple-app

## Technologies Used
+ Python
+ AWS (EC2 & ECR)
+ Tensorflow
+ Docker
+ Flask
+ MLFLow
+ DVC (Data Version Control)
+ Dagshub
+ Github Actions
+ Transfer Learning

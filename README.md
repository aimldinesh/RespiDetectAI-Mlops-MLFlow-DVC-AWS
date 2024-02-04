# RespiDetectAI-MLFlow-DVC-AWS

## Problem Statement
Chest cancer remains a significant global health challenge, with early detection and type classification being crucial for effective treatment. One detection method involves analyzing CT scan images, which can then be interpreted by doctors to determine the presence and type of lung cancer. However, this method has limitations; human interpretation may miss subtle patterns indicative of early-stage chest cancer. In contrast, deep learning models offer a promising avenue in this matter, excelling in recognizing intricate patterns and identifying subtle abnormalities not easily observable through other methods. Another advantage is that they automatically learn relevant features from data, eliminating the need for manual feature engineering, which is particularly useful in medical imaging where defining explicit features can be complex. 
We use a dataset containing CT scan images of the chest categorized as normal and adenocarcinoma. Traditional cancer classification methods suffer from subjectivity, time-intensive processes, and a crucial need for automation. By adopting MLOps principles, we address these challenges by optimizing the end-to-end pipeline, encompassing model training, deployment, and continuous monitoring. Our goal is to provide healthcare professionals with a scalable, reproducible, and efficient tool for adenocarcinoma diagnosis, ultimately enhancing patient care and treatment outcomes.



## Approach
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
Develop a user-friendly interface for the adenocarcinoma cancer classification project using Flask.

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
#optinal

+ sudo apt-get update -y

+ sudo apt-get upgrade

#required

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

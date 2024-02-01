# RespiDetectAI-MLFlow-DVC-AWS

### Introduction:


## Problem Statement


## Approach
### Data Collection :
#### Download from Kaggle :
The initial step involved downloading histopathological images pertinent to adenocarcinoma from Kaggle. This dataset served as the foundation for our training and testing sets.

#### Transfer to Google Drive :
Recognizing the importance of centralized and collaborative data storage, the dataset was then transferred to Google Drive. This approach not only enhanced accessibility for team members but also streamlined the integration of the dataset into our MLOps pipeline.

### Data Ingestion :
Extracted data, organized it by labeling or categorizing, and stored the processed dataset as a versioned data artifact. This structured approach ensures consistency for subsequent stages in our MLOps pipeline.

### Model Building :
Base Model with Transfer Learning:
To establish a robust foundation for our adenocarcinoma cancer classification model, we adopted a transfer learning approach using the VGG16 architecture with pre-trained weights from ImageNet. Leveraging the knowledge encoded in these weights enhances the model's ability to extract relevant features from histopathological images.

### Training on Dataset:
The base model was then fine-tuned and trained on our carefully prepared dataset. This process involved optimizing the model's parameters to adapt it specifically to the task of adenocarcinoma classification. The transfer learning strategy, coupled with training on our dataset, enables the model to learn intricate patterns and features associated with adenocarcinoma pathology.

### Model Evaluation:
#### Loss:
The loss metric gauges the disparity between predicted and actual values during the model training process. Lower values indicate better alignment between predicted and ground truth labels.

#### Accuracy:
Accuracy measures the model's correctness in predicting adenocarcinoma classification. It is the ratio of correctly predicted samples to the total number of samples.

### Logging with MLflow and DVC:
#### MLFlow:
MLflow was employed to track and log key metrics, hyperparameters, and model artifacts during the evaluation phase. This ensures comprehensive visibility into the model's performance and facilitates experiment reproducibility.

#### DVC (Data Version Control)
DVC played a crucial role in version controlling the datasets, ensuring that the evaluation metrics were associated with specific dataset versions. This enhances traceability and reproducibility, fundamental aspects of a robust MLOps workflow.

## User Interface:
Develop a user-friendly interface for the adenocarcinoma cancer classification project using Flask.

### Dockerizing the Web App
Package the Flask web app and its dependencies into a Docker container for consistent deployment. Making it easier to manage dependencies and deploy the application across different environments.

## Deployment:
### Amazon Elastic Container Registry (ECR):
Build the Docker image for the Flask web app, and push it to AWS ECR for storage and easy access.

### Amazon EC2 Instances:
Launch one or more EC2 instances, specifying the Amazon Machine Image (AMI) and instance type suitable for your application.

### Docker Installation on EC2:
Connect to the EC2 instances and install Docker to enable them to run the Dockerized Flask web app.

### Run Docker Container on EC2:
Pull the Docker image from ECR onto the EC2 instance and run the Flask web app.

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

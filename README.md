# TextClassificationAzureML

## Introduction
The purpose of this project is to develop natural language processing models using Azure Machine Learning services.

## AutoML in Azure Machine Learning
- Automates machine learning model development 
- Used to train and tune a model against a target metric you specify
- Low code / no code

<img src="https://user-images.githubusercontent.com/22310955/185616697-3792dbe8-99de-473f-9851-0d248940c208.png" width="600">

### NLP capability in AutoML
- Deep neural network training with pre-trained BERT models
- Integration with Azure ML data labelling
- Multi-lingual support (104 languages)
- Distributed training with Horovod

## Text Classification Implementation using AutoML

### Prerequisites
- Azure Machine Learning studio workspace
- Dataset to train and validate

### 1. Upload or select dataset
Under “Automated ML” section, create New Automated ML Job

<img src="https://user-images.githubusercontent.com/22310955/185617195-568561c9-6e8d-4afe-999f-0f93c8bfd263.png" width="600">

Select data asset either from existing data assets, or upload your own in the form of:
- Local files
- Datastore
- Web files
- Open datasets

<img src="https://user-images.githubusercontent.com/22310955/185617301-eefd8313-c916-4d0e-897b-751690a30f2e.png" width="600">

### 2. Configure Job
Create a new experiment (process):
- Choose a **target column** that the model will be trained to predict
- Choose or create compute instance or cluster with GPU

<img src="https://user-images.githubusercontent.com/22310955/185617959-6427ba0f-91ce-491d-aa3d-d8faab994b41.png" width="600">

### 3. Select Task and Settings

Select NLP as machine learning task:

<img src="https://user-images.githubusercontent.com/22310955/185622961-3b40d68c-2b88-4438-941a-50727e2e711f.png" width="600">

NLP Task Types:
- Multi-class classification (predict a single label amongst a list of classes)
- Multi-label classification (predictions can have multiple labels)

Additional configurations:
- Primary metric (the metric you want the model to be optimized for, i.e., Accuracy)
- Maximum training time
- Metric score threshold (job stops if a model meets this primary metric value)
- Max concurrent iterations (limit number of parallel executions for models)

<img src="https://user-images.githubusercontent.com/22310955/185625610-d5da773c-028c-4afc-9e31-433a7fe74a46.png" width="600">

### 4. Validate and Test

<img src="https://user-images.githubusercontent.com/22310955/185625841-5809a445-7562-40ac-95e8-2876d7d31303.png" width="600">

- Validation data is required
- Test data currently not supported
- Data asset selection similar to step 1

## Example: Text Cateogrization using Reuters 21578 dataset

Reference Paper: [Text Categorization via Similarity Search](https://arxiv.org/pdf/1307.2669.pdf)

### The Reuters 21578 Dataset
- Consists of documents from the Reuters newswire in 1987 used as a benchmark for text classifier algorithms
- Only used single-labelled documents from the top 8 most frequent classes (R8 subset)

## End to End Machine Learning Project
# End-to-End Student Performance Prediction

An end-to-end Machine Learning project that predicts **student mathematics performance** based on demographic, academic, and preparation-related factors. The project demonstrates a production-oriented ML workflow covering data ingestion, preprocessing, model training, evaluation, prediction, and deployment through a Flask web application.

## Project Overview

The project takes raw student data through a modular Machine Learning pipeline and produces predictions through a web-based interface.

The pipeline is designed using a **modular, object-oriented architecture**, separating data ingestion, transformation, model training, prediction, logging, and exception handling into independent components.

### ML Pipeline

```text
Raw Dataset
     │
     ▼
Data Ingestion
     │
     ├── Raw Data
     ├── Train Data
     └── Test Data
     │
     ▼
Data Transformation
     │
     ├── Missing Value Handling
     ├── Categorical Encoding
     └── Feature Preprocessing
     │
     ▼
Model Training
     │
     ├── Multiple ML Models
     ├── Hyperparameter Tuning
     └── Model Evaluation
     │
     ▼
Best Performing Model
     │
     ▼
Prediction Pipeline
     │
     ▼
Flask Web Application
```

## Key Features

* Modular end-to-end Machine Learning pipeline
* Object-Oriented Programming based project structure
* Automated train-test data ingestion
* Separate data transformation pipeline
* Categorical feature encoding and numerical preprocessing
* Multiple Machine Learning models for comparison
* Hyperparameter tuning and model evaluation
* Serialized preprocessing and trained model artifacts
* Custom exception handling
* Centralized logging
* Flask-based prediction application
* Reproducible project environment using `requirements.txt`

## Tech Stack

**Programming & Data Analysis**

* Python
* Pandas
* NumPy

**Machine Learning**

* Scikit-learn
* CatBoost
* XGBoost

**Visualization**

* Matplotlib
* Seaborn

**Deployment**

* Flask

**Development Tools**

* Git
* GitHub
* VS Code
* Python Virtual Environment

## 📁 Project Structure

```text
ML_Project/
│
├── artifact/
│   ├── data.csv
│   ├── train.csv
│   ├── test.csv
│   └── preprocessor.pkl
│
├── notebook/
│   └── data/
│       └── stud.csv
│
├── src/
│   ├── components/
│   │   ├── data_ingestion.py
│   │   ├── data_transformation.py
│   │   └── model_trainer.py
│   │
│   ├── pipeline/
│   │   ├── predict_pipeline.py
│   │   └── train_pipeline.py
│   │
│   ├── exception.py
│   ├── logger.py
│   └── utils.py
│
├── templates/
│   ├── index.html
│   └── home.html
│
├── app.py
├── requirements.txt
├── setup.py
└── README.md
```

## Dataset

The project uses student performance data containing demographic, socioeconomic, and academic preparation features.

Example input features include:

* Gender
* Race/Ethnicity
* Parental Level of Education
* Lunch Type
* Test Preparation Course
* Reading Score
* Writing Score

The target variable is the student's **Mathematics Score**.

## Machine Learning Workflow

### 1. Data Ingestion

The raw dataset is loaded and divided into training and testing datasets.

```text
stud.csv
   │
   ├── 80% → train.csv
   └── 20% → test.csv
```

The ingestion component also creates the required artifact directory and stores the raw dataset for reproducibility.

### 2. Data Transformation

The transformation pipeline prepares the data for Machine Learning by handling preprocessing requirements such as:

* Numerical feature processing
* Categorical feature encoding
* Missing value handling
* Feature transformation

The preprocessing pipeline is serialized so that the **same transformations used during training can be applied during prediction**.

### 3. Model Training

Multiple Machine Learning algorithms are evaluated and compared.

The project uses models from libraries including:

* Scikit-learn
* CatBoost
* XGBoost

Hyperparameter configurations are evaluated to identify the best-performing model.

### 4. Prediction Pipeline

The prediction pipeline accepts user input from the web application, converts it into a DataFrame, applies the saved preprocessing pipeline, and generates a prediction using the trained model.

### 5. Web Application

A Flask application provides a simple interface through which users can enter student information and receive a predicted mathematics score.

```text
User Input
    ↓
Flask
    ↓
CustomData
    ↓
Prediction Pipeline
    ↓
Preprocessor
    ↓
Trained Model
    ↓
Predicted Math Score
```

## Software Engineering Practices

This project goes beyond simply training a Machine Learning model and includes several software engineering practices:

* **Modular architecture** — individual ML stages are separated into components.
* **Object-Oriented Programming** — components and configurations are organized using classes and objects.
* **Configuration management** — paths and component configurations are separated from processing logic.
* **Logging** — important pipeline operations are recorded for debugging and monitoring.
* **Custom exception handling** — project-specific errors are captured and reported.
* **Pipeline-based prediction** — training and inference use consistent preprocessing.
* **Version control** — source code is maintained using Git and GitHub.

## Installation & Setup

### 1. Clone the repository

```bash
git clone <YOUR_GITHUB_REPOSITORY_URL>
cd ML_Project
```

### 2. Create a virtual environment

```bash
python -m venv .venv
```

### 3. Activate the environment

**Windows PowerShell:**

```bash
.venv\Scripts\Activate.ps1
```

### 4. Install dependencies

```bash
pip install -r requirements.txt
```

### 5. Run the training pipeline

```bash
python src/components/data_ingestion.py
```

### 6. Start the Flask application

```bash
python app.py
```

Open the application at:

```text
http://127.0.0.1:5000/
```

## Project Objective

The primary objective of this project is to demonstrate the complete lifecycle of a Machine Learning solution — from raw data ingestion and preprocessing to model selection, prediction, and deployment through a web interface.

Rather than treating Machine Learning as an isolated model-training task, the project focuses on building a **structured, modular, and reusable ML application**.

## Future Improvements

Potential improvements include:

* Cloud deployment
* CI/CD integration
* Docker containerization
* Model monitoring
* Experiment tracking
* Automated testing
* REST API deployment
* Improved frontend interface




Below is a **clean, technical, GitHub-ready README.md** designed to **showcase your DevOps + MLOps + Cloud engineering skills**.
It highlights **architecture, tools, CI/CD, cloud, ML pipeline, Docker, AWS, MongoDB, GitHub Actions**, etc — which **recruiters and engineers look for**.

You can directly paste this into **README.md**.

---

# 🚗 End-to-End MLOps Vehicle Prediction Pipeline

A **production-grade MLOps project** demonstrating how to build, train, deploy, and automate a Machine Learning system using modern **DevOps + MLOps + Cloud practices**.

This project implements a **complete ML lifecycle**, including:

* Data ingestion from **MongoDB Atlas**
* Data validation and transformation
* Model training and evaluation
* Model versioning in **AWS S3**
* Docker containerization
* CI/CD using **GitHub Actions**
* Deployment on **AWS EC2**
* Automated pipeline execution

---

# 🧠 Architecture Overview

```
                 ┌─────────────────────┐
                 │   MongoDB Atlas     │
                 │   Dataset Storage   │
                 └──────────┬──────────┘
                            │
                            ▼
                ┌─────────────────────┐
                │   Data Ingestion    │
                └──────────┬──────────┘
                           ▼
                ┌─────────────────────┐
                │  Data Validation    │
                └──────────┬──────────┘
                           ▼
                ┌─────────────────────┐
                │ Data Transformation │
                └──────────┬──────────┘
                           ▼
                ┌─────────────────────┐
                │   Model Training    │
                └──────────┬──────────┘
                           ▼
                ┌─────────────────────┐
                │  Model Evaluation   │
                └──────────┬──────────┘
                           ▼
                ┌─────────────────────┐
                │   Model Registry    │
                │     AWS S3          │
                └──────────┬──────────┘
                           ▼
                 ┌───────────────────┐
                 │   Flask App API   │
                 └──────────┬────────┘
                            ▼
                   Docker Container
                            ▼
                       AWS EC2
                            ▼
                  CI/CD via GitHub Actions
```

---

# ⚙️ Tech Stack

### Programming

* Python 3.10
* Flask
* Jupyter Notebook

### Machine Learning

* Scikit-Learn
* Pandas
* Numpy

### Database

* MongoDB Atlas

### Cloud

* AWS S3
* AWS EC2
* AWS ECR
* AWS IAM

### DevOps

* Docker
* GitHub Actions
* Self Hosted Runner

### Configuration & Packaging

* `setup.py`
* `pyproject.toml`
* Virtual Environment (Conda)

---

# 📂 Project Structure

```
vehicle_project
│
├── notebook/
│   ├── mongoDB_demo.ipynb
│   ├── EDA.ipynb
│
├── src/
│   ├── components/
│   │    ├── data_ingestion.py
│   │    ├── data_validation.py
│   │    ├── data_transformation.py
│   │    ├── model_trainer.py
│   │    ├── model_evaluation.py
│   │    └── model_pusher.py
│   │
│   ├── configuration/
│   │    ├── mongo_db_connection.py
│   │    └── aws_connection.py
│   │
│   ├── data_access/
│   │    └── proj1_data.py
│   │
│   ├── entity/
│   │    ├── config_entity.py
│   │    ├── artifact_entity.py
│   │    ├── estimator.py
│   │    └── s3_estimator.py
│   │
│   ├── utils/
│   │    └── main_utils.py
│
├── pipeline/
│    ├── training_pipeline.py
│    └── prediction_pipeline.py
│
├── static/
├── templates/
│
├── app.py
├── demo.py
├── requirements.txt
├── setup.py
├── pyproject.toml
├── Dockerfile
└── README.md
```

---

# 🚀 Environment Setup

Create and activate environment:

```bash
conda create -n vehicle python=3.10 -y
conda activate vehicle
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Verify packages:

```bash
pip list
```

---

# 📦 Local Package Setup

Local packages are imported using:

```
setup.py
pyproject.toml
```

Install project as package:

```bash
pip install -e .
```

---

# 🍃 MongoDB Atlas Setup

1️⃣ Create MongoDB Atlas account
2️⃣ Create project and cluster (M0 free tier)
3️⃣ Create DB user
4️⃣ Allow network access:

```
0.0.0.0/0
```

5️⃣ Get connection string

Example:

```
mongodb+srv://<username>:<password>@cluster.mongodb.net
```

---

# 🔐 Environment Variables

### MongoDB

Linux / Mac

```bash
export MONGODB_URL="mongodb+srv://username:password..."
```

Windows PowerShell

```powershell
$env:MONGODB_URL="mongodb+srv://username:password..."
```

---

# 📊 Data Pipeline Components

## 1️⃣ Data Ingestion

* Fetch data from MongoDB
* Convert JSON documents to Pandas DataFrame
* Store raw data artifact

---

## 2️⃣ Data Validation

* Schema validation
* Missing values detection
* Data drift validation

---

## 3️⃣ Data Transformation

* Feature engineering
* Data preprocessing
* Feature scaling
* Pipeline creation

---

## 4️⃣ Model Trainer

* Train ML model
* Hyperparameter tuning
* Model serialization

---

## 5️⃣ Model Evaluation

Compares:

```
Existing model vs New model
```

Using threshold:

```
MODEL_EVALUATION_CHANGED_THRESHOLD_SCORE = 0.02
```

---

## 6️⃣ Model Pusher

Pushes trained model to:

```
AWS S3 Model Registry
```

---

# ☁️ AWS Setup

### IAM

Create user:

```
firstproj
```

Attach policy:

```
AdministratorAccess
```

Generate access keys.

---

### Environment Variables

Linux:

```bash
export AWS_ACCESS_KEY_ID=""
export AWS_SECRET_ACCESS_KEY=""
```

PowerShell:

```powershell
$env:AWS_ACCESS_KEY_ID=""
$env:AWS_SECRET_ACCESS_KEY=""
```

---

# 🪣 AWS S3 Model Registry

Create bucket:

```
my-model-mlopsproj
```

Used for:

* Model versioning
* Model registry
* Artifact storage

---

# 🐳 Docker Setup

Build Docker image:

```bash
docker build -t vehicleproj .
```

Run container:

```bash
docker run -p 5080:5080 vehicleproj
```

---

# 🔁 CI/CD Pipeline

CI/CD implemented using **GitHub Actions**.

Pipeline stages:

```
Code Commit
      ↓
Build Docker Image
      ↓
Push Image to AWS ECR
      ↓
Deploy to EC2
      ↓
Run Application
```

---

# 🖥️ AWS Deployment

### EC2 Setup

Instance:

```
Ubuntu 24.04
t2.medium
```

Install Docker:

```bash
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
```

Add docker permissions:

```bash
sudo usermod -aG docker ubuntu
```

---

# 🔗 GitHub Self Hosted Runner

Steps:

```
Github Repo
 → Settings
 → Actions
 → Runner
 → New Self Hosted Runner
```

Run commands on EC2:

```
./config.sh
./run.sh
```

---

# 🔐 GitHub Secrets

Add following secrets:

```
AWS_ACCESS_KEY_ID
AWS_SECRET_ACCESS_KEY
AWS_DEFAULT_REGION
ECR_REPO
```

---

# 🌐 Application Access

Allow port on EC2:

```
Port 5080
```

Access application:

```
http://<EC2-PUBLIC-IP>:5080
```

---

# 🧪 Training Endpoint

Trigger model training:

```
http://<EC2-IP>:5080/training





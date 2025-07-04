# 🚀 Hotel Reservation Prediction

This project demonstrates a full MLOps pipeline from raw data to a production-ready ML application. It incorporates industry-standard tools and practices, including model training, versioning, experiment tracking, and CI/CD deployment.

**Medium** - [https://medium.com/@doye.n/%EF%B8%8Fbuilding-production-ready-ml-systems-with-gcp-lessons-from-my-mlops-prediction-application-7c7b0fe7d8b1]

---

## 📌 Workflow Overview

Database Setup → Project Setup → Data Ingestion → Jupyter Notebook Testing 
→ Data Processing → Model Training → Experiment Tracking 
→ Training Pipeline → Data & Code Versioning 
→ User App Building → CI/CD Deployment → DONE ✅

---

## 📂 1. Project Setup

- **Database**: Cloud storage buckets (e.g., GCP buckets)
- **Structure**: Modular and scalable folder architecture

---

## 🔄 2. Data Workflow

- **Data Ingestion**: Raw data is pulled from source systems and stored.
- **Notebook Testing**: Quick experimentation and sanity checks using Jupyter notebooks.
- **Data Processing**: Cleaning, feature engineering, and transformation.

---

## 🧠 3. Model Development

- **Model Training**: Custom training scripts for ML models.
- **Training Pipeline**: Automates the process using modular code blocks.

---

## 🧪 4. Experiment Tracking

- **Tool**: MLflow is used to track parameters, metrics, and models.
- Track performance across multiple training runs and model iterations.

---

## 📦 5. Version Control

- **Data Versioning**: Ensures reproducibility of datasets.
- **Code Versioning**: Git-based version control with structured commits.

---

## 🌐 6. User App Building

- **Stack**:
  - Flask for backend
  - HTML for UI
  - Integrated ChatGPT (optional interactive feature)

---

## ⚙️ 7. CI/CD Deployment

- **Tools**:
  - Jenkins
  - Docker
  - Google Cloud Platform (GCP)
  - Google Cloud Run

---

## 🐳 Docker-in-Docker (DinD) Usage

To enable dynamic and containerized builds within the CI/CD pipeline, this project leverages **Docker-in-Docker (DinD)** in Jenkins:

### 🔧 Why DinD?

- Allows Jenkins agents to **build, run, and push Docker images** as part of the pipeline.
- Ensures each build runs in **isolated containers**, avoiding interference from other builds.
- Simplifies deployment by allowing end-to-end container lifecycle management inside Jenkins.

### 🛠️ How It Works

- Jenkins spins up a containerized agent that has Docker installed.
- That agent itself **runs Docker inside Docker** to build the ML app container.
- The container is then pushed to a **Docker registry** or deployed directly to **Google Cloud Run**.

---


## ✅ 8. Final Output

A fully automated, scalable, and reproducible ML pipeline, ending in a deployed ML-powered application.

---

## 💡 Future Improvements

- Add monitoring (e.g., Prometheus, Grafana)
- Improve data validation from an input perspective
- Integrate advanced model retraining schedules

---

## 📬 Feedback

Feel free to fork, open issues, or contribute!

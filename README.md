# Vehicle Project

## Overview
Vehicle Project is an end-to-end machine learning application covering data ingestion, transformation, model training, evaluation, and deployment. It integrates modern MLOps best practices, cloud computing, and automation for scalability and efficiency.

## Key Features

- **Project Setup & Packaging**
  - Automated project template generation (`template.py`)
  - Local package management with `setup.py` and `pyproject.toml`

- **Environment & Dependency Management**
  - Virtual environment setup using Conda (Python 3.10)
  - Dependency installation via `requirements.txt`

- **MongoDB Atlas Integration**
  - Cloud database setup and management
  - Data ingestion and transformation using `mongoDB_demo.ipynb`

- **Logging & Exception Handling**
  - Custom logging and exception handling in `demo.py`
  - Modular EDA and feature engineering components

- **Data Pipeline Components**
  - Data ingestion, validation, transformation, and training
  - Schema-driven validation via `config.schema.yaml`
  - AWS S3 integration for model storage

- **Cloud & Deployment**
  - AWS (S3, EC2, IAM, ECR) for cloud-based storage and computing
  - Docker containerization and deployment automation
  - CI/CD pipeline with GitHub Actions and a self-hosted runner

## Technologies Used

- **Programming Language:** Python 3.10
- **Database:** MongoDB Atlas
- **Cloud Services:** AWS (EC2, S3, IAM, ECR)
- **CI/CD Tools:** GitHub Actions, Docker
- **Environment Management:** Conda
- **Visualization & Experimentation:** Jupyter Notebook

## Project Structure

```
├── constants
│   └── __init__.py            # Global constants and configurations
├── configuration
│   └── mongo_db_connections.py  # MongoDB connection functions
├── data_access
│   └── proj1_data.py          # Data fetching and transformation logic
├── components
│   └── data_ingestion.py      # Data ingestion pipeline component
├── entity
│   ├── config_entity.py       # Configuration entities
│   ├── artifact_entity.py     # Artifact entities for model outputs
│   └── s3_estimator.py        # AWS S3 integration
├── utils
│   └── main_utils.py          # Utility functions
├── notebook
│   └── mongoDB_demo.ipynb     # Notebook for MongoDB integration
├── static/                    # Static files for web app
├── template/                  # Project template files
├── Dockerfile                 # Docker configuration
├── .dockerignore              # Files to exclude from Docker build
├── app.py                     # Main application
├── requirements.txt           # Required Python packages
├── setup.py                   # Local package installation
├── pyproject.toml             # Pyproject configuration
├── crashcourse.txt            # Setup reference guide
```

## Setup Instructions

1. **Clone the Repository**
   ```bash
   git clone https://github.com/yourusername/vehicleproj.git
   cd vehicleproj
   ```

2. **Generate Project Template**
   ```bash
   python template.py
   ```

3. **Create and Activate Virtual Environment**
   ```bash
   conda create -n vehicle python=3.10 -y
   conda activate vehicle
   ```

4. **Install Dependencies**
   ```bash
   pip install -r requirements.txt
   ```

5. **MongoDB Atlas Setup**
   - Create a cluster (M0 free tier) and whitelist IP `0.0.0.0/0`.
   - Set environment variable:
     ```bash
     export MONGODB_URL="your_connection_string"
     ```

6. **AWS Setup**
   - Configure IAM user and set credentials:
     ```bash
     export AWS_ACCESS_KEY_ID="your_access_key"
     export AWS_SECRET_ACCESS_KEY="your_secret_key"
     ```

7. **Run Data Pipeline**
   ```bash
   python demo.py
   ```

8. **Deploy the Application**
   ```bash
   docker build -t vehicleproj .
   ```
   - Start the web application:
     ```bash
     python app.py
     ```

## Running the Application

- **Local Development:**
  - Start the app:
    ```bash
    python app.py
    ```

- **Production Deployment:**
  - CI/CD workflow builds, tests, and deploys the app on commits.

## Conclusion

This project demonstrates a full MLOps workflow with cloud services, automation, and best practices, making it scalable and production-ready. Contributions and improvements are welcome!

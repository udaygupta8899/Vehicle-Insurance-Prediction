# 🚗 Vehicle Data Pipeline Project 🚀

## 📌 Overview
This project is a complete **MLOps pipeline** that involves **data ingestion, validation, transformation, model training, and deployment** using **MongoDB, AWS, Docker, and CI/CD** integration with GitHub Actions. It enables **real-time vehicle data processing** and prediction.

## 🎯 Features
✅ **Automated Data Pipeline** - Ingest, validate, and transform vehicle data from MongoDB Atlas.  
✅ **Machine Learning Model Training** - Train models for vehicle data analysis and prediction.  
✅ **Cloud Storage & Deployment** - AWS S3 for model storage, EC2 for deployment.  
✅ **CI/CD Pipeline** - Automated deployment via GitHub Actions and AWS services.  
✅ **Dockerized App** - Containerized for smooth deployment and scaling.  
✅ **Logging & Exception Handling** - Robust logging and error handling for debugging.  

---

## 🏗 Project Setup

### 🔹 Step 1: Create & Activate Virtual Environment
```bash
conda create -n vehicle python=3.10 -y
conda activate vehicle
```

### 🔹 Step 2: Install Dependencies
```bash
pip install -r requirements.txt
```

### 🔹 Step 3: Setup MongoDB Atlas 📦
1️⃣ Sign up at [MongoDB Atlas](https://www.mongodb.com/atlas) & create a new project.  
2️⃣ Create a cluster → Select **M0 Free Tier** → Deploy.  
3️⃣ Create a **DB user** with username & password.  
4️⃣ Set **Network Access** to `0.0.0.0/0` (accessible from anywhere).  
5️⃣ Get the **Connection String** (`mongodb+srv://<username>:<password>@cluster.mongodb.net/`).  

### 🔹 Step 4: Push Data to MongoDB
- Store dataset in the `notebook` folder and load it into **MongoDB Atlas** using `mongoDB_demo.ipynb`.  
- Verify data in **MongoDB Atlas → Browse Collections**.

### 🔹 Step 5: Implement Logging & Exception Handling 📝
- Develop logging in `logger.py` & exception handling in `exception.py`.  
- Test with `demo.py`.

### 🔹 Step 6: Data Ingestion 📥
1️⃣ Define constants in `constants/__init__.py`.  
2️⃣ Set up **MongoDB connection** in `configuration/mongo_db_connections.py`.  
3️⃣ Implement ingestion logic in `data_access/proj1_data.py`.  
4️⃣ Define ingestion config in `entity/config_entity.py`.  
5️⃣ Run `demo.py` to test data ingestion.

### 🔹 Step 7: Setup AWS ☁️
1️⃣ Login to AWS Console → Go to **IAM** → Create user (`firstproj`).  
2️⃣ Attach **AdministratorAccess** policy.  
3️⃣ Generate & download **AWS access keys**.  
4️⃣ Set environment variables:
```bash
export AWS_ACCESS_KEY_ID="your_key"
export AWS_SECRET_ACCESS_KEY="your_secret_key"
export AWS_DEFAULT_REGION="us-east-1"
```
5️⃣ Configure **AWS S3 Bucket** (`my-model-mlopsproj`).

### 🔹 Step 8: Model Training & Evaluation 📊
- Implement `Data Validation`, `Data Transformation`, and `Model Trainer` components.  
- Store trained models in **AWS S3** using `aws_storage/s3_estimator.py`.  

### 🔹 Step 9: Deploy Model with CI/CD 🚀
1️⃣ **Docker Setup:**  
   - Create `Dockerfile` & `.dockerignore`.  
   - Build & test Docker container locally.
2️⃣ **GitHub Actions:**  
   - Create `.github/workflows/aws.yaml` for automation.
3️⃣ **AWS EC2 Setup:**  
   - Create **EC2 Instance** (`vehicledata-machine`).  
   - Install Docker on EC2:
   ```bash
   curl -fsSL https://get.docker.com -o get-docker.sh
   sudo sh get-docker.sh
   ```
4️⃣ **Self-Hosted Runner:**  
   - Connect **EC2 to GitHub Actions** for CI/CD.
5️⃣ **Expose Port for Deployment:**  
   - Open port `5000` in **AWS Security Group**.
6️⃣ **Launch the App:**  
   - Access via `http://<public-ip>:5000` in your browser.

---

## 🤝 Contributing
Contributions are welcome! Feel free to submit a pull request.  

🏡 Real Estate Price Prediction Model

AI-powered Home Price Estimator — Built with Flask, scikit-learn & Deployable on AWS EC2
Predict home prices instantly using a clean ML workflow, a Flask API backend, and a lightweight web UI.
This project demonstrates how to take a real ML model from Jupyter Notebook → Flask API → Cloud Deployment.

📘 Project Overview

This project walks through a complete end-to-end Data Science + Deployment pipeline:
1️⃣ Model Development (Machine Learning)
Trained using the Bengaluru House Prices dataset (Kaggle) with Linear Regression.
Includes:
✔️ Data cleaning & preprocessing
✔️ Outlier detection
✔️ Feature engineering
✔️ Dimensionality reduction
✔️ Hyperparameter tuning (GridSearchCV)
✔️ K-Fold cross-validation
✔️ Model saving via pickle

2️⃣ Flask Backend API
A lightweight Python Flask server that:
Loads trained ML model
Exposes REST endpoints
Accepts JSON inputs
Returns predicted home price

3️⃣ Frontend Website
A simple UI built with:
HTML + CSS + JavaScript
Users can input property details and get predictions in real time via API.

🛠️ Technologies Used
ML & Programming-
Python
NumPy & Pandas
Matplotlib
scikit-learn

Backend-
Flask (REST API)

Frontend-
HTML
CSS
JavaScript

Cloud-

AWS EC2 for hosting

🌟 Key Features

✨ Machine Learning model trained on real data
✨ Flask REST API for predictions
✨ Frontend UI for user inputs
✨ Fast JSON-based communication
✨ Deployable on any cloud — EC2, Render, Railway, etc.

🚀 Ultra-Concise Steps to Deploy ML Model on AWS EC2
1️⃣ Launch EC2 Instance

Ubuntu 22.04 LTS

t2.micro (Free Tier)

Add security rule:
Custom TCP → Port 5000 → 0.0.0.0/0

2️⃣ SSH Into EC2
chmod 400 mykey.pem
ssh -i "mykey.pem" ubuntu@<EC2-PUBLIC-IP>

3️⃣ Install Python & Tools
sudo apt update
sudo apt install python3-pip python3-venv -y

4️⃣ Upload Your Project to EC2

From your local terminal:

scp -i "mykey.pem" -r RealEstateModel/ ubuntu@<ECIP>:/home/ubuntu/

5️⃣ Create Virtual Environment & Install Dependencies
cd RealEstateModel
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt

6️⃣ Update Flask to Run Publicly

In server.py:

app.run(host='0.0.0.0', port=5000)

7️⃣ Run Flask Server in Background
nohup python3 server.py > server.log 2>&1 &


Check status:

sudo lsof -i :5000

8️⃣ Test API

Open:

http://<EC2-PUBLIC-IP>:5000

# 🏡 Real Estate Price Prediction Model  
### _AI-powered Home Price Estimator — Built with Flask & scikit-learn_

Predict home prices instantly using a clean ML workflow, a Flask API backend, and a lightweight web UI.  
This project demonstrates how to take a real ML model **from Jupyter Notebook → Flask API → Cloud Deployment on AWS EC2**.

---

## 📘 Project Overview

This project covers a complete end-to-end **Data Science + Deployment** pipeline:

### **1️⃣ Model Development (Machine Learning)**  
Trained using the **Bengaluru House Prices** dataset (Kaggle) with **Linear Regression**.

Includes:
- Data cleaning & preprocessing  
- Outlier detection  
- Feature engineering  
- Dimensionality reduction  
- Hyperparameter tuning (GridSearchCV)  
- K-Fold cross-validation  
- Model saving via pickle

---

### **2️⃣ Flask Backend API**

A lightweight Flask server that:
- Loads the trained ML model  
- Exposes REST API endpoints  
- Accepts JSON input  
- Returns predicted home prices  

---

### **3️⃣ Frontend Website**

Built using:
- HTML  
- CSS  
- JavaScript  

Allows users to input property details and get instant predictions.

---

## 🛠️ Technologies Used

### Machine Learning & Programming
- Python  
- NumPy  
- Pandas  
- Matplotlib  
- scikit-learn  

### Backend
- Flask (REST API)

### Frontend
- HTML  
- CSS  
- JavaScript  

### Cloud
- AWS EC2

---

## 🌟 Key Features

- ML model trained on real-world data  
- REST API for predictions  
- Simple, responsive UI  
- JSON-based communication  
- Cloud-ready deployment  
- Lightweight & fast  

---

# 🚀 Ultra-Concise Deployment Steps (AWS EC2)

## **1️⃣ Launch EC2 Instance**
- Ubuntu 22.04 LTS  
- t2.micro (Free Tier)  
- Add inbound rule:  
Custom TCP | Port 5000 | 0.0.0.0/0


---

## **2️⃣ SSH Into EC2**
```bash
chmod 400 mykey.pem
ssh -i "mykey.pem" ubuntu@<EC2-PUBLIC-IP>

3️⃣ Install Python & Tools
sudo apt update
sudo apt install python3-pip python3-venv -y

4️⃣ Upload Project to EC2
scp -i "mykey.pem" -r RealEstateModel/ ubuntu@<EC2-PUBLIC-IP>:/home/ubuntu/

5️⃣ Create Virtual Environment & Install Dependencies
cd RealEstateModel
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt

6️⃣ Update Flask to Run Publicly

In server.py:

app.run(host='0.0.0.0', port=5000)

7️⃣ Start Flask Server in Background
nohup python3 server.py > server.log 2>&1 &


Check running process:

sudo lsof -i :5000

8️⃣ Test API

Open in browser:

http://<EC2-PUBLIC-IP>:5000


Test via curl:

curl -X POST http://<EC2-PUBLIC-IP>:5000/predict_home_price \
-H "Content-Type: application/json" \
-d '{"total_sqft":1000, "location":"Whitefield", "bhk":3, "bath":2}'

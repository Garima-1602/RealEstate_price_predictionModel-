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

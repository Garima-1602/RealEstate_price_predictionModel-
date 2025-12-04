🏡 Real Estate Price Prediction Model

A Machine Learning model built with Flask & scikit-learn

This project predicts real estate/home prices based on key features such as square footage, location, number of bedrooms, and bathrooms.
It includes an end-to-end Machine Learning workflow, a Flask backend API, and can be deployed easily on AWS EC2.

📘 Project Overview

This project demonstrates a complete Data Science pipeline, starting from data preprocessing to deployment:

1. Model Development

Using the Bengaluru home prices dataset (Kaggle), the model is built using scikit-learn’s Linear Regression.
The workflow includes:

Data loading & cleaning

Outlier detection & removal

Feature engineering

Dimensionality reduction

Hyperparameter tuning (GridSearchCV)

K-Fold cross-validation

Model saving & pickle serialization

2. Flask Backend

A Python Flask server:

Loads the trained model

Exposes REST endpoints

Takes JSON input from UI or API

Returns predicted price

3. Frontend Website

A simple interface built using:

HTML

CSS

JavaScript

This UI allows users to enter property details and fetch predicted price from the Flask API.

🛠️ Technologies Used
Programming & ML

Python

NumPy & Pandas (data cleaning)

Matplotlib (visualization)

scikit-learn (model building)

Development Tools

Jupyter Notebook

VS Code / PyCharm

Backend

Python Flask (REST API server)

Frontend

HTML

CSS

JavaScript

Cloud Deployment

AWS EC2

⭐ Features

ML model trained with scikit-learn

REST API endpoint for predictions

Lightweight Flask backend

Frontend UI for user interaction

JSON-based request/response

Easy cloud deployment (AWS EC2)

🚀 Concise Steps to Deploy ML Model on AWS EC2
1. Launch EC2 Instance

Ubuntu 22.04 LTS

Instance type: t2.micro

Add inbound security rule:

Custom TCP → Port 5000 → 0.0.0.0/0

2. SSH Into EC2
chmod 400 mykey.pem
ssh -i "mykey.pem" ubuntu@<EC2-PUBLIC-IP>

3. Install Python Dependencies
sudo apt update
sudo apt install python3-pip python3-venv -y

4. Upload Project to EC2

From your local machine:

scp -i "mykey.pem" -r RealEstateModel/ ubuntu@<EC2-PUBLIC-IP>:/home/ubuntu/

5. Create Virtual Environment
cd RealEstateModel
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt

6. Update Flask to Listen Publicly

In server.py, ensure:

app.run(host='0.0.0.0', port=5000)

7. Start the Server
nohup python3 server.py > server.log 2>&1 &


Check if running:

sudo lsof -i :5000

8. Test the API

Open in browser or Postman:

http://<EC2-PUBLIC-IP>:5000


Test prediction:

curl -X POST http://<EC2-PUBLIC-IP>:5000/predict_home_price \
-H "Content-Type: application/json" \
-d '{"total_sqft":1000, "location":"Whitefield", "bhk":3, "bath":2}'

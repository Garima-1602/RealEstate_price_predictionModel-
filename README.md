REAL ESTATE PRICE PREDICTION MODEL

A Machine Learning model built with Flask & scikit-learn

This project predicts real estate/home prices based on user-given features such as square footage, location, number of bedrooms, and bathrooms.
It includes a fully functional Flask API and can be deployed on AWS EC2.

Additionally,this  project demonstrates an end-to-end Data Science workflow by building a complete Real Estate Price Prediction system.
It includes:

Model Development: Using the Bengaluru home prices dataset from Kaggle, the model is built with scikit-learn and Linear Regression. The process covers data loading, 
cleaning, outlier removal, feature engineering, dimensionality reduction, hyperparameter tuning (GridSearchCV), and K-Fold cross-validation.
Flask Backend: A Python Flask server loads the trained model and exposes HTTP endpoints to return price predictions based on user inputs.
Interactive Website: A frontend built with HTML, CSS, and JavaScript allows users to enter square footage, location, bedrooms, and bathrooms. The UI communicates with the Flask API to display predicted prices.

TECHNOLOGIES USED

Python
NumPy & Pandas (data cleaning)
Matplotlib (visualization)
Scikit-learn (model building)
Jupyter Notebook, VS Code, PyCharm
Flask (API server)
HTML/CSS/JavaScript (frontend UI)
cloud deployement(aws)

FEATURES

Trained ML model using scikit-learn
REST API endpoint for predictions
Lightweight Flask backend
Easy to deploy on EC2
JSON-based request & response

------Concise Steps to Deploy ML Model on AWS EC2------------

1. Launch EC2 Instance

Ubuntu 22.04 LTS
t2.micro
Add inbound security rule:
Custom TCP → Port 5000 → 0.0.0.0/0

2. SSH Into EC2
   
chmod 400 mykey.pem
ssh -i "mykey.pem" ubuntu@<EC2-PUBLIC-IP>

4. Install Python Dependencies
   
sudo apt update
sudo apt install python3-pip python3-venv -y

6. Upload Project

From your local machine:
scp -i "mykey.pem" -r RealEstateModel/ ubuntu@<EC2-PUBLIC-IP>:/home/ubuntu/

5. Create Virtual Environment
   
cd RealEstateModel
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt

7. Update Flask to Listen Publicly

In server.py:
app.run(host='0.0.0.0', port=5000)

7. Start the Server
   
nohup python3 server.py > server.log 2>&1 &
Check it’s running:
sudo lsof -i :5000

8. Test API

Browser or Postman:
http://<EC2-PUBLIC-IP>:5000

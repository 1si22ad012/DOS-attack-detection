 DoS Attack Detection System
DoS attack detection is an intelligent, end-to-end cybersecurity system designed to detect Denial of Service (DoS) attacks using machine learning. It integrates network traffic monitoring, advanced feature engineering, algorithm comparison, and a Django-based web dashboard for real-time interaction and prediction.

⚙️ How It Works


📥 1. Data Collection
Network traffic is captured using Wireshark and saved in .csv format.

The captured data includes both normal and DoS attack traffic patterns.

🧠 2. Feature Engineering
Extracted and preprocessed critical flow-based features using Pandas and NumPy, including:

Flow Duration, Flow_Byts/s, Tot_Fwd_Pkts, Tot_Bwd_Pkts

Fwd_Pkt_Len_Max, Bwd_Pkt_Len_Max, Fwd_IAT_Mean, Bwd_IAT_Mean

SYN_Flag_Cnt, RST_Flag_Cnt, ACK_Flag_Cnt, Flow_Pkts/s

These features help model traffic behavior and differentiate between normal and malicious flows.

🧪 3. Machine Learning Modeling
Trained and evaluated five machine learning algorithms using Scikit-learn:

✅ Random Forest Classifier (Best Overall Performance)

Decision Tree Classifier

K-Nearest Neighbors (KNN)

Multi-layer Perceptron (Neural Network)

LSTM (Long Short-Term Memory, deep learning)

Evaluation Metrics:

Accuracy (Train/Test)

Confusion Matrix

ROC-AUC Scores

Precision, Recall, F1-Score

Feature Importance Analysis

🌐 Web Application Features
A full-stack Django web app with an intuitive interface and RESTful APIs:

📊 User Functionalities
Upload network traffic .csv files
Predict and visualize DoS vs Normal traffic

Download prediction results as CSV

View charts using Chart.js

User authentication system: Sign Up, Login, Password Reset

User prediction history tracking

📦 REST API Endpoints (Django REST Framework)
POST /api/predict/manual/ – Predict using manual JSON input

POST /api/predict/csv/ – Upload CSV, receive bulk predictions with a downloadable file

📈 Result Summary
Model	Accuracy (Test)	ROC AUC Score
✅ Random Forest	Highest	Highest
Decision Tree	High	Good
K-Nearest Neighbors	Moderate	Fair
Neural Network (MLP)	Moderate–High	Fair–Good
LSTM (Deep Learning)	Variable	Good (Time-Series)

📂 Dataset Overview
Training: training_data.csv / updated_dataset.csv

Testing: test_data.csv

Data Format: Captured from Wireshark, cleaned, and engineered via notebook

📓 Jupyter Notebook Highlights
File: Notebook.ipynb

Includes:

EDA (Exploratory Data Analysis)

Feature Engineering & Scaling

Model Comparison

GridSearchCV for hyperparameter tuning

Evaluation & Visualization

Export of final prediction results

🧰 Tech Stack
Layer	Technology
Frontend	HTML, CSS, Bootstrap, Chart.js
Backend	Django, Django REST Framework
ML Frameworks	Scikit-learn, Pandas, NumPy
Data Capture	Wireshark (Real traffic)
Notebook Env	Jupyter Notebook
Deployment	Render (Free Tier)

🧪 How to Run Locally

# Create a virtual environment
python -m venv env
source env/bin/activate  # or env\Scripts\activate on Windows

# Install dependencies
pip install -r requirements.txt

# Apply database migrations
python manage.py migrate

# Run the development server
python manage.py runserver



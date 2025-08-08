Fuel Blend Properties Prediction – Shell.ai Hackathon 2025
📄 Overview
This repository contains the solution for the Shell.ai Hackathon 2025 challenge: Fuel Blend Properties Prediction.
The goal is to build a machine learning model that predicts the final properties of complex fuel blends given their constituent components and proportions.

This project focuses on creating an accurate and generalizable predictive model that can help guide the design of sustainable fuels without compromising on safety, performance, and environmental goals.

📊 Problem Statement
The challenge is to:

Predict resultant blend properties from the composition of different sustainable and conventional fuels.

Handle datasets with scaled property values and no explicit property names (to ensure fair competition).

Build a model capable of generalizing to unseen blend compositions in the test dataset.

📂 Repository Structure
bash
Copy
Edit
.
├── train.csv         # Training dataset containing blend compositions and target properties
├── test.csv          # Test dataset containing blend compositions without target properties
├── submission.csv    # Sample submission file (prediction format)
├── BlendProperty.ipynb # Main notebook with data processing, model building, and prediction
└── README.md         # Project documentation
🛠️ Approach
Data Exploration

Load and inspect the datasets (train.csv, test.csv).

Check missing values, feature distributions, and correlations.

Preprocessing

Scale/normalize features if necessary.

Handle any outliers or anomalies.

Modeling

Experiment with multiple regression models (e.g., LightGBM, XGBoost, CatBoost, Random Forest).

Apply blending/stacking techniques to combine predictions from multiple models for improved performance.

Evaluation

Cross-validation to assess model stability.

Optimize hyperparameters for best generalization.

Prediction & Submission

Generate predictions for test.csv.

Save results in the format required for submission.csv.

📦 Requirements
Make sure you have the following Python packages installed:

bash
Copy
Edit
pip install pandas numpy scikit-learn xgboost lightgbm catboost matplotlib seaborn
▶️ How to Run
Clone the repository:

bash
Copy
Edit
git clone <repo_url>
cd <repo_name>
Install dependencies:

bash
Copy
Edit
pip install -r requirements.txt
(Create requirements.txt from the list in the section above.)

Open and run the notebook:

bash
Copy
Edit
jupyter notebook BlendProperty.ipynb
The notebook will:

Load the data

Train and evaluate models

Produce predictions in submission.csv

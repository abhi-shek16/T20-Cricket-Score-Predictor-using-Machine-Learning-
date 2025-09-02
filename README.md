🏏 T20 Cricket Score Predictor Using Machine Learning
📌 Overview

This project predicts the final first-innings score of a T20 cricket match using machine learning techniques.
By leveraging ball-by-ball match data and engineered features such as current score, wickets left, balls remaining, and recent scoring patterns, the model provides real-time predictions of the final score.

🎯 Problem Statement

Predicting the final score in a T20 cricket match is challenging because it depends on several dynamic factors such as:

Batting team & Bowling team

Venue/City

Current score and run rate

Wickets in hand

Last few overs’ performance

This project builds a predictive model that learns from historical match data to estimate the final innings score.

📂 Dataset

Source: Ball-by-ball commentary data in YAML/JSON format

Data Cleaning:

Filtered male T20 International matches

Removed incomplete/unwanted attributes

Handled missing values (cities, venues)

Intermediate Datasets:

dataset_level1.pkl → Match-level dataset

dataset_level2.pkl → Ball-by-ball dataset with features

🛠 Features Extracted

Batting Team

Bowling Team

City (Venue)

Current Score

Balls Left (120 – balls bowled)

Wickets Left

Current Run Rate (CRR)

Runs in Last 5 Overs

🎯 Target Variable: Final First-Innings Runs

🤖 Model Development

Preprocessing:

One-Hot Encoding for categorical features (teams, city)

Standard Scaling for numerical features

Machine Learning Algorithm:

XGBoost Regressor (optimized with tuned hyperparameters)

Pipeline:

Column Transformer → Scaler → XGBoost Model

Evaluation Metrics:

R² Score

Mean Absolute Error (MAE)

📈 Workflow

Data Extraction (data_extraction_(1).py)

Reads raw cricket match files

Cleans and processes match/ball-level data

Saves dataset as dataset_level2.pkl

Feature Engineering & Model Training (feature_extraction_(1).py)

Extracts match situation features

Builds and trains ML pipeline

Saves trained model as pipe.pkl

Prediction

Load the saved pipeline (pipe.pkl)

Input current match scenario

Output predicted final score

🚀 Applications

Real-time live score prediction

Fantasy cricket analytics

Broadcasters & commentators for data-driven insights

Team strategy planning

📦 Tech Stack

Languages: Python

Libraries:

Pandas, NumPy

Scikit-learn

XGBoost

Pickle

tqdm (progress tracking)

📊 Results

Achieved reliable score prediction with low mean absolute error (MAE)

Model captures the effect of wickets left and recent scoring momentum

🔮 Future Scope

Extend to win probability prediction

Include player-specific impact factors

Deploy using Streamlit / Flask for live demo

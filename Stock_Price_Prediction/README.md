📈 Stock Price Prediction using Scikit-Learn
🧠 Overview
This project uses machine learning regression models to predict future stock prices based on historical market data. It leverages open-source libraries such as pandas, matplotlib, and scikit-learn to perform data analysis and train three different types of regression models.

📁 Project Structure
bash
Copy
Edit
.
├── Stock_price.py            # Main Python script with data loading, modeling, and visualization
├── ABBV.csv                  # Historical stock price data (e.g., ABBV)
└── README.md                 # Project documentation
🔧 Technologies Used
Python 3

Pandas

NumPy

Scikit-Learn

Matplotlib

pandas_datareader (optional for real-time data)

🔍 Project Workflow
📊 1. Data Collection
Historical stock price data (e.g., from Yahoo Finance).

CSV file format (e.g., ABBV.csv) with Adj Close, Volume, and Close columns.

🧹 2. Data Preprocessing
Handle missing values using .fillna().

Use rolling mean to calculate moving average.

Shift labels to create a forecasting window.

Apply StandardScaler to normalize features.

⚙️ 3. Model Training
Three machine learning models are trained:

Linear Regression

Polynomial Regression (degree 2) with Ridge Regularization

K-Nearest Neighbors (KNN)

Data is split into training (80%) and testing (20%) sets using train_test_split.

📈 4. Prediction & Visualization
Predictions are made for each model.

Each model's performance is visualized via scatter plots of actual vs. predicted stock prices.

📌 How to Use
Download stock price data (e.g., from Yahoo Finance) as CSV and place it in the project folder as ABBV.csv

📊 Sample Output
Each model will generate a scatter plot:

X-axis: Actual Prices

Y-axis: Predicted Prices

This gives a visual representation of the model's prediction accuracy.

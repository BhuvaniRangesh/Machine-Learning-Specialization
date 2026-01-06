Phishing Website Detection via Logistic Regression

A custom implementation of a binary classifier designed to identify phishing websites. This project focuses on building the Machine Learning pipeline from scratch using NumPy, following the mathematical principles of Gradient Descent and Logarithmic Loss.
📌 Project Overview

Phishing remains one of the most common cyber threats. This project utilizes a dataset of over 11,000 websites, each characterized by 30 features (e.g., SSL state, URL length, anchor tags), to train a model that predicts whether a site is "Safe" or a "Phish."

Unlike standard implementations that use high-level libraries, this project implements the math engine manually to demonstrate a deep understanding of how Logistic Regression optimizes weights.
⚙️ The Mathematical Engine (Implemented from Scratch)

The core of this project is built using Vectorized NumPy operations, replacing slow Python loops with efficient matrix math:

    Sigmoid Function: Transforms linear outputs into probabilities between 0 and 1.
    g(z)=1+e−z1​

    Cost Function (Log Loss): Measures the penalty for incorrect predictions.

    Gradient Descent: Iteratively updates 30 weights (w) and 1 bias (b) to minimize the cost.
    w=w−α∂w∂J​

🛠️ Tech Stack

    Language: Python

    Libraries: * NumPy: Vectorized mathematical operations.

        Pandas: Data cleaning and ARFF file processing.

        Matplotlib & Seaborn: Visualizing the Confusion Matrix and Feature Importance.

        Scikit-Learn: Used only for data splitting and final evaluation metrics.

📊 Performance Results

The model was trained over 1,000 iterations with a learning rate (α) of 0.1.

    Final Training Cost: ~0.19

    Test Accuracy: [Insert your % e.g., 92.5%]

    Top Indicator: [Insert your #1 Feature e.g., SSL_final_State]

Confusion Matrix

The model successfully balanced the detection of phishing sites while minimizing "False Positives" (blocking safe sites).
🚀 How to Run

1. Clone the repo:
    git clone https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
2. Install dependencies:
pip install numpy pandas matplotlib seaborn scipy


Key Insights

By analyzing the Final Weights, we discovered that the model places the highest importance on:

    Feature A: (Briefly explain why this makes sense, e.g., SSL certificates are vital for security).

    Feature B: (e.g., Long URLs often hide malicious subdomains).


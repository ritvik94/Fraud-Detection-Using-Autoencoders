# Fraud-Detection-Using-Autoencoders

This project demonstrates how to use a deep learning autoencoder model to detect fraudulent credit card transactions. The model is built with TensorFlow and Keras.

The core idea is to train an autoencoder exclusively on normal (non-fraudulent) transactions. The autoencoder learns to reconstruct these normal transactions with very low error. When a fraudulent transaction is passed through the model, it will be unable to reconstruct it accurately, resulting in a high reconstruction error. By setting a threshold on this error, we can effectively flag transactions as anomalous or fraudulent.

# Dataset

The project uses the "Credit Card Fraud Detection" dataset, which can be found on Kaggle. It contains transactions made by European cardholders in September 2013.
  - Features: The dataset has 31 columns.
  - Time: Time elapsed in seconds between each transaction and the first transaction in the dataset.
  - V1 to V28: Anonymized features obtained through Principal Component Analysis (PCA).
  - Amount: The monetary value of the transaction.
  - Class: The target variable, where 1 indicates fraud and 0 indicates a normal transaction.
  - Imbalance: The dataset is highly imbalanced, with a very small percentage of fraudulent transactions, which is typical for fraud detection scenarios.

# Methodology

The anomaly detection process follows these key steps:
1. **Data Exploration and Preprocessing**
  - Load Data: The creditcard.csv dataset is loaded into a pandas DataFrame.
  - Exploratory Data Analysis (EDA): The script analyzes the distribution of normal vs. fraudulent transactions and compares the statistical properties of the          Amount feature for both classes.
  - Data Scaling: The V1 to V28 features are already scaled. The script applies StandardScaler from scikit-learn to normalize the Time and Amount columns to ensure     all features have a similar scale.

2. **Data Splitting**
  - The dataset is split into a training set (80%) and a testing set (20%). Crucially, the training data is filtered to include only normal transactions.
  - The test set retains both normal and fraudulent transactions to evaluate the model's ability to distinguish between them.

3. **Autoencoder Model Architecture**

A simple, dense autoencoder is constructed using Keras.
  - Encoder: Compresses the input data into a lower-dimensional latent space.
  - Input Layer: 30 neurons (matching the number of features).
  - Hidden Layers: Dense(18, activation="tanh"), Dense(10, activation="relu"), Dense(6, activation="tanh").
  - Decoder: Attempts to reconstruct the original input data from the compressed representation.
  - Hidden Layers: Dense(6, activation="relu"), Dense(10, activation="tanh").
  - Output Layer: Dense(30, activation="relu") to reconstruct the original 30 features.
The model is compiled with the adam optimizer and mean_squared_error as the loss function.


# Results

The Model has an Accuracy of **"95.128"**.

The scatter plot plot shows the reconstruction error:
<img width="1005" height="547" alt="image" src="https://github.com/user-attachments/assets/93fccad0-e503-4812-94f8-dc61c20bd2c3" />

The confusion matrix below shows the performance of the classification:
<img width="531" height="470" alt="image" src="https://github.com/user-attachments/assets/73706677-5865-42cc-96af-a5acdd3fcd0c" />




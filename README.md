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

# Results

The Model has an Accuracy of **95.128**.

The scatter plot plot shows the reconstruction error:
<img width="1005" height="547" alt="image" src="https://github.com/user-attachments/assets/93fccad0-e503-4812-94f8-dc61c20bd2c3" />

The confusion matrix below shows the performance of the classification:
<img width="531" height="470" alt="image" src="https://github.com/user-attachments/assets/73706677-5865-42cc-96af-a5acdd3fcd0c" />




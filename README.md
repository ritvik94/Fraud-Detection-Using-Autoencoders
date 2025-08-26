# Fraud-Detection-Using-Autoencoders

This project demonstrates how to use a deep learning autoencoder model to detect fraudulent credit card transactions. The model is built with TensorFlow and Keras.

The core idea is to train an autoencoder exclusively on normal (non-fraudulent) transactions. The autoencoder learns to reconstruct these normal transactions with very low error. When a fraudulent transaction is passed through the model, it will be unable to reconstruct it accurately, resulting in a high reconstruction error. By setting a threshold on this error, we can effectively flag transactions as anomalous or fraudulent.

Dataset


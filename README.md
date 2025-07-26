# Autoencoder from Scratch

This project implements a **basic autoencoder neural network from scratch using PyTorch**, designed to learn and compress image representations using an unsupervised learning approach. The model is trained on the MNIST dataset of handwritten digits.

> A hands-on project to understand how autoencoders work, how they compress input data, and how reconstruction loss drives the training process.

---

## Overview

An **autoencoder** is a type of neural network that learns to encode data into a compressed representation and then decode it back to the original input form. It consists of two main parts:
- **Encoder:** Compresses the input into a latent-space representation.
- **Decoder:** Reconstructs the input from the latent representation.

This notebook includes:
- Data loading using torchvision (MNIST dataset)
- Custom encoder and decoder architecture using `nn.Sequential`
- Training loop using reconstruction loss (`MSELoss`)
- Visualization of original and reconstructed digits

---

##  Model Architecture

- **Encoder:**
  - Linear → ReLU → Linear → ReLU → Latent Space
- **Decoder:**
  - Linear → ReLU → Linear → Sigmoid

This simple feedforward autoencoder is trained to minimize the reconstruction error between the input and the output.

---
## Credits

This project is based on and inspired by the YouTube tutorial:

**"Autoencoders - EXPLAINED!"** by Aladdin Persson  
[https://www.youtube.com/watch?v=zp8clK9yCro](https://www.youtube.com/watch?v=zp8clK9yCro)

Full credit goes to Aladdin Persson for the foundational walkthrough and explanations.


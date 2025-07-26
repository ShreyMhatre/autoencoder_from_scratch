# Autoencoder from Scratch

This project implements **basic autoencoder neural networks from scratch using PyTorch**, designed to learn and compress image representations in an unsupervised manner. The models are trained on the MNIST dataset of handwritten digits.

> A practical project to understand the working principles of autoencoders, how they compress input data, and how reconstruction loss drives the training process.

---

## Overview

An **autoencoder** is a type of neural network that learns to encode data into a compressed latent representation and then decode it back to the original input form. It has two main components:

- **Encoder:** Compresses the input into a lower-dimensional latent space.
- **Decoder:** Reconstructs the input from the latent representation.

This project includes:
- Data loading using torchvision (MNIST dataset)
- Two custom autoencoder architectures built with PyTorch (`nn.Sequential`)
- Training loops optimizing reconstruction loss (mean squared error)
- Visualization of original and reconstructed digits

---

## Model Architectures

### 1. Fully Connected (Dense) Autoencoder

**Encoder:**
- Flatten input images (28×28 → 784 features)
- Linear(784 → 128), ReLU
- Linear(128 → 64), ReLU
- Linear(64 → 12), ReLU
- Linear(12 → 3)   *(Latent representation: 3-dimensional)*

**Decoder:**
- Linear(3 → 12), ReLU
- Linear(12 → 64), ReLU
- Linear(64 → 128), ReLU
- Linear(128 → 784), Sigmoid
- Reshape output to image size (784 → 28×28)

This architecture provides a deep encoder and decoder, compressing the original input down to a compact 3-dimensional latent space before reconstructing the images.

---

### 2. Convolutional Autoencoder

**Encoder:**
- Conv2d: 1 → 16, kernel size=3, stride=2, padding=1 → ReLU
- Conv2d: 16 → 32, kernel size=3, stride=2, padding=1 → ReLU
- Conv2d: 32 → 64, kernel size=7 (output: 1×1×64 latent representation)

**Decoder:**
- ConvTranspose2d: 64 → 32, kernel size=7 → ReLU
- ConvTranspose2d: 32 → 16, kernel size=3, stride=2, padding=1, output_padding=1 → ReLU
- ConvTranspose2d: 16 → 1, kernel size=3, stride=2, padding=1, output_padding=1 → Sigmoid

This convolutional architecture preserves spatial relationships and typically yields sharper reconstructions compared to fully connected variants.

---

## Credits

This project is inspired by and based on the YouTube tutorial:

**"Autoencoders - EXPLAINED!"** by Aladdin Persson  
[https://www.youtube.com/watch?v=zp8clK9yCro](https://www.youtube.com/watch?v=zp8clK9yCro)

Full credit goes to Aladdin Persson for the clear explanations and foundational code walkthroughs.

# Smart Waste Detection and Classification System

## Overview

This project is a computer vision-based waste detection and classification system developed to improve waste sorting efficiency. It uses multiple deep learning models to classify different types of waste and compares their performance.

The project is built using the **TrashNet dataset** and evaluates several machine learning and deep learning approaches, including CNNs, YOLOv8, GANs, Autoencoders, and a Multimodal model.

---

## Problem Statement

Improper waste disposal contributes to pollution, environmental damage, and health risks. Manual waste sorting is often slow, expensive, and prone to human error.

This project aims to automate waste classification using computer vision, enabling faster and more accurate waste sorting.

---

## Objectives

- Detect and classify different waste types.
- Compare the performance of multiple deep learning models.
- Improve waste sorting efficiency through AI.
- Deploy the best-performing model in a web application.

---

## Dataset

**Dataset:** TrashNet

### Classes

- Cardboard
- Glass
- Metal
- Paper
- Plastic
- Trash

| Class | Images |
|--------|--------|
| Glass | 501 |
| Cardboard | 403 |
| Metal | 410 |
| Paper | 594 |
| Plastic | 482 |
| Trash | 137 |

---

## Data Preprocessing

The following preprocessing techniques were applied:

- Image resizing
- Normalization
- Data augmentation
  - Rotation
  - Flipping
  - Brightness adjustment

The dataset was split into:

- 80% Training
- 10% Validation
- 10% Testing

For validation data, augmentation was not applied.

---

## Models Used

### 1. Custom CNN

Features:

- Input size: 224 × 224 × 3
- Convolution layers
- MaxPooling
- Flatten layer
- Dense layer (128 neurons)
- Output layer (6 classes)

Training includes:

- 100 epochs
- Model checkpoint
- Early stopping

---

### 2. Pre-trained CNN (MobileNetV2)

- Transfer learning using MobileNetV2
- Last 50 layers frozen
- Dense classification head
- Faster and more lightweight than the custom CNN

---

### 3. YOLOv8

Used for object detection.

Features:

- Dataset converted into YOLO format
- YAML configuration file
- Image-label pairing verification
- YOLOv8n model
- Training and evaluation pipeline

YOLO achieved the best overall performance and was selected for deployment.

---

### 4. GAN (Generative Adversarial Network)

Implemented for image generation.

Components:

- Generator
- Discriminator

The GAN was trained on the **Glass** class to generate realistic waste images.

---

### 5. Autoencoder

Used for image reconstruction.

Architecture:

- Encoder
- Decoder
- Latent representation
- Reconstruction visualization

---

### 6. Multimodal Model

Combines:

- Image features
- Text descriptions

A CSV dataset containing:

- Image path
- Text description
- Label

was created to train the multimodal model.

---

## Technologies Used

- Python
- TensorFlow / Keras
- Ultralytics YOLOv8
- OpenCV
- NumPy
- Pandas
- Streamlit

---

## Web Application

The final application was developed using **Streamlit**.

### Features

- Upload an image
- Detect waste type
- Display prediction
- Supports:

  - JPG
  - PNG

The deployed model uses the trained **YOLOv8** weights (`best.pt`).



---

## Results

The project compares several deep learning models for waste classification.

Models evaluated include:

- Custom CNN
- MobileNetV2
- YOLOv8
- GAN
- Autoencoder
- Multimodal Model

Among all tested approaches, **YOLOv8 produced the best performance** and was selected for deployment in the Streamlit web application.




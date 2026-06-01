# American Sign Language (ASL) Detection using Deep Learning

## Project Overview

This project focuses on recognizing and classifying **American Sign Language (ASL) alphabet gestures** using Deep Learning and Computer Vision techniques.

A Convolutional Neural Network (CNN) was developed to classify hand-sign images into **29 different ASL classes**, including alphabets and special symbols. The project further explores **Transfer Learning using MobileNetV2**, advanced evaluation techniques, and model explainability through **Grad-CAM visualizations**.

The goal of this project is to demonstrate how Deep Learning can be applied to assist communication for individuals who use sign language.

---

## Problem Statement

American Sign Language is widely used by the deaf and hard-of-hearing community. Manual interpretation may not always be available, creating communication barriers.

The objective of this project is to develop an automated system capable of recognizing ASL hand gestures from images and accurately predicting the corresponding sign.

---

## Dataset

**Dataset:** ASL Alphabet Dataset

**Source:** Kaggle

The dataset contains images representing:

- 26 Alphabet Classes (A–Z)
- Space
- Delete
- Nothing

Total Classes:

- 29 Classes

Dataset Characteristics:

- Thousands of labeled hand-sign images
- Multiple image samples per class
- RGB image format
- Suitable for multi-class image classification

---

## Project Workflow

### 1. Data Acquisition

- Downloaded dataset using KaggleHub
- Loaded image directories automatically
- Created training and validation subsets

### 2. Data Preprocessing

Image preprocessing steps included:

- Image resizing to 32×32 pixels
- Pixel normalization (0–1 scaling)
- Batch generation
- Dataset splitting

### 3. Data Augmentation

To improve generalization and reduce overfitting:

- Random Rotation
- Random Zoom
- Width Shift
- Height Shift
- Horizontal Flip

---

## Exploratory Analysis

Dataset verification included:

- Class inspection
- Directory structure validation
- Sample image visualization
- Class distribution review

---

# CNN-Based ASL Classification Model

## Model Architecture

A custom Convolutional Neural Network (CNN) was developed.

### Convolution Block 1

- Conv2D (32 Filters)
- ReLU Activation
- MaxPooling2D

### Convolution Block 2

- Conv2D (64 Filters)
- ReLU Activation
- MaxPooling2D

### Convolution Block 3

- Conv2D (128 Filters)
- ReLU Activation
- MaxPooling2D

### Fully Connected Layers

- Flatten Layer
- Dense Layer (128 Units)
- Dropout (0.5)
- Output Layer (29 Classes)

### Output Layer

- Softmax Activation

---

## Model Training

### Training Configuration

- Optimizer: Adam
- Learning Rate: 0.001
- Loss Function: Categorical Crossentropy
- Epochs: 15
- Batch Size: 128

### Training Process

The CNN model was trained using augmented image data and validated on a separate validation subset.

---

## Transfer Learning with MobileNetV2

To improve performance, a Transfer Learning approach was implemented using **MobileNetV2**.

### Transfer Learning Workflow

- Pretrained MobileNetV2 loaded from ImageNet
- Top classification layer removed
- Base layers frozen
- Custom classification head added
- Retrained on ASL dataset

### Advantages

- Faster convergence
- Better feature extraction
- Improved generalization
- Higher classification performance

---

## Model Evaluation

The model was evaluated using multiple performance metrics.

### Evaluation Metrics

- Accuracy
- Precision
- Recall
- F1 Score
- Classification Report
- Confusion Matrix

---

## Model Explainability

### Grad-CAM Visualization

Gradient-weighted Class Activation Mapping (Grad-CAM) was implemented to visualize the regions of hand images influencing model predictions.

Benefits:

- Improves model interpretability
- Highlights important gesture regions
- Provides explainable AI insights

---

## Prediction System

The trained model can:

- Load an input image
- Perform preprocessing
- Predict the corresponding ASL sign
- Return prediction confidence

Example Output:

```text
Predicted Sign: A
Confidence: 98.4%
```

---

## Results

The CNN and MobileNetV2 models successfully learned meaningful gesture representations from ASL images.

Key observations:

- Strong multi-class classification performance
- Effective recognition of ASL alphabet gestures
- Transfer Learning significantly improved accuracy
- Data augmentation improved model robustness
- Grad-CAM enhanced interpretability

The project demonstrates the effectiveness of Deep Learning for real-time sign language recognition systems.

---

## Technologies Used

### Programming

- Python

### Deep Learning

- TensorFlow
- Keras

### Computer Vision

- OpenCV

### Data Processing

- NumPy

### Visualization

- Matplotlib
- Seaborn

### Transfer Learning

- MobileNetV2

### Explainable AI

- Grad-CAM

---

## Key Learnings

- CNNs effectively capture spatial features from hand-sign images.
- Data augmentation improves model generalization.
- Transfer Learning can significantly outperform training from scratch.
- Explainable AI techniques provide deeper insight into model decisions.
- Sign language recognition is a strong real-world application of Computer Vision.

---

## Future Improvements

- Real-time webcam-based ASL detection
- Fine-tuning MobileNetV2 layers
- Deployment using Streamlit
- Mobile application integration
- Video-based sign language recognition
- Transformer-based Vision Models
- Real-time sentence generation from gestures

---

## Author

**Chaitali Jadhav**

Data Analytics | Machine Learning | Deep Learning | Computer Vision | Healthcare AI | Bioinformatics

GitHub: https://github.com/chaitali-analytics

LinkedIn: https://www.linkedin.com/in/chaitali-jadhav-971622380/

Email: cjbioinformatics@gmail.com

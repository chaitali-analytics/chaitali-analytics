# Animal Image Classification using Deep Learning and Transfer Learning

## Project Overview

This project focuses on multiclass animal image classification using Deep Learning and Computer Vision techniques.

The objective was to automatically identify animal categories from images by training Convolutional Neural Networks (CNNs) and improving performance through Transfer Learning using MobileNetV2.

The project demonstrates a complete Deep Learning workflow including:

* Image preprocessing
* Data normalization
* Dataset optimization
* CNN model development
* Transfer Learning
* Data Augmentation
* Model evaluation
* Performance visualization

---

## Problem Statement

Image classification is one of the most important tasks in Computer Vision.

Manually identifying animals from large image collections is time-consuming and error-prone.

The goal of this project was to build an intelligent image classification system capable of automatically recognizing different animal categories from images.

---

## Dataset

The dataset consists of animal images organized into separate folders representing different classes.

Dataset structure:

dataset/

├── Animal_Class_1

├── Animal_Class_2

├── Animal_Class_3

├── ...

Each folder contains images belonging to a specific animal category.

---

## Project Workflow

### 1. Data Loading

The dataset was loaded directly from Google Drive using TensorFlow's image dataset loader.

Key configurations:

* Image Size: 224 × 224
* Batch Size: 32
* Validation Split: 20%
* Random Seed: 123

---

### 2. Data Preprocessing

To improve model performance and training stability:

#### Normalization

Pixel values were scaled from:

0 – 255

to

0 – 1

This helps neural networks converge faster during training.

#### Dataset Optimization

TensorFlow data pipelines were optimized using:

* Cache
* Prefetch
* AUTOTUNE

Benefits:

* Faster training
* Reduced I/O bottlenecks
* Better GPU utilization

---

## Exploratory Analysis

Training and validation datasets were created using:

* 80% Training Data
* 20% Validation Data

Class names were automatically extracted from folder structures.

---

## Initial CNN Model

A custom Convolutional Neural Network was developed as the baseline model.

### Architecture

#### Input Layer

224 × 224 × 3 RGB Images

#### Convolution Block 1

* Conv2D (16 Filters)
* ReLU Activation
* MaxPooling

#### Convolution Block 2

* Conv2D (32 Filters)
* ReLU Activation
* MaxPooling

#### Convolution Block 3

* Conv2D (64 Filters)
* ReLU Activation
* MaxPooling

#### Fully Connected Layers

* Flatten Layer
* Dense Layer (128 Units)
* Output Layer (Softmax)

---

## Baseline Model Training

Configuration:

* Optimizer: Adam
* Loss Function: Sparse Categorical Crossentropy
* Epochs: 10
* Metric: Accuracy

### Observation

The baseline CNN showed signs of underfitting.

Training accuracy and validation accuracy remained limited, indicating the need for a more powerful feature extraction approach.

---

# Transfer Learning Approach

To improve classification performance, Transfer Learning was implemented using MobileNetV2.

---

## Why MobileNetV2?

MobileNetV2 offers:

* Lightweight architecture
* Faster training
* Pretrained ImageNet knowledge
* Excellent image feature extraction capability

---

## Data Augmentation

To increase dataset diversity and reduce overfitting, the following augmentation techniques were applied:

* Random Horizontal Flip
* Random Vertical Flip
* Random Rotation
* Random Zoom
* Random Contrast Adjustment

Benefits:

* Improved generalization
* Better robustness to unseen images
* Reduced overfitting risk

---

## Transfer Learning Model Architecture

### Base Model

MobileNetV2

Configuration:

* ImageNet Weights
* Top Layers Removed
* Feature Extractor Frozen

### Custom Classification Head

* GlobalAveragePooling2D
* Dropout (0.2)
* Dense Output Layer

---

## Model Training

Training Configuration:

* Optimizer: Adam
* Learning Rate: 0.0001
* Loss Function: Sparse Categorical Crossentropy
* Epochs: 20

The pretrained MobileNetV2 feature extractor significantly improved learning capability compared to the baseline CNN.

---

## Model Evaluation

The trained model was evaluated using multiple classification metrics.

### Evaluation Metrics

* Accuracy
* Precision
* Recall
* F1 Score
* Confusion Matrix
* Classification Report

---

## Prediction Pipeline

The final model can:

1. Accept a new animal image
2. Perform preprocessing
3. Extract features using MobileNetV2
4. Predict the most probable animal class
5. Return prediction confidence score

Example Output:

Actual Class: Tiger

Predicted Class: Tiger

Confidence: 98.4%

---

## Results

The Transfer Learning model substantially outperformed the baseline CNN.

Key observations:

* Higher classification accuracy
* Better feature extraction
* Improved generalization capability
* Reduced underfitting
* Stronger validation performance

MobileNetV2 successfully learned discriminative visual features across multiple animal categories.

---

## Technologies Used

### Programming Language

* Python

### Deep Learning

* TensorFlow
* Keras

### Transfer Learning

* MobileNetV2

### Data Processing

* NumPy

### Visualization

* Matplotlib
* Seaborn

### Evaluation

* Scikit-Learn

---

## Key Learnings

* Transfer Learning significantly improves image classification performance.
* MobileNetV2 provides powerful pretrained visual representations.
* Data augmentation helps prevent overfitting.
* CNN architectures require sufficient training data to generalize effectively.
* Proper preprocessing and optimization pipelines improve training efficiency.

---

## Future Improvements

* Fine-Tune MobileNetV2 Layers
* Experiment with EfficientNet
* Add Early Stopping
* Implement Learning Rate Scheduling
* Hyperparameter Optimization
* Deploy as a Web Application
* Real-Time Animal Recognition System

---

## Author

### Chaitali Jadhav

Data Analytics | Machine Learning | Deep Learning | Computer Vision | Healthcare AI | Bioinformatics

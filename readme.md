# Milk Adulteration Detection Using Evaporation Pattern Analysis and CNN

## Overview

This project focuses on detecting milk adulteration using image processing and deep learning techniques. The system analyzes evaporation-pattern residue images of milk samples and classifies them into different adulteration categories using a Convolutional Neural Network (CNN) based on MobileNetV2 transfer learning.

The objective of the project is to identify the type of adulterant present in milk rather than predicting concentration levels.

The model classifies milk samples into the following categories:

- Pure Milk
- Water Adulteration
- Sugar Adulteration
- Salt Adulteration
- Detergent Adulteration

---

# Problem Statement

Milk adulteration is a major issue affecting food quality and public health. Traditional laboratory-based testing methods are often time-consuming, costly, and require specialized equipment.

This project proposes an image-based deep learning approach that analyzes milk evaporation residue patterns to automatically detect adulterants using computer vision and CNN models.

---

# Objectives

- Detect adulterant type from milk evaporation-pattern images
- Use image processing and CNN for automated classification
- Reduce dependency on manual laboratory analysis
- Develop a lightweight and scalable deep learning model
- Achieve high classification accuracy using transfer learning

---

# Dataset Description

## Original Dataset

The original dataset contained:

- BMP images
- Resolution: 2592 × 1944
- RGB images
- Approximately 925 images

Dataset included:

- Different adulterant types
- Multiple concentration levels
- Center and edge residue regions

---

## Original Dataset Structure

```text
Milk_adulteration_images/
├── detergent/
│   ├── 1_gm/
│   │   ├── Center/
│   │   └── Edges/
│   ├── 2_gm/
│   ├── 3_gm/
│   ├── 4_gm/
│   └── 5_gm/
│
├── Salt/
├── sugar/
├── Water/
└── pure_milk/
```

---

# Dataset Preparation

## Preprocessing Steps

1. Converted BMP images to JPG format
2. Resized images to 224×224
3. Merged concentration and region variations into single adulterant classes
4. Generated metadata CSV file
5. Created metadata-aware train-validation split

---

# Final Dataset Structure

```text
CNN_Dataset/
├── detergent/
├── pure_milk/
├── salt/
├── sugar/
└── water/
```

---

# Technologies Used

## Programming Language

- Python 3.11

## Libraries

- TensorFlow / Keras
- OpenCV
- NumPy
- Pandas
- Matplotlib
- Seaborn
- Scikit-learn
- Pillow

## Development Environment

- Windows
- VS Code
- Virtual Environment

---

# Deep Learning Model

## Model Used

- MobileNetV2 (Transfer Learning)

## Why MobileNetV2?

- Lightweight architecture
- Faster training
- Good performance on smaller datasets
- Efficient feature extraction
- Suitable for transfer learning

---

# Model Architecture

```text
Input Image (224×224×3)
        ↓
MobileNetV2 Base Model
        ↓
GlobalAveragePooling2D
        ↓
BatchNormalization
        ↓
Dropout
        ↓
Dense Layer (ReLU)
        ↓
BatchNormalization
        ↓
Dropout
        ↓
Output Layer (Softmax)
```

---

# Training Configuration

| Parameter | Value |
|---|---|
| Image Size | 224×224 |
| Batch Size | 16 |
| Epochs | 25 |
| Optimizer | Adam |
| Learning Rate | 1e-4 |
| Loss Function | Categorical Crossentropy |
| Validation Split | 20% |

---

# Techniques Used to Improve Performance

- Transfer Learning
- Data Augmentation
- Metadata-aware Stratified Splitting
- Class Weights
- Batch Normalization
- Dropout Regularization
- Early Stopping
- ReduceLROnPlateau
- Model Checkpointing

---

# Final Results

## Validation Accuracy

95.14%

---

# Classification Report

| Class | Precision | Recall | F1-Score |
|---|---|---|---|
| detergent | 0.87 | 1.00 | 0.93 |
| pure_milk | 1.00 | 1.00 | 1.00 |
| salt | 0.95 | 0.95 | 0.95 |
| sugar | 1.00 | 0.87 | 0.93 |
| water | 1.00 | 0.98 | 0.99 |

---

# Confusion Matrix Analysis

- Strong classification performance across all classes
- Minimal confusion between adulterants
- Salt and sugar patterns initially showed similarity
- Metadata-aware splitting significantly improved generalization

---

# Project Workflow

```text
Milk Sample Collection
        ↓
Milk Evaporation Process
        ↓
Residue Image Capture
        ↓
Image Preprocessing
        ↓
Dataset Preparation
        ↓
CNN Training
        ↓
Model Evaluation
        ↓
Adulteration Prediction
```

---

# Features

- Automatic adulterant classification
- Deep learning-based prediction
- High validation accuracy
- Image-based analysis
- Lightweight MobileNetV2 architecture
- Supports multiple adulterant types

---

# Files Generated

```text
milk_model.keras
best_model.keras
class_names.json
metadata.csv
accuracy_graph.png
loss_graph.png
confusion_matrix.png
```

---

# How to Run the Project

## 1. Clone Repository

```bash
git clone <repository_link>
```

---

## 2. Create Virtual Environment

```bash
python -m venv venv
```

---

## 3. Activate Environment

### Windows

```bash
venv\Scripts\activate
```

---

## 4. Install Requirements

```bash
pip install -r requirements.txt
```

---

## 5. Generate Metadata

```bash
python generate_metadata.py
```

---

## 6. Train Model

```bash
python train_model.py
```

---

# Future Enhancements

- Real-time adulteration detection
- Mobile application integration
- Flask web deployment
- Concentration estimation
- Multi-adulterant detection
- IoT-based smart milk testing system

---

# Applications

- Dairy Industry
- Food Quality Testing
- Milk Collection Centers
- Smart Food Inspection Systems
- Agricultural Research

---

# Research Contribution

This work demonstrates that milk adulteration can be effectively identified using evaporation-pattern image analysis combined with deep learning techniques. The proposed approach provides a low-cost and scalable alternative to traditional laboratory testing methods.

---

# Author

Rohit Chavan

---

# License

This project is developed for academic and research purposes.

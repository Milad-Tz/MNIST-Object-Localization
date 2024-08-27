# Object Localization and Classification Using MNIST Dataset

This repository provides a notebook that explores object localization and classification tasks using the MNIST dataset, which consists of images of handwritten digits from 0 to 9. The notebook covers various cases, demonstrating how to create datasets, build models, and evaluate performance for different object detection and classification scenarios.

## Objectives

The primary objective of this notebook is to build and evaluate models capable of detecting and localizing digits within images. The notebook addresses different scenarios to cover a range of object localization and classification tasks.

## Overview of Cases

### Case 1: Single Class Localization
- **Objective**: Detect and localize a single digit (e.g., digit '1') within larger images.
- **Data Creation**:
  - **Images**: Larger images with a single digit randomly placed on a black background.
  - **Labels**: Bounding box coordinates for the digit and a binary label indicating the presence of the digit.

### Case 2: Binary Classification and Localization
- **Objective**: Classify whether a digit is present in an image and localize it if present. The dataset includes images with and without digits.
- **Data Creation**:
  - **Images**: Larger images with one digit, two digits, or completely empty.
  - **Labels**:
    - **Presence/Absence**: A binary classification label indicating whether any digit is present.
    - **Bounding Box**: Coordinates for the bounding box around the digit(s), if present.

### Case 3: Multi-Class Localization
- **Objective**: Detect and localize digits from all 10 classes (0-9) within larger images.
- **Data Creation**:
  - **Images**: Larger images containing one digit from any of the 10 classes, placed randomly on a black background.
  - **Labels**:
    - **Class Label**: One-hot encoded class of the digit present in the image.
    - **Bounding Box**: Coordinates for the bounding box around the digit.

### Case 4: Multi-Class Detection with Multiple Objects
- **Objective**: Handle images containing multiple digits from different classes or be empty.
- **Data Creation**:
  - **Images**: Larger images with:
    - One or two digits from any class.
    - Only one digit.
    - An empty background.
  - **Labels**:
    - **Presence Classification**: A label indicating if there are one or two digits or if the image is empty.
    - **Bounding Boxes**: Coordinates for up to two digits, or empty if no digit is present.

## Data Creation Process

1. **Generating Large Images**:
   - Create larger images (e.g., 128x128 pixels) with a black background.
   - Place smaller MNIST digits at random locations within these larger images.

2. **Creating Labels**:
   - Generate bounding box coordinates for the digits and classify their presence.
   - Use one-hot encoding for multi-class classification where applicable.

3. **Model Training and Evaluation**:
   - Train models to classify and localize digits.
   - Evaluate model performance based on classification accuracy and Intersection over Union (IoU) for bounding box predictions.

## Usage

1. **Prepare the Dataset**:
   - Follow the provided scripts to generate and preprocess the dataset according to the case you are exploring.

2. **Build and Compile the Model**:
   - Use the provided model architecture to build and compile your model.

3. **Train the Model**:
   - Train the model using the prepared dataset and evaluate its performance.

4. **Visualize Results**:
   - Use the visualization code to inspect the results and compare predicted bounding boxes with ground truth.

## Requirements

- Python 3.x
- TensorFlow/Keras
- NumPy
- Matplotlib
- Scikit-learn

Install the required packages using:

```bash
pip install tensorflow numpy matplotlib scikit-learn

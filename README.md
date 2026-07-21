# Handwritten Digit Recognition System using CNN

## Overview

This project presents an end-to-end Handwritten Digit Recognition System developed using Convolutional Neural Networks (CNNs). The model is trained on the MNIST dataset to classify handwritten digits (0-9) and is capable of predicting unseen handwritten images through a custom image preprocessing pipeline.

The project follows industry-inspired practices including:
- Dataset splitting
- Data preprocessing
- CNN architecture design
- EarlyStopping
- ModelCheckpoint
- Model evaluation techniques
- Custom image prediction using OpenCV
- Error analysis using Confusion Matrix and Classification Report


---

## Problem Statement

The objective of this project is to develop a Deep Learning model that can accurately recognize handwritten digits from images. The system should:

- Classify digits from 0 to 9.
- Predict unseen handwritten images.
- Generalize well on test data.
- Handle custom image inputs using OpenCV preprocessing techniques.
- Save the best performing model automatically during training.


---

## Dataset Information

The project uses the MNIST Handwritten Digit Dataset.

| Information | Value |
|------------|-------|
| Total Images | 70,000 |
| Number of Classes | 10 |
| Image Size | 28 × 28 |
| Image Type | Grayscale |
| Classes | 0-9 |



## Technologies Used

- Python
- TensorFlow
- NumPy
- Matplotlib
- Scikit-Learn
- OpenCV
- Jupyter Notebook
- Deep Learning
- Convolutional Neural Networks (CNN)


---

## Data Preprocessing

The preprocessing pipeline includes:

- Dataset splitting
- Image normalization
- Reshaping images
- Grayscale conversion
- Image resizing
- Image inversion
- Thresholding techniques
- Preparing custom images for prediction


### Normalization

```
0 - 255
   ↓
 0 - 1

```

### Reshaping

```
(28,28)
    ↓
(28,28,1)

```


---

## CNN Architecture

```
                Input
             (28,28,1)
                   |
             Conv2D (32)
                   |
             MaxPooling
                   |
             Conv2D (64)
                   |
             MaxPooling
                   |
                Flatten
                   |
              Dense(128)
                   |
             Dropout(0.5)
                   |
          Dense(10, Softmax)
                   |
              Prediction
```

### Layers Used

- Conv2D
- MaxPooling2D
- Flatten
- Dense Layers
- Dropout
- Softmax Activation Function


---

## Model Training

The model is trained using:

```python
Optimizer:
Adam

Loss Function:
Sparse Categorical Crossentropy

Metric:
Accuracy

Batch Size:
32

Epochs:
50

Callbacks:
- EarlyStopping
- ModelCheckpoint
```

### EarlyStopping

```python
monitor="val_loss"
patience=5
restore_best_weights=True
```

### ModelCheckpoint

```python
monitor="val_accuracy"
save_best_only=True
```

The best performing model is automatically saved during training.


---

## Model Evaluation

The model is evaluated using:

- Test Accuracy
- Test Loss
- Confusion Matrix
- Classification Report
- Misclassified Image Analysis
- Custom Image Predictions


### Evaluation Pipeline

```
Testing Dataset
        |
     evaluate()
        |
     predict()
        |
     argmax()
        |
 Confusion Matrix
        |
Classification Report
        |
Misclassified Images
        |
 Performance Analysis
```


---

## Custom Image Prediction Pipeline

The project supports prediction on unseen handwritten images.

```
            Image
              |
          Read Image
              |
         Gray Scale
              |
         Thresholding
              |
        Image Inversion
              |
           Resize
            28x28
              |
        Normalization
              |
          Reshape
      (1,28,28,1)
              |
        model.predict()
              |
          Softmax Output
              |
          np.argmax()
              |
        Predicted Digit
```


---

## Results

The model successfully performs:

- Multiclass Classification
- Custom Image Prediction
- Misclassification Analysis
- Automatic Best Model Saving
- Robust Prediction Pipeline Design

> Note: Actual accuracy may vary slightly depending on preprocessing techniques and training configurations.


---



## Future Improvements

Some possible extensions include:

- Transfer Learning
- Batch Normalization
- Streamlit Deployment
- GUI Development
- Webcam-based Digit Recognition
- Data Augmentation Techniques
- Mobile Deployment


---

## Learning Outcomes

Through this project, I learned:

- CNN Architecture Design
- Image Preprocessing Techniques
- Deep Learning Model Training
- Callback Functions in TensorFlow
- Overfitting and Underfitting Analysis
- Model Evaluation Strategies
- Custom Image Prediction Pipelines
- OpenCV Integration
- End-to-End Deep Learning Project Development


---

## Conclusion

This project demonstrates the complete workflow of building an end-to-end Handwritten Digit Recognition System using Deep Learning techniques. It combines CNN-based image classification, professional model evaluation practices, and custom image prediction pipelines to provide a practical and portfolio-ready Deep Learning project.



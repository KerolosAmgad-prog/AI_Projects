# MNIST Digit Classification using TensorFlow Keras

## Project Title
MNIST Digit Classification

## Description
This project implements a simple Artificial Neural Network (ANN) using TensorFlow's Keras API to classify handwritten digits from the MNIST dataset. The MNIST dataset is a widely used benchmark in machine learning, consisting of 60,000 training images and 10,000 testing images of handwritten digits (0-9).

The goal is to build and train a neural network that can accurately identify the digit represented in an image.

## Setup
To run this notebook, you need to have Python installed along with the following libraries:

- `tensorflow`
- `keras` (comes with tensorflow)
- `numpy`
- `pandas`
- `matplotlib`
- `seaborn`

You can install the necessary packages using pip:
```bash
pip install tensorflow[and-cuda] numpy pandas matplotlib seaborn
```

## Usage
1. **Load Data**: The MNIST dataset is automatically loaded using `keras.datasets.mnist.load_data()`.
2. **Data Normalization**: Pixel values of the images are scaled from the range [0, 255] to [0, 1] to aid model training.
3. **Model Architecture**: A sequential Keras model is defined with:
    - A `Flatten` layer to convert 2D image data (28x28 pixels) into a 1D array (784 pixels).
    - A `Dense` (hidden) layer with 120 neurons and `relu` activation.
    - A `Dense` (output) layer with 10 neurons (one for each digit 0-9) and `sigmoid` activation.
4. **Model Compilation**: The model is compiled using the `adam` optimizer, `sparse_categorical_crossentropy` loss function, and `accuracy` as the metric.
5. **Training**: The model is trained on the `X_train_norm` and `y_train` data for 10 epochs.
6. **Evaluation**: The trained model's performance is evaluated on the test set (`X_test_norm`, `y_test`).
7. **Prediction**: Predictions are made on the test data, and individual predictions are analyzed.
8. **Confusion Matrix**: A confusion matrix is generated and visualized using seaborn to understand the model's classification performance across all digits.

## Model Architecture
```python
model = tf.keras.Sequential([
    tf.keras.layers.Flatten(input_shape=(28, 28), name='input_Layer'),
    tf.keras.layers.Dense(120, activation='relu', name='hidden_Layer'),
    tf.keras.layers.Dense(10, activation='sigmoid', name='output_Layer')
])
```

## Results
After training for 10 epochs, the model achieved an accuracy of approximately **97.6%** on the test dataset. The confusion matrix provides a detailed breakdown of correct and incorrect classifications for each digit, highlighting where the model performs well and where it might struggle (e.g., occasional confusion between certain digits like 7 and 9).

## Conclusion
This project demonstrates a basic yet effective implementation of a neural network for image classification on the MNIST dataset. The results indicate that a relatively simple ANN can achieve high accuracy on this task, showcasing the power of deep learning for pattern recognition.



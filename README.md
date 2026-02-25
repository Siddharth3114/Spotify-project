Spotify Genre Classification
This project aims to classify the genre of a song based on its audio features using various machine learning and deep learning models. The final model, a neural network built with TensorFlow/Keras, is saved and can be used for inference through a simple Streamlit web application.

Project Overview
The goal is to build a robust multi-class classifier that can accurately predict a song's genre from a set of audio features provided by Spotify, such as danceability, energy, acousticness, and valence. The project involves a complete machine learning pipeline: data exploration, preprocessing, model training, evaluation, and saving the final model for deployment.

Dataset
The project uses the SpotifyFeatures.csv dataset, which contains audio features for over 232,000 tracks across 27 different genres.

Key features used for classification:

popularity

acousticness

danceability

duration_ms

energy

instrumentalness

key

liveness

loudness

mode

speechiness

tempo

time_signature

valence

The target variable is genre.

Methodology
The project follows these key steps:

Data Loading & Cleaning: The dataset is loaded using pandas. Unnecessary columns like artist_name, track_name, and track_id are dropped.

Data Preprocessing:

Label Encoding: The target variable genre is converted from categorical text to numerical labels using LabelEncoder.

One-Hot Encoding: Categorical features (key, mode, time_signature) are converted into a numerical format using one-hot encoding.

Feature Scaling: All numerical features are standardized using StandardScaler to ensure that they have a mean of 0 and a standard deviation of 1.

Train-Test Split: The dataset is split into training (80%) and testing (20%) sets. Stratification is used on the target variable y to maintain the same proportion of genres in both sets.

Model Training & Evaluation: Several models were trained and evaluated:

Logistic Regression

Random Forest Classifier

MLP Classifier (from Scikit-learn)

A Deep Neural Network (using TensorFlow/Keras)

Final Model: The TensorFlow/Keras model was selected as the final model due to its superior performance.

Models and Results
Multiple classification models were tested. The Deep Learning model built with TensorFlow/Keras provided the best performance.

Model	Test Accuracy
Logistic Regression	38.6%
Random Forest	36.9%
MLP Classifier (Scikit-learn)	44.3%
Deep Learning (TensorFlow/Keras)	44.8%
The final TensorFlow model architecture is as follows:

Input Layer: Dense (256 units, ReLU activation)

Batch Normalization & Dropout (0.3)

Hidden Layer 1: Dense (128 units, ReLU activation)

Dropout (0.3)

Hidden Layer 2: Dense (64 units, ReLU activation)

Dropout (0.2)

Output Layer: Dense (27 units, Softmax activation for multi-class classification)

The model was trained using the Adam optimizer, sparse_categorical_crossentropy loss, and an EarlyStopping callback to prevent overfitting.

Technologies Used
Python 3

Pandas: For data manipulation and analysis.

Scikit-learn: For data preprocessing (StandardScaler, LabelEncoder) and baseline modeling.

TensorFlow / Keras: For building and training the final deep learning model.

Matplotlib: For data visualization.

Joblib: For saving the preprocessor objects.

Streamlit (for the app): To create an interactive web application for model inference.



#Scarf Detection System with Transfer Learning
This project implements a lightweight yet powerful computer vision system using a Convolutional Neural Network (CNN) for the binary classification of images, determining the presence of a scarf. The system is built on TensorFlow/Keras and utilizes the MobileNetV2 architecture, providing a complete end-to-end pipeline for training, evaluation, and interactive deployment.

##🎯 Project Goals
Build and Fine-Tune a high-efficiency CNN model (MobileNetV2) via Transfer Learning to achieve optimal accuracy.

Accurately classify aerial images into "With Scarf" or "Without Scarf" classes.

Prevent Overfitting using data augmentation, Early Stopping, and learning rate reduction strategies.

Deploy a seamless, interactive prediction interface within the Kaggle notebook environment for real-time demonstration.

##📂 Dataset
This project is trained and evaluated using the Scarf Detection Dataset, which contains:

A pre-split collection of images organized into dedicated Train, Valid, and Test sets.

The data is processed using Keras's ImageDataGenerator, including robust Data Augmentation techniques (rotation, zoom, shift) to enhance model generalization.

The dataset is accessed directly within the Kaggle environment, ensuring immediate and consistent data access.

##⚙️ Main Steps
Data Preprocessing: Images are loaded, resized to 224×224, and normalized using the ImageDataGenerator.

Model Definition: The MobileNetV2 base model is loaded with ImageNet weights, initially frozen for feature extraction. A custom classification head is added.

Fine-Tuning: The model is recompiled with a low learning rate (1e−5) and the top layers of MobileNetV2 are unfrozen, allowing subtle weight adjustments.

Training & Validation: The model is trained using Model Checkpointing and Early Stopping based on validation accuracy, and the best weights are saved.

Interactive Deployment: The final model is integrated with an ipywidgets FileUpload button that triggers the prediction function, displays the image, and outputs the binary classification result and confidence score.

##📊 Output Example
Training Performance: High final test accuracy (e.g., 94.07%) on the unseen test set, demonstrating the model's ability to generalize features learned by MobileNetV2.

Prediction System: The interactive system runs seamlessly on Kaggle, simulating instant decision-making. Upon image upload, the output shows:

Prediction: This is a scarf image. (Confidence: 0.98)

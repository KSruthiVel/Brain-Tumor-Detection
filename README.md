<h1 align="center">Brain Tumor Detection: Analysis of Model Performance with Dataset Poisoning</h1>

This project utilizes Convolutional Neural Networks (CNNs) to detect brain tumors from MRI images, aiming to support medical professionals by providing an automated diagnostic tool. In addition to tumor detection, the project explores the impact of **data poisoning**—a form of adversarial attack—on the model’s performance. Through a controlled experiment, the study highlights the significant effect that data integrity has on machine learning models used in medical diagnostics.

### Key Features:
- **Automated Tumor Classification**: The model classifies MRI images into four categories: glioma, meningioma, pituitary tumor, and normal brain scans.
- **Data Augmentation**: To improve generalization, the model employs data augmentation techniques such as image rescaling, rotation, and horizontal flipping.
- **Data Poisoning Experiment**: A controlled experiment where 50% of the training labels are flipped to simulate a data poisoning attack. The model's performance under these conditions is analyzed.
- **Robust Evaluation Metrics**: The project tracks accuracy and loss to evaluate how data poisoning affects model reliability.

## Dataset Description
The dataset used in this project is the **"Refined Brain Tumor Image Dataset with Grayscale Normalization and Zoom"**, sourced from Kaggle. It contains MRI images categorized into four distinct classes:

- Glioma Tumor
- Meningioma Tumor
- Pituitary Tumor
- Normal Brain
  
![image](https://github.com/user-attachments/assets/65530aa3-622b-402a-875d-0d5b1ce37432)

All images are preprocessed to a consistent resolution of **256x256 pixels** in grayscale format, which simplifies the image processing and improves model training efficiency.
## Project Structure
### Data Preprocessing:
- Standardizes images by converting them to grayscale and resizing them.
- Applies data augmentation techniques like rescaling, rotation (up to 18 degrees), and horizontal flipping to enhance the model's robustness.

### CNN Model Architecture:
- **Convolutional Layers**: The model begins with three convolutional layers, progressively extracting features of increasing complexity from the input images.
- **Pooling and Dropout**: Max pooling layers reduce spatial dimensions, and dropout layers prevent overfitting by randomly deactivating neurons during training.
- **Fully Connected Layers**: The extracted features are passed through dense layers for final classification into one of the four categories.
- **Output Layer**: Uses a softmax activation function to produce probability scores for each class.

### Data Poisoning Experiment:
- A controlled dataset poisoning scenario is introduced by flipping 50% of the labels in the training data.
- The goal is to analyze how poisoning affects the model's ability to classify brain tumors correctly and highlight the importance of data integrity.

![image](https://github.com/user-attachments/assets/1469d2de-dc5d-4709-ae19-2fd409f9e007)

## Evaluation Metrics:
Two primary metrics are used to evaluate model performance:
- **Accuracy**: Measures the proportion of correct predictions.
- **Loss**: Measures how far off the model's predictions are from the true labels using categorical cross-entropy.

## Results:
The base model (clean dataset) achieved:
- **Validation Accuracy**: 82.94%
- **Final Training Loss**: 0.7806

The poisoned model (50% label flipping) showed significantly degraded performance:
- **Validation Accuracy**: 40.62%
- **Final Loss**: 1.1486

![image](https://github.com/user-attachments/assets/f647ad90-3364-41c5-8817-e10a6c6ef0bc)

The results illustrate the severe impact of data poisoning on CNN model performance and underscore the importance of ensuring data integrity.

This project aims to implement a convolutional neural network (CNN) using PyTorch to classify handwritten digits from the MNIST dataset. The project is divided into multiple steps, each focusing on different aspects of model optimization and improvement.

## Step 1: Basic Setup and Batch Normalization

**Target:**
- Set up basic components including data transforms, data loader, model architecture, training, and test loop.
- Incorporate batch normalization to improve model efficiency.

**Results:**
- Parameters: 9,830
-Best Training Accuracy: 99.64%
- Best Test Accuracy: 99.25%

**Analysis:**
- Model parameters can be reduced to less than 8k, indicating scope for model optimization.
- The model is overfitting, as the training accuracy is higher than the test accuracy.
- Batch normalization helps stabilize and accelerate training.

## Step 2: Regularization and Model Optimization

**Target:**
- Address overfitting by adding regularization techniques such as dropout and reducing model capacity.
- Implement global average pooling (GAP) to reduce model parameters.

**Results:**
- Parameters: 7,560
- Best Training Accuracy: 98.91%
- Best Test Accuracy: 99.28%

**Analysis:**
- Model parameters reduced to 7.5k, enhancing model efficiency.
- Overfitting is mitigated, but there's room for improvement in accuracy.
- The addition of regularization techniques improves generalization performance.

## Step 3: Data Augmentation and Learning Rate Scheduling

**Target:**
- Focus on improving accuracy by introducing data augmentation techniques such as rotation.
- Implement a learning rate scheduler to optimize learning rate during training.

**Results:**
- Parameters: 7,416
- Best Training Accuracy: 99.03%
- Best Test Accuracy: 99.44%

**Analysis:**
- Model achieves target accuracy without overfitting, indicating successful regularization and optimization.
- Learning rate scheduling effectively optimizes learning rate, leading to faster convergence.
- Rotation augmentation improves accuracy, particularly with (-5.0, 5.0) rotation, showcasing the importance of data augmentation in improving model performance.

## Instructions for Running Jupyter Notebooks:
- Step1_Basic_Setup.ipynb: Contains code for setting up basic components and adding batch normalization.
- Step2_Regularization_Optimization.ipynb: Implements regularization techniques and model optimization strategies.
- Step3_Data_Augmentation_LR_Scheduler.ipynb: Introduces data augmentation and learning rate scheduling for accuracy improvement.

## Requirements:
- Python 3.x
- PyTorch
- torchvision
- Jupyter Notebook

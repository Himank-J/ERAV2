# Analysis of Normalization Techniques on CIFAR Dataset

## Overview:
In this project, we implemented and compared the performance of three normalization techniques, namely Batch Normalization, Layer Normalization, and Group Normalization, on the CIFAR dataset. Each technique was applied to a convolutional neural network (CNN), and their respective performances were evaluated in terms of test accuracy and model parameters.

## Experimental Setup:

- Dataset: CIFAR (Canadian Institute for Advanced Research) dataset, consisting of 60,000 32x32 color images in 10 classes.
- Model: Convolutional Neural Network (CNN) architecture.
- Normalization Techniques: Batch Normalization, Layer Normalization, and Group Normalization.

## Findings:
Based on the experiments conducted, the following observations were made:

- Batch Normalization (BN):

  - Parameters: 48k
  - Test Accuracy (1st run): 74.30%
  - Test Accuracy (2nd run): 72.24%
  - Batch normalization yielded relatively high test accuracy, indicating effective stabilization of the training process. However, there was a slight decrease in accuracy in the second run, suggesting some sensitivity to variations in training.
  - Misclassified Images:
    
  ![image](https://github.com/Himank-J/ERAV2/assets/55919214/24164c99-943d-447a-a498-d0abcecf4800)

  - Loss Graph

  ![image](https://github.com/Himank-J/ERAV2/assets/55919214/774b74f1-3cdd-4c67-bb54-600a8cebafb4)


- Layer Normalization (LN):

  - Parameters: 50k
  - Test Accuracy (1st run): 54.96%
  - Test Accuracy (2nd run): 55.69%
  - Layer normalization resulted in lower test accuracy compared to batch normalization. However, it exhibited no signs of overfitting, which could be advantageous in certain scenarios.
  - Misclassified images -
 
  ![image](https://github.com/Himank-J/ERAV2/assets/55919214/a25fa89d-13df-4e0e-9459-91987d0e5b18)

  - Loss Graph

  ![image](https://github.com/Himank-J/ERAV2/assets/55919214/a319b51d-c0be-46e7-88bc-8adf32a8720c)


- Group Normalization (GN):

  - Parameters: 48k
  - Test Accuracy (1st run): 73.40%
  - Test Accuracy (2nd run): 71.23%
  - Group normalization showed performance similar to batch normalization in terms of test accuracy. It also maintained consistency across runs, indicating robustness to variations in training.
  - Misclassified Images:

  ![image](https://github.com/Himank-J/ERAV2/assets/55919214/fae04e7d-81fd-4cd1-b268-00e6d7246ed9)

  - Loss Graph
 
  ![image](https://github.com/Himank-J/ERAV2/assets/55919214/8b62a9cc-df55-4397-add2-ef80864c9562)



## Conclusion:

- Batch Normalization demonstrated the highest test accuracy among the three techniques, although it exhibited some sensitivity to variations in training.
- Layer Normalization, while not achieving the highest accuracy, showed no signs of overfitting, which could be beneficial for certain applications.
- Group Normalization provided a viable alternative to batch normalization, offering competitive performance with robustness to training variations.

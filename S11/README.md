# GradCam Visualization of CIFAR-10 dataset with Albumentations

This PyTorch project focuses on building and training a RESNET18 deep learning model on the CIFAR-10 dataset. It includes various features such as data augmentation using the Albumentations library, a custom dataset loader, plotting train and test loss curves, GradCam visualization of randomly sampled misclassified images, and visualization of misclassified images with labels and appropriate legends.

## Training and Evaluation

1. Train the Model:

   To train the model on the CIFAR-10 dataset for 20 epochs, run the following command:

   ```bash
   python main.py
   ```
   OR
   Run main.ipynb in jupyter notebook.

2. Evaluate the Model:

   After training, the model's performance will be evaluated on the test dataset automatically.

## Data Augmentation

In this project, data augmentation is performed using the Albumentations library. Augmentations like RandomCrop and Cutout are applied to the training data to enhance the model's generalization.

## Custom CIFAR-10 Dataset Loader

The project includes a custom dataset loader for CIFAR-10. The `CustomCIFAR10` class extends the PyTorch `Dataset` class and allows you to customize the data loading process.

## Loss Curve Visualization
![image](https://github.com/Himank-J/ERAV2/assets/55919214/f7422aee-b601-4469-9a33-3db649286a20)


## Misclassified Image Visualization
![image](https://github.com/Himank-J/ERAV2/assets/55919214/91dff9ad-011d-478f-9664-218529c8224f)


## GradCam Visualization of Misclassified Images

GradCam is used to visualize the regions of interest in the misclassified images that contribute to the model's predictions. The `gradcam.py` script can be used to apply GradCam to randomly sampled misclassified images.

![image](https://github.com/Himank-J/ERAV2/assets/55919214/825088ba-cb2d-4c3b-9db7-0080a69d1b26)


## Conclusion

This PyTorch CIFAR-10 project provides a comprehensive pipeline for training and evaluating deep learning models on the CIFAR-10 dataset. With data augmentation, custom dataset loading, loss curve visualization, GradCam visualization, and misclassified image visualization, you can gain insights into the model's performance and identify misclassifications. Feel free to explore and modify the code to suit your needs and experiment with different model architectures and hyperparameters.

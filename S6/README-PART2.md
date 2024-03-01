# Neural Network for Recognizing Handwritten Digits (MNIST Dataset)
This is a simple neural network written in Python using the PyTorch library. The purpose of this neural network is to recognize handwritten digits from the MNIST dataset.

## Getting Started
### Prerequisites

Make sure you have Python and PyTorch installed on your system.

``` bash
pip install torch torchvision tqdm
```

### Training the Model
To train the model, run the following command:

```bash
python train_model.py
```
This will train the neural network on the MNIST dataset for 20 epochs.

### Model Architecture
The neural network architecture consists of convolutional layers, batch normalization, max-pooling, dropout, and an adaptive average pooling layer. It is designed to efficiently learn and recognize patterns in handwritten digits.

- Convolutional Layer (Conv1): Input channels=1, Output channels=16, Kernel size=3x3, Padding=1, Batch Normalization, ReLU activation
- Convolutional Layer (Conv2): Input channels=16, Output channels=16, Kernel size=3x3, Padding=1, Batch Normalization, ReLU activation
- Max Pooling Layer (Pool1): 2x2 kernel, Stride=2
- Convolutional Layer (Conv3): Input channels=16, Output channels=32, Kernel size=3x3, Padding=1, Batch Normalization, ReLU activation
- Convolutional Layer (Conv4): Input channels=32, Output channels=32, Kernel size=3x3, Padding=1, Batch Normalization, ReLU activation
- Dropout Layer: Dropout rate=0.2
- Convolutional Layer (Conv5): Input channels=32, Output channels=10, Kernel size=3x3, Padding=1

The output from Conv5 goes through a Global Average Pooling layer, which reduces the spatial dimensions to 1x1. The final output is passed through a LogSoftmax activation.

### Results
After training for 20 epochs, the model achieves an accuracy of around 99% on the test set.

### Additional Information
#### Learning Rate Scheduler
A learning rate scheduler is used to adjust the learning rate during training, which can help improve the model's performance. In this case, a StepLR scheduler is used with a step size of 15 epochs and a gamma value of 0.1.

### Hyperparameters

- Learning Rate: 0.01
- Batch Size: 512
- Dropout Rate: 0.2

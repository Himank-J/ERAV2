# Session 22 - UNET and VAE

## Objective

1. UNet - Train with the below four variations of architecture/loss

    MP+Tr+BCE
    
    MP+Tr+Dice Loss
    
    StrConv+Tr+BCE
    
    StrConv+Ups+Dice Loss
    
2. VAE - For the following dataset customize to have an input (image and label)

    MNIST
    
    CIFAR10


## Result

### 1. Example of prediction using UNet 
![results](./results/unet_results.png)

### 2. VAE

    A. MNIST --> Input image + 25 different iterations of wrong label
![results](./results/mnist_vae_results.png)


    B. CIFAR10 --> Input image + 25 different iterations of wrong label
![results](./results/cifar_vae_results.png)

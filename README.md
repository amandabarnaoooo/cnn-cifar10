# CNN for CIFAR-10 Classification

This project implements a Convolutional Neural Network (CNN) based on the classic LeNet architecture, extended with modern techniques like dropout, batch normalisation, and advanced data augmentation to evaluate the performance of a CNN using modern methods and hyperparameter optimisation. The model is trained and evaluated on the CIFAR-10 dataset using PyTorch.

## Project Overview

- Dataset: CIFAR-10
- Model 1: Vanilla LeNet-5 CNN
- Model 2: Improved CNN with modern enhancements 
- Goal: Improve classification accuracy using deeper architecture and better regularisation

## Results

Starting from the original LeNet-5 architecture, I made the following step-by-step changes to improve test accuracy and reduce overfitting:

1. **Max Pooling Instead of Average Pooling:**
I replaced average pooling with max pooling to preserve stronger spatial features. This led to a small improvement in validation accuracy (~57.8%).

2. **Dropout for Regularisation:**
My model showed signs of overfitting (training loss improving, validation loss worsening), so I added 30% dropout after the first fully connected layer. This reduced overfitting, as the gap between training and validation loss narrowed, though accuracy remained mostly unchanged.

3. **Data Augmentation:**
To increase training data diversity and improve generalisation, I applied random transformations including cropping, flipping, rotation, and colour jitter. This helped the model learn more robust features, though regularisation slightly reduced early training accuracy.

4. **Smaller Kernels and Deeper Architecture:**
Switching from 5x5 to 3x3 kernels improved accuracy to ~78% by capturing more local patterns. Adding more convolutional layers and feature maps further boosted accuracy (~82%) by enabling richer representations - these made the biggest improvement!

5. **Additional Regularisation and Training Adjustments:**
I added weight decay and label smoothing to improve generalisation. Increasing epochs to 60 allowed more time for convergence, ultimately achieving ~87% test accuracy (~75% by epoch 10).

Overall, the model improved significantly from the classic LeNet-5 (~56% to ~87% accuracy) due to deeper layers, stronger regularisation, and data augmentation. Validation loss was unstable early on due to strong regularisation and data augmentation but eventually stabilised. The confusion matrix and per-class accuracy chart show balanced performance, with highest accuracy on structured objects like automobiles, and lower accuracy on visually similar classes like cats and dogs. These brought accuracy down, so to further improve, I could use advanced augmentation, deeper architecture with attention, or oversampling for difficult classes. With more compute, increasing neuron count or training an ensemble might push test accuracy beyond 90%.


## Requirements
See `requirements.txt` for dependencies.

## Author
Amanda Barnao – [LinkedIn](https://linkedin.com/in/amanda-barnao)
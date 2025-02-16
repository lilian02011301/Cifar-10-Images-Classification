# Cifar-10-Images-Classification
The goal of this project is to implement a Neural Network to predict the image content with a desired architecture.

# Basic architecture
The architecture is composed of a sequence of intermediate blocks B1, B2, . . . , BK that are followed by an output block O, as shown in the following figure. These blocks are detailed in the following subsections.

<img width="337" alt="截圖 2025-02-16 23 20 28" src="https://github.com/user-attachments/assets/be5ae224-4abb-4c51-84e2-e3febb3536a9" />


# Dataset
The CIFAR-10 dataset used in this project is loaded into PyTorch DataLoaders to facilitate efficient training and testing procedures. The dataset can be explored more at CIFAR-10 dataset.

# Intermediate block
An intermediate block receives an image x and outputs an image x′. Each block has L independent convolutional layers. Each convolutional layer Cl in a block receives the input image x and outputs an image Cl(x). Each of
these images is combined into the single output image x′, which is given by x′ = a1C1(x) + a2C2(x) + . . . + aLCL(x), where a = [a1, a2, . . . , aL]T is a vector that is also computed by the block. Note that each convolutional 
layer in a block receives the same input image x (and not the output of another convolutional layer within the block).
Suppose that the input image x has c channels. In order to compute the vector a, the average value of each channel of x is computed and stored into a c-dimensional vector m. The vector m is the input to a fully
connected layer that outputs the vector a. Note that this fully connected layer should have as many units as there are convolutional layers in the block. Each block in the basic architecture may have a different number of convolutional layers, and each convolutional
layer may have different hyperparameters (within or across blocks). However, every convolutional layer within a block should output an image with the same shape.

# Output block
The output block receives an image x (output of the last intermediate block) and outputs a logits vector o. Suppose that the input image x has c channels. In order to compute the vector o, the average value of each
channel of x is computed and stored into a c-dimensional vector m. The vector m is the input to a sequence of zero or more fully connected layer(s) that output the vector o.


# Final result
- Loss Plot: The trend shows a general decrease in cross-entropy loss over training batches, indicating that the model is learning and improving its predictions over time. The spikes in the plot suggest instances where the
batch of data might have been particularly challenging or diOerent from the model's previous experience, leading to momentary increases in loss. Accuracy Plot: Include a plot showing both training accuracy and testing
accuracy across epochs. Highlight any key observations.
- Highest Accuracy: The highest accuracy obtained on the training and testing dataset is 95.5% and 80.9%. The accuracy plot reveals an interesting dynamic: the training accuracy consistently increases over epochs,
demonstrating that the model is eOectively learning from the training data. 
<img width="709" alt="截圖 2025-02-16 23 19 48" src="https://github.com/user-attachments/assets/4dba5ecd-267d-46b0-a461-c3fcd9859ff3" />

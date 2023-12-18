---
tags:
  - neural-networks
  - supervised-learning
  - classification
---
# Convolutional Neural Networks (CNNs)

Types of image recognition tasks:

- Classification: Is this image a cat or a dog?
- Object detection: Label the things in the image
- Semantic segmentation: Which pixels are cats or dogs?

Images have structure: a white pixel will probably have whitish pixels around it
- Old neural networks instead treated images as 1D arrays and ignored structure

**Channel:** Three channels: red, green, and blue

## Hidden layers

At each step, there are three hidden layers working in parallel (one for each color channel)

Each hidden layer can find different features (patterns/shapes) in the image (e.g., one might find lines)

The hidden layers are convolutional layers

### Convolutional layers

Every node in the hidden layer will have a **local receptive field** (a small subset of neurons that go into activating it)
- It will look at only a small square from the input (say, 4x4)
- Its neighbor's square can overlap with it but it won't be the exact same square (shifted over by the **stride**)
	- **Stride:** How much you shift the window/kernel each time
- To get a single number out of that small square:
	- Matrix multiply that small square with a **kernel** (which would be a 4x4 matrix)
	- Fardina calls this "dot product"
	- Sum up all the elements of that matrix

Every node in the entire layer uses the same weights (same kernel)

### Kernel

- The weights of the kernel are learned parameters
- The size of the kernel is a hyperparameter

## Activation layer

After convolutional layer comes an activation function

For images, use [ReLU](Activation%20functions.md#ReLU) rather than sigmoid as the activation function

- Introduces non-linearity to the network (necessary for learning complex patterns)
- ReLU is a simple linear function itself

## Pooling layers

Between the convolutional layers are pooling layers

Instead of using weights, we aggregate the pixels we're responsible for

Max pooling layer: Just finds the max value in each small grid

## Final layer

Fully connected layer and an output layer

- Flatten the grid
- Do classification

## Training Process

- Show the network N pictures, where N is your **batch size**
	- Slides say that higher batch size will **underfit**, lower batch size will **overfit**
	- Yes that's correct, *not* the other way around
- Use the backpropagation algorithm, but randomly pick some number of weights to not update (set to 0), based on your **dropout rate**
	- A higher dropout rate will prevent overfitting and make training go faster
	- Too high and it underfits
- Repeat until network loss stops decreasing

## Transfer Learning

Can use [transfer learning](../Transfer%20Learning.md)

One common approach is to adjust the final output layer to match number of classes in new task
- No need to change the convolutional layers

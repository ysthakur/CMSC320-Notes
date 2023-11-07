---
tags:
  - neural-networks
---

Types of image recognition tasks:

- Classification: Is this image a cat or a dog?
- Object detection: Label the things in the image
- Semantic segmentation: Which pixels are cats or dogs?

Images have structure: a white pixel will probably have whitish pixels around it
- Old neural networks instead treated images as 1D arrays and ignored structure

## Hidden layers

There are multiple hidden layers

Each hidden layer can find different features (patterns/shapes) in the image (e.g., one might find lines)

The hidden layers are convolutional layers

### Convolutional layers

Every node in the hidden layer will have a **local receptive field** (a small subset of neurons that go into activating it)
- It will look at only a small square from the input (say, 6x6)
- Its neighbor's square can overlap with it but it won't be the exact same square (shifted over by one)

Every node in the entire layer uses the same weights

## Pooling layers

Between the convolutional layers are pooling layers

Instead of using weights, we aggregate the pixels we're responsible for

Max pooling layer: Just finds the max value in each small grid

## Final layer

Fully connected layer and an output layer

## Training Process

- Show the network N pictures, where N is your **batch size**
	- Slides say that higher batch size will underfit, lower batch size will overfit
	- ==TODO check if that's true, it seems the wrong way around==
- Use the backpropagation algorithm, but randomly pick some number of weights to not update, based on your **dropout rate**
	- A higher dropout rate will prevent overfitting and make training go faster
	- Too high and it underfits
- Repeat until network loss stops decreasing
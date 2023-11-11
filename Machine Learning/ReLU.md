Rectified linear unit is an activation function

It's an alternative to sigmoid function that's more popular for [Convolutional Neural Networks](Convolutional%20Neural%20Networks.md):

- Faster to compute than sigmoid
- Useful if you only want positive values

Function:

- If input is negative or 0, output is 0
- If input is positive, output is equal to input

![relu](relu.png)
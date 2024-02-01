## Quick review of training gradients

Imagine we're trying to predict a single output value $y$ from a single input value $x$ using a simple neural network. The network's prediction $\hat{y}$ is given by $\hat{y} = wx + b$

Where:

- $w$ is the weight of the connection between the input and output neuron.
- $b$ is the bias.
- $x$ is the input.

## Objective of our training

- want to adjust $w$ and $b$ to get $\hat{y}$ close to real $y$
- measure how we're doing with *loss*
- example choice: MSE, $L = \frac{1}{2}(y - \hat{y})^2$

## Training Gradients in this example

Training gradients indicate in which direction (and by how much) we should adjust our params to minimize loss

To find these gradients, we use backpropagation, which involves calculating the derivative of the loss function with respect to each parameter:

## Gradient wrt $w$

$\frac{\partial L}{\partial w} = -(y - \hat{y} ) \cdot x$

tells how a small change in $w$ affects loss. 

If $\frac{\partial L}{\partial w}$ is positive, increasing $w$ will increase the loss, so we should decrease $w$ to reduce the loss.

## Gradient wrt $b$

$\frac{\partial L}{\partial b} = -(y - \hat{y})$

tells us how a small change in $b$ affects the loss. Similarly, if $\frac{\partial L}{\partial b}$ is positive, increasing $b$ will increase the loss, so we should decrease $b$ to reduce the loss.

## Updating

We update $w$ and $b$ using a learning rate $\eta$ (a kind of step size, how far we adjust things based on the direction of our gradients):

$w = w - \eta \frac{\partial L}{\partial w}$

$b = b - \eta \frac{\partial L}{\partial b}$

### Iteration

This process is repeated for many iterations (or epochs) over the training data, gradually reducing the loss and making the predictions $\hat{y}$ closer to the actual outputs $y$
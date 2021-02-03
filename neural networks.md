# Artificial Neural Networks

A neural network can be used to approximate any function.

## Perceptron Model

![[imgs/Screen Shot 2021-02-02 at 7.15.48 PM.png]]

- Bias
- Weights

![[imgs/Screen Shot 2021-02-02 at 7.13.35 PM.png]]

- Perceptron Rule
- Gradient Descent Rule / Delta Rule
- Sigmoid Function (see below)


## Binary Classification Activation Functions
- Activation Functions
	- Step Function: outputs 0 or 1. Ideal for binary classification.
	- Sigmoid Function (logistic function)
![[imgs/Screen Shot 2021-02-02 at 7.29.41 PM.png]]
	- Hyperbolic tangent: tanh(z)
![[imgs/Screen Shot 2021-02-02 at 7.29.41 PM 1.png]]
	- Rectified Linear Unit
		- Good performance especially when dealing with vanishing gradient.
	- Softmax Activation Function
		- Calculates the probabilities distribution of the event over K different events.
		- This function will calculate the probabilities of each target class over all possible target classes.
![[imgs/Screen Shot 2021-02-02 at 9.43.45 PM 1.png]]

## Multiclass Activation Functions
- Output layer has multiple neurons
- One-hot encoding (dummy variables)
- Exclusive vs. Non-exclusive
- If non-exclusive, then you can use a sigmoid function.

- Feedforward network: All the information is going from the input layer all the way to the output layer.
- Backpropogation
- Deep Neural Network: A neural network that has two or more hidden layers.

## Cost Functions
- [[ANN cost functions]] A measure of how far off a prediction is from the true value. It should be an average.
- Quadratic Cost Function
	- Notice that squaring does two things. First, it keeps everything positive. Second, punished large errors.
	- Note that in **a(x)** holds information about the weights and biases.
![[imgs/Screen Shot 2021-02-02 at 9.57.56 PM.png]]

![[imgs/Screen Shot 2021-02-02 at 9.58.49 PM.png]]

![[imgs/Screen Shot 2021-02-02 at 10.01.09 PM.png]]

- Gradient Descent
	- Learning Rate: step size used for finding the local minimum value.
- Cross Entropy Cost Function
	- Commonly used for classification problems
	- The assumption is that your model predicts a probability distribution for each class.

![[imgs/Screen Shot 2021-02-02 at 10.10.40 PM.png]]

## Backpropagation

[[backpropagation]]

## Bias

- Restriction bias: Representional power of the model, i.e. the set of all hypothesis considered.
	- Perceptron unit: restricted to linear functions
	- Sigmoids: more complex, not much restriction
	- Can represent Boolean, continuous functions, and really any arbitrary function
	- Neural networks are not restrictive so long as they have sufficiently complex network structure.
	- Danger of overfitting since ANNs can represent any function.
		- Typically give a network bounds on the number of layers, nodes, and weights. So, not every ANN structure can represent any arbitrary function.
		- Use cross validation to determine how many layers, nodes, and when to stop training.
- Preference bias: Why an algorithm would prefer one representation over another.
	- If starting out with small random values, then starting with low complexity. Slow prefer simpler explanations. 
		- Occam's Razor: entities should not be multiplied unnecessarily
		- Will get better generalization with simpler theories.
	- Prefer correct answers.

## Dangers
- Overfitting
- Large weights can lead to overfitting
- Initial weights: small random values (helps avoid local minima)

## Optimizing
- Momentum: During gradient descent, continue in the direction the descent is moving to avoid getting stuck in local minimums.
- Higher order derivatives
- Randomized optimization
- Penality for complexity
	- More nodes or more layers or large weights
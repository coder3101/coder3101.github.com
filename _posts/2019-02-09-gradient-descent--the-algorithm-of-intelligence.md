---
mathjax: true
title: Gradient Descent - The Algorithm of Intelligence
categories: NeuralNets
featured-img: gradient_descent
---

In the last post we learned about loss functions that help us determine how well or poor our neural networks are performing. However We did not talked about how to cause our neural neural network to minimise that loss. In this post we will talk about Gradient descent Algorithm which slowly reduces the loss of our model. It is no big deal, you just need some basics of Derivatives and what they actually represent. It will be very good if you know these things, but if you don't you can still follow.

### Recall

Before we begin it is very important that you must know where a neural network holds its intelligence. It is the values of weight and biases. In [this](https://coder3101.github.io/understanding-a-complete-neural-net/) post I briefly discussed how intelligence is embedded in the values of weights and biases. We also talked about training our network which involves getting the perfect values of weights and biases. In this post we will learn how do we actually change the values of weights and biases during training. Let's get started



## Backpropagation

We talked about Forward Propagation in [this](https://coder3101.github.io/understanding-a-complete-neural-net/) post. Forward Propagation is the pass in which computation flowed from input layer to output layer. "*input times weight, add a bias, activate*" , this statement beautifully describes what  forward pass/propagation actually does. For More you can read [this](https://coder3101.github.io/understanding-a-complete-neural-net/) post.

Today we will talk about Backward pass or Back Propagation. As evident from the name it is opposite to forward propagation. **The computation flow from the output layer to the input layer**, updating all the weights and biases of the network in such a way that minimises the loss of the network. Here is what actually happens "*output gives loss, propagate it up-to input, update all parameters in the path*". 

<center>
    <img src="https://raw.githubusercontent.com/coder3101/coder3101.github.com/master/in-post_imgs/gradient-descent-algorithm-of-intelligence/backward_forward.png">
</center>


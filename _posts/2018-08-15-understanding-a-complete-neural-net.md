---
mathjax: true
title: Understanding a Complete Neural Network
categories: NeuralNets
featured-img: CompleteNet
---

In this post I will explain the complete Neural Network and the intuition about how a neural network learns from data.

By the end of this post, you will have the in-depth understanding of forward propagation in a feed-forward neural network. I will focus on the math part as well and we will be using [numpy](https://pypi.org/project/numpy/) for numerical calculations in python. In the end, you will be able to implement the complete neural network with forward propagation.

This post assumes that you have an basic understanding of activation functions and are familiar with terms like weights and biases. If all these seem alien to you. Read [this](https://coder3101.github.io/understanding-ff-nn/)  and come back here again.

## A Neural Network 

<p align="center"><img src="https://github.com/coder3101/coder3101.github.com/raw/master/in-post_imgs/understanding-a-complete-neural-net/full-complete-net.jpg" width="70%" />

</p>



As you are already familiar with what a single neuron computes from my previous post. When we arrange many such neurons such that each neuron gets same input values but have different weights they form a **Layer** (In above picture, Vertical Stack of Neurons is a Layer).

All the layers apart from input and output layers are called **Hidden layers**.

The layer that gets value from us is the **Input Layer**.

The layer of Neurons that hold the ouput values by the network is the **Output Layer**. It can have any number of Neurons. In the picture above there is only one neuron in the output layer.

The Un-activated value of a neuron is generally referred to as **Logits**. For Example In the last post we talked about Relu activation being applied to weighed sum, if we do not apply that relu the results we have is called logit.

### Some Properties of Layers

- Activation Function used for all the neurons in a layer must be same. In a layer you should not apply relu to some neurons and some other activation function to other neurons. However, You can apply different activations in different layers.
- Number of layers is directly proportional to learning capacity of the network.
- You get the freedom to choose the number of hidden layers and number of neurons in each hidden layer (These things that are in your hand to change are sometimes called Hyper-parameters). But the Input Layer and Output Layer will be according to your Data.
- No two neurons in the same layer are connected with others. Rather Every Neuron in a Layer is connected with all the other neurons from Previous Layer. This forms a dense connection of Weights. Hence such layers are also sometimes referred by name "Dense" in some programming frameworks.



## Neural Network as Universal Function Approximator

If you hold a mathematical background you might be familiar with this :

<p align="center">



$$\huge{y = f(x_1,x_2,x_3)} $$

</p>

The Neural Network shown in the above picture is exactly this function $f$ . Our Neural Network takes three Input values through Input Layer and Produces a Single output $y$ .

But How do we define that $f$ ?

Remember the Complete Neural Network is just a collection of many neurons. So output of complete neural network depends on the output of each neuron.

Now, a Neuron's output depend on 3 things (Weights,bias and Input). We cannot change the Input directly that is fixed. The only way to change the output is to change the weights and biases of individual neuron. Great, but how do we choose values of Weights and biases that gives the expected results. Here comes the training part, We use an algorithm called Gradient Descent that fine tunes the values of all weights and biases of the all the neurons. So, We Initially set some random values to weights and biases and let the training fine tune it for us. We will talk about Back Propagation and Gradient Descent in  some other Post.

So choosing all the possible values of all the weights and biases will give us all possible definition of $f$. This way our Neural network can approximate all most all $f$, and thus it is called *Universal Function Approximator*

*Please Note : I do not mean the above Neural Network in the Picture can approximate all the functions. It will fail to approximate complex functions so to overcome this we build more sophisticated networks with Hundred of Layers and many neurons with regularization*.



## Building a Neural Network : The Math Part

In the previous post I told you how `weights` and `inputs` are multiplied, added with `bias` and activated with non-linearity like `relu`

I also showed you how we can do all those operations using Matrices.

Consider this Simple Neural Network.

<p align="center">

<img src="https://github.com/coder3101/coder3101.github.com/raw/master/in-post_imgs/understanding-a-complete-neural-net/simple-net.jpg"/>

</p>
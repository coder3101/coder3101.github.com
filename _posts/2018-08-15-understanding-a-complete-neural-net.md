---
mathjax: true
title: Understanding a Complete Neural Network
categories: NeuralNets
featured-img: CompleteNet
---

In this post I will explain the complete Neural Network and the intuition about how a neural network learns from data.

By the end of this post, you will have the in-depth understanding of forward propagation in a feed-forward neural network. I will focus on the math part as well and we will be using [numpy](https://pypi.org/project/numpy/) for numerical calculations in python. In the end, you will be able to implement the complete neural network with forward propagation.

This post assumes that you have an basic understanding of activation functions and are familiar with terms like weights and biases. If all these seem alien to you. Read [this](https://coder3101.github.io/understanding-ff-nn/)  and come back here again.

### A Neural Network 

<p align="center"><img src="https://github.com/coder3101/coder3101.github.com/raw/master/in-post_imgs/understanding-a-complete-neural-net/full-complete-net.jpg" width="70%" />

</p>



 Before we dive into the the maths and code of it. We need to get familiar with what we mean when we say "*Hidden Layers*" or "*5-layered neural network*" or "*Input layers*" and "*logits*". Let's define them :

1. **Layers** : As you are already familiar with what a single neuron computes from my previous post. When we arrange many such neurons such that each neuron gets same input values but have different weights they form a layer (In above picture, Vertical Stack of Neurons is a Layer).
2. **Hidden Layer** : Layers apart from input and output layers are called hidden layers. In this case we have two hidden layers. 
3. **Input Layer** : The layer that gets value from us is the Input Layer. In the above Picture, three values are placed in the neurons of input layers and those inputs flow through weights all the way upto output layer.
4. **Ouput Layer :** The Neuron that holds the ouput value by the network is the output layer. It can have any number of Neurons. In the picture above there is only one neuron in the output layer.
5. **Logits** : The Un-activated value of a neuron is generally referred to as logits. For Example In the last post we talked about Relu activation being applied to weighed sum, if we do not apply that relu the results we have is called logit(s).

### Some Properties of Layers

- Activation Function used for all the neurons in a layer must be same. In a layer you should not apply relu to some neurons and some other activation function to other neurons. However, You can apply different activations in different layers.
- Number of layers is directly proportional to learning capacity of the network.
- You get the freedom to choose the number of hidden layers and number of neurons in each hidden layer (These things that are in your hand to change are sometimes called Hyper-parameters). But the Input Layer and Output Layer will be according to your Data.
- No two neurons in the same layer are connected with others. Rather Every Neuron in a Layer is connected with all the other neurons from Previous Layer. This forms a dense connection of Weights. Hence such layers are also sometimes referred by name "Dense" in some programming frameworks.



### Neural Network as Universal Function Approximator

If you hold a mathematical background you might be familiar with this :

<p align="center">



$$\huge{y = f(x_1,x_2,x_3)} $$

</p>

The Neural Network shown in the above picture is exactly this function $f$ . Our Neural Network takes three Input values through Input Layer and Produces a Single output $y$ .

But How do we define that $f$ ?

Remember the Complete Neural Network is just a collection of many neurons. So output of complete neural network depends on the output of each neuron.

Now, a Neuron's output depend on 3 things (Weights,bias and Input). We cannot change the Input directly that is fixed. The only way to Change the Output is to Change the Weights and biases of the neuron. Great, but how do we choose values of Weights and biases that gives the expected results. Here comes the training part, We use an algorithm called back-propagation that fine tunes the values of all weights and biases of the all the neurons. These weights and baises are trainable parameter.So, We Initially set some random values to weights and biases and let the training fine tune it for us. We will talk Back Propagation in  some other Post.


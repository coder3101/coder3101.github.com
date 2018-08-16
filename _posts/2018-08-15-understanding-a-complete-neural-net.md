---
mathjax: true
title: Understanding a Complete Neural Network
categories: NeuralNets
featured-img: CompleteNet
---

Today in this post I will explain the Complete neural network and the intuition about how a neural network learns from data.

By the end of this post, you will have the in-depth understanding of forward and backward propagation in a feed-forward neural network. I will focus on the math part as well and we will be using [numpy](https://pypi.org/project/numpy/) for numerical calculations in python. In the end, you will be able to implement the complete neural network with forward porpagation.

This post assumes that you have an basic understanding of activation functions and are familiar with terms like weights and biases. If all these seem alien to you. Read [this](https://coder3101.github.io/understanding-ff-nn/)  and come back here again.

### A Neural Network 

<p align="center"><img src="https://github.com/coder3101/coder3101.github.com/raw/master/in-post_imgs/understanding-a-complete-neural-net/full-complete-net.jpg"/>

</p>



 Before we dive into the the maths and code of it. We need to get familiar with what we mean when we say "Hidden Layers" or "5-layered neural network" or Input layers, logits. Let's define them :

1. **Layers**: As you are already familiar with what a single neuron computes from my previous post. When we arrange many such neurons  they form a layer (Just like combining bricks build a wall). A layer holds a Unique Property, Every Neuron in a Layer is connected with all the other neurons from Previous Layer. This forms a dense connection of Weights. So such layers are also sometimes referred by name "Dense" in some programming frameworks. Total Number of layers in a above diagram is 3. We do not consider *input_layer* in count.
2. **Hidden Layers**: As evident from the name, the number of layers apart from input and output layers are called hidden layers. In this case we have 2 hidden layers. Hidden layers are sandwitched between the input and ouput layers. 
3. **Input Layers** : The layer that gets value from us is the Input Layer. From the above Picture, three values are placed in the neurons of input layers and then those inputs flow through weights all the way upto output layer.
4. **Ouput Layers :** The Neuron that holds the ouput value by the network is the output layer. It can have any number of Neurons. In the picture above there is only one neuron in the output layer.
5. **Logits** : This is related to the Neurons again. The Un-activated value of a neuron is generally referred to as logits. For Example In the last post we talked about Relu activation being applied to weighed sum, if we do not apply that relu the results we have is called logit(s). It is important that all the neurons of a layer spit unactivated values.



### Some Properties of Layers

- Activation Function used for all the neurons in a layer must be same. In a layer you should not apply relu to some neurons and some other activation function to other neurons. However, You can apply different activations in different layers.
- Number of layers is directly proportional to learning capacity of the network.
- You get the freedom to choose the number of hidden layers and number of neurons in each hidden layer (These things that are in your hand to change are sometimes called Hyper-parameters). But the Input Layer and Output Layer will be according to your Data.



### Neural Network as Universal Function Approximators

If you hold a mathematical background you might be familiar with this :

<p align="center">



$$\Huge{y = f(x_1,x_2,x_3)} $$

</p>

The Neural Network shown in the above picture is exactly this function $f$ . Our Neural Network takes three Input values through Input Layer and Produces a Single output $y$ .

But How do we define that $f$ ?

Recall that our A Neuron's output depend on 3 things (Weights,bias and Input). We cannot change the Input directly that is fixed. The only way to Change the Output is to Change the Weights and biases of the neuron. Great, but how do we choose values of Weights and biases that gives the expected results. Here comes the training part, We use an algorithm called back-propagation that fine tunes the values of all weights and biases of the network. These weights and baises are trainable parameter. We Initially set some random values to weights and biases and let the training fine tune it for us.


---
title: Understanding a Neuron in Neural Networks
categories: NeuralNets
mathjax: true
featured-img: sleek
---

Neural Networks are most widely used in deep learning today. You will hardly find a benchmarks that is not dominated by Neural Networks. Everything from Image recognition to Machine Translation. It is the same Neural Networks with some variations, that achieves or surpasses Human Level Performance. In this post I will explain the building block of Neural Network called **Neurons**

##  Neurons

Neurons are the most fundamental unit of  neural networks. Before I describe an Artificial Neuron. Let's have a look at biological Neuron or Nerve Cell.

From Wikipedia

> *A **neuron**  is an electrically excitable cell that receives, processes, and transmits information through electrical and chemical signals.*

This biological definition is pretty acceptable for Artificial Neurons as well. Artificial Neurons also recieves some values, processes and then transmits the results.

There is no standard way of visualizing a neuron in artificial neural networks. But You can assume a **neuron as a mathematical function that gets some input and produces some output**. So, stick to this Idea, It will get more clear as you progress in the post.



## Neuron's Components

As I mentioned above **a neuron is a mathematical function**. So what is the input to that neuron and what is the output and what mathematical relation converts input to output?

Here We will look at those deails. This Picture depicts how a neuron gets input(s) and produces output(s) and all of its components.

<p align="center"><img src="https://github.com/coder3101/coder3101.github.com/raw/master/in-post_imgs/understanding-ff-nn/NeuronExpl.jpg"/>

</p>

Here are some terms called *weights* which are `w1,w2,w3` , *inputs* `x1,x2,x3` and *biases* `b`.

**Weight(s)** are the *imaginary lines* that connect the neurons together. You can assume that those lines that connect neurons together are *pipes* through which input values `x` flows. When an input flows through that *pipe* the input is scaled by a number `w` . Such that in the end the result is `w * x`. This `w` is uniquely associated with each weight (pipe) and can be any real number.  Say x1 = 5 and w1 = 0.5, then the value that reaches the neuron is x1 * w1 = 2.5

**Inputs(s)** are the values we feed into the neuron or the outputs of the previous neurons. In the above example we assume that `x1, x2, x3` are the inputs we provide to the neuron. However we can also feed the output `z1` produced by the this neuron as input for next neuron as we do in Multi-layered Neural Networks. 

**Biase(s)** each neuron is associated with a unique bias term. The Value of this term `b` can be any real number. We can even skip this term in some cases. The work of this term will be clear when we study the actual calculation that out neuron does. So, Read with Patience and remember to share it with others.

There is one more thing called Activation Function that we can choose and this is function's output is  `z1` the final output of the neuron.

**Activation Function** are functions whose Domain is { ${-\infty, +\infty}$ } and are continious and differentiable everywhere (exceptions exists to differentiablity like Relu). In very simple words, the activation function must be defined for all values of input and the graph of which should not break or abruptly change directions. Most widely used activation function today is *Relu* expanded as Rectified Linear Unit.

Mathematically,

<p align="center">

​						$relu(x) = x^+ = max(0, x)$

</p>

The output of relu is very simple. For all the positive values the result is identity for negative values it is always zero. 

Here is the graph of Relu.

<p align="center">

<img src="https://github.com/coder3101/coder3101.github.com/raw/master/in-post_imgs/understanding-ff-nn/relu.jpeg"/>

</p>

*Note : Relu function is a non-linear function and is not differentiable at $x=0$, So, we assume derivative of relu at $x=0$ as zero*



##Neuron's Calculation

A Neuron represents a simple function that takes in value(s) from *pipes* and adds all the values including the *bias term* and then applies the **activation function** .

Here is how it looks mathematically,

<p align="center">

$w^1_{out} =  x_1 * w_1$

$w^2_{out} =  x_2 * w_2$

$w^3_{out} =  x_3 * w_3$

<p>

From our analogy of *weights* as *pipes* when `x1, x2, x3` flow through the weights `w1, w2, w3` the outputs that will reach to the neuron are denoted as $w^1_{out}, w^2_{out}, w^3_{out}$ respectively. The above mathematical calculations denote these operations. 

Inside the neuron following calculations take place.

<p align="center">

$a_1 = w^1_{out} + w^2_{out} + w^3_{out} + b$

$z_1 = relu (a_1)$

</p>




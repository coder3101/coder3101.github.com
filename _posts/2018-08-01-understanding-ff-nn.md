---
title: Understanding Feed Forward Neural Networks
categories: NeuralNets
mathjax: true
featured-img: sleek
---

Neural Networks are most widely used in deep learning today. You will hardly find a benchmarks that is not dominated by Neural Networks. Everything from Image recognition to Machine Translation. It is the same Neural Networks with some variations, that achieves or surpasses Human Level Performance. In this post I will explain the most Fundamental type of Neural Network called **Feed Forward Neural Network**. 

##  Neurons

Neurons are the most fundamental unit of  neural networks. Before I describe an Artificial Neuron. Let's have a look at biological Neuron or Nerve Cell.

From Wikipedia

> *A **neuron**  is an electrically excitable cell that receives, processes, and transmits information through electrical and chemical signals.*

This biological definition is pretty acceptable for Artificial Neurons as well. Artificial Neurons also recieves some values, processes and then transmits the results.

There is no standard way of visualizing a neuron in artificial neural networks. But You can assume a **neuron as a mathematical function that gets some input and produces some output**. So, stick to this Idea, It will get more clear as you progress in the post.



## Neuron's Calculation

As I mentioned above **a neuron is a mathematical function**. So what is the input to that neuron and what is the output and what mathematical relation converts input to output?.

Here We will look at those deails. This Picture depicts how a neuron gets input(s) and produces output(s).

![](https://github.com/coder3101/coder3101.github.com/raw/master/in-post_imgs/understanding-ff-nn/NeuronExpl.jpg "A Single Neuron")

Now here are some terms called *weights* which are `w1,w2,w3` , *inputs* `x1,x2,x3` and *biases* `b`. (Not visible in the picture)

**Weight(s)** are the *imaginary lines* that connect the neurons together. When we will look at the complete Neural Network in the end it will be more clear.For Now You can assume that those lines that connect neurons together are *pipes* through which input values`x` flows. When an input flows through that *pipe* the input is scaled by a number `w` . Such that in the end the result is `w * x`. This `w` is uniquely associated with each weight (pipe) and can be any real number.  (*Say x1 = 5 and w1 = 0.5, then the value that reaches the neuron is x1* * *w1 = 2.5*)

**Inputs(s)** are the values we feed into the neuron or the outputs of the previous neurons. In the above example we assume that `x1, x2, x3` are the inputs we provide to the neuron. However we can also feed the output `z1` produced by the this neuron as input for next neuron as we do in Multi-layered Neural Networks. 

**Biase(s)** each neuron is associated with a bias term. The work of this term will be clear when we study the actual calculation that out neuron does. So, Read with Patience and remember to share it with others.


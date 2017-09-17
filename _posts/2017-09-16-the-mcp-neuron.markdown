---
layout: post
title:  "The MCP Neuron"
date:   2017-09-16
categories: jekyll update
tags: ['featured', 'neural networks', 'ai', 'machine learning', 'deep learning']
image: /assets/article_images/2017-09-16-the-mcp-neuron/meddy-huduti-201619.JPG
use_math : true
---

Artificial intelligence is an incredibly exciting area of research and development which spans mathematics, statistics, computer science, engineering, philosophy, linguistics, information theory, biology, pyschology, neuroscience and others. It is also a fairly nascent area of science - what has been achieved so far is just the first steps in the journey to achieving *general artificial intelligence*. 


The success, however, of *deep learning* in image recognition, natural language and games, has inspired the world to take note of artificial intelligence. This success has fueled a wave of media hype and attention, that has perhaps misinterpreted what AI *is* for what it *isn't*. AI as we know it today is not capable of thought, has no consciousness and certainly does not have any sort of intelligence that can surpass our own. Rather, the "AI" that we experience in our mobile phones, the internet or read about in the news, is a collection of computational techniques known as deep learning (or machine learning, depending on the scope). 


So what is deep learning? For the best explanation of deep learning and it's limits, I recommend this excellent [two-part post](https://blog.keras.io/the-limitations-of-deep-learning.html) by Francois Chollet, the creator of Keras. In summary, deep learning is a sequence of geometric transformations (linear and non-linear), that when applied to data, *may* be able to model the relationships contained in that data. These geometric transformations are organised in a layered network, known as a *neural network*. This series is about these so called artificial neural networks, in which I will attempt to uncover what they are, how they work, where they come and why they are called "neural networks".

## The MCP Neuron
<br>

Before there were any artificial neural networks, or even the perceptron (more on both in upcoming posts!), there was the MCP Neuron. First proposed in 1943 by the neurophysiologist Walter S. McCulloch and the logician Walter Pitts, the McCulloch-Pitts (MCP) neuron is a simple mathematical model of a biological *neuron*. 

To understand how this model works, let's begin with a very simplified (and certainly non-expert) explanation of a biological neuron. These are electrically excitable, interconnected nerve cells in the brain which process and transmit information through electrical and chemical signals. These neurons are all connected with each other to form a neural network in the brain. The connections between neurons are known as *synapses*. Now a single neuron in this simplified explanation consists of three parts:


* The cell body or soma: this is the main part of the neuron which processes signals.
* Dendrites: these are branch-like shapes which receive signals from other neurons.
* Axon: this a single nerve which sends signals to other neurons.


The picture looks something like this: 


[picture here: biological neuron]


At its most basic, a single biological neuron may receive multiple signals from other neurons via its dendrites. These signals are then combined in the soma, and this combination *may* fire off another signal from the neuron to other neurons, which is propagated via the axon.


[picture here: a neuron sending and receiving signals]

***

The idea behind the MCP neuron is to abstract the biological neuron described above into a simple mathematical model. The neuron receives incoming signals as \\(1\\)'s and \\(0\\)'s, takes a weighted sum of these signals and outputs a \\(1\\) if the weighted sum is greater than some threshold value or a \\(0\\) otherwise. Formally this mathematical model can be specified as follows:



>* Let $[x_1, x_2, ... , x_m]$ be a vector of input signals where each \\(x_i\\) has a value of \\(1\\) or \\(0\\).
>* Let \\([w_1, w_2, ... , w_m]\\) be a vector of weights corresponding to the input signals where each \\(w_i\\) has a value of \\(1\\), \\(-1\\) or \\(0\\). 
    - Input signals with a weight of \\(1\\) are called *excitatory* since they contribute towards a positive output signal in the sum. 
    - Input signals with a weight of \\(-1\\) are called *inhibitory* since they contribute towards a null output signal in the sum. 
    - Input signals with a weight of \\(0\\) do not contribute at all to the neuron.
>* Then for some threshold value \\(t\\), an integer, the output signal is determined by the following activation function:
>
>$$
    y = \begin{cases}
        1, & \text{if} \ \sum_{i=1}^{m}w_{i}x_{i} \ \geq \ t, \\\
        0, & \text{otherwise}
    \end{cases}
$$


McCulloch's and Pitt's original experiment was to see if they could use this model to construct different [*logic gates*](http://www.ee.surrey.ac.uk/Projects/CAL/digital-logic/gatesfunc/) by simply specifying what the weights and threshold should be. In the next section, we'll see how MCP neurons can model certain logic gates in action using Python. 



*This is the first post in a series dedicated to the history of Artificial Neural Networks. Special thanks go to [Sebastian Raschka](https://sebastianraschka.com) and [Andrey Kurenkov](http://www.andreykurenkov.com/writing/a-brief-history-of-neural-nets-and-deep-learning/) for the inspiration, and to [Andrew Ng](https://www.coursera.org/specializations/deep-learning) for his passion and dedication to the field of Deep Learning. The style of this blogpost is intended to be conversational and informal. For a more formal treatment of the mathematics and code, checkout the Jupyter notebook version on Github [here](https://github.com/JontySinai/PythonAI/blob/master/Notebooks/Sec1-1_MCP_Neuron.ipynb).*


*Photo by Meddy Huduti on Unsplash.*



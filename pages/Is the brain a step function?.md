---
title: "Is the brain a step function?"
---

On whether the idea that "cranial nerves are step functions, so neural nets use sigmoids" is correct.

I think the fact that the brain works more like a step function means that cranial nerves are binary outputs that either pulse or do not pulse. This is a point that McCulloch and Pitts emphasized when they proposed [[formal neuron]] in 1943. [formal neuron - Wikipedia](https://ja.wikipedia.org/wiki/%E5%BD%A2%E5%BC%8F%E3%83%8B%E3%83%A5%E3%83%BC%E3%83%AD%E3%83%B3)

But 70 years have passed since then, and Dr. [[Kenji Doya]]'s [lecture notes](http://www.jnns.org/previous/niss/1999/lectnote/lecture_doya.pdf), written in 1999, organizes it as follows

- > There are two possible ways: (1) [[firing rate expression]] (rate coding) and (2) [[timing expression]] (temporal coding).
- > In primary sensory neurons and primary motor neurons, the firing frequency uniquely corresponds to a physical quantity such as light intensity or muscle tension. The inter-spike interval (ISI) is also nearly constant for a constant stimulus.
- > The idea of temporal coding (timing representation), which assumes that there is information in the timing of firing... Experimental facts, for example, show synchronous firing in the visual cortex.
    - firing rate expression
        - > Spike firing rates that are considered to be encoding information.
            - element representation
            - combinatorial expression
            - population representation
            - Spatial Pattern Representation
        - > There is also experimental and model support for the theory that the various representations described above take a "[[sparse]] representation" in which the rate of actually active cells in the population is kept low.
    - timing expression
        - > In the firing rate representation, we focus on the average value of the frequency of neural spikes over an appropriate range of time and space, and do not concern ourselves with the timing at which each spike is emitted on the order of milliseconds. However, there is a position that it is precisely such subtle timing that reflects a wealth of information.
            - time-delayed representation
            - synchronous idle
            - Ignition Pattern Expression
            - synaptic plasticity

So the idea that "cranial nerves are step functions" has not been updated in almost 20 years of knowledge.

Also, "use sigmoid" was published in 1986, but as of 2018 it is considered:.
> In 2011, Xavier Glorot et al. showed that using max(0, x) as the activation function of the hidden layer is an improvement over tanh or soft plus... In the world of neural networks it is called ReLU (English: Rectified Linear Unit, Rectifier, normalized linear function); a paper written by Yann LeCun and Jeffrey Hinton et al. in the journal Nature states that this is the best as of May 2015.
[Activation function - Wikipedia](https://ja.wikipedia.org/wiki/%E6%B4%BB%E6%80%A7%E5%8C%96%E9%96%A2%E6%95%B0)
[https://www.nature.com/articles/nature14539](https://www.nature.com/articles/nature14539)

Note that "as of May 2015, this is the best we can do" is an interpretation, and the fact is that the great success in convolutional neural networks in 2012 (ImageNet Classification with Deep Convolutional Neural Networks) was attributed to [[ReLU]].
>  This success came from the efficient use of GPUs, ReLUs, a new regularization technique called dropout, and techniques to generate more training examples by deforming the existing ones.

In other words, "cranial nerves are step functions, so neural nets use sigmoids" is incorrect in both the first half and the second half as of 2018.

---
This page is auto-translated from [/nishio/脳はステップ関数か](https://scrapbox.io/nishio/脳はステップ関数か) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
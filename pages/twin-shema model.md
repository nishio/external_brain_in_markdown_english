---
title: "twin-shema model"
---

- The bishema model is a modular learning model
    - Modular learning model in which new modules are created by subjectively discovering changes in the dynamics of the environment

- What is Shema?
    - Piaget
    - Self-organizing processes in cognitive development
    - Its basic module is the Shema
    - Assimilation and regulation
        - Assimilation: incorporating information from the outside world into the Shema
            - Which Shema to incorporate
        - Regulation: changing the shema to take in information from the outside world
        - The assimilation and regulation cycle is similar to both steps of the k-means method<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
    - Equilibration and differentiation
        - Above, processes of assimilation and regulation are in equilibrium
        - When data that is far from the Shema comes in, a new Shema is created, and this is differentiation.

- Dual-schema model
    - Assume a robot with sensors and motors
    - Sensor input is a finite-dimensional real-valued vector
    - Based on sensor inputs, the internal processing system makes decisions and produces action outputs.
    - The action output is a real-valued vector of several dimensions
    - at time t
        - Sensor input, perceptual vector: $S_t$
        - Action output, action vector: $A_t$
        - [[Semiotics of parsing]]
        - The concept of an object is "how we act upon it and what are the consequences of our actions".
            - The case ratio of [pragmatism
        - That is, $U_t = (A_t, S_t, S_{t+1})$ is the primitive form
            - We call this the experience vector.
        - Furthermore, consider F such that $F(S_t, S_{t+1}) = A_t$.
            - Instantaneous motor output is rarely meaningful for agents operating in real space (2006)
            - The policy function $a_t = \pi(s_t)$ is what should be called an "action" (2006), based on the idea that a series of actions acting on an object is an action.
            - The two expressions are connected when combined with a function expressing intent, as explained later.

    - Split the shema of Biaget into two parts.
        - why<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
        - Act Shema and Perceived Shema
        - Perceived Shema: $\hat{F}=(F,\alpha): A_t = F(S_t, I_{t+1}) + \alpha\delta_t$
        - Act Shema: $\hat{G}=(G, \beta): I_{t+1} = G(S_t) + \beta\delta_t$
        - where $I_{t+1}$ is the perception (Intention) that the subject wants to obtain at time t+1, ideally $S_{t+1} \simeq I_{t+1}$.
        - The combination of the two selects actions from inputs from the outside world.
            - The program of an action is a function that determines A from S $A_t = H(S_t)$.
            - :$A_t = F(S_t, G(S_t))$
        - Whether or not : $U_t$ satisfies the function F of the perceptual shema corresponds to whether or not the shema is appropriate as a symbol to represent an object existing in the external world. The process of assimilation can be performed here.
            - If the model error $(A_t - F(S_t, S_{t+1}))^2$ is small, the target belongs to the perceptual shema with F
            - Do you take the margin of error there?$(S_{t+1} - I_{t+1})^2$ではなくて？<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
    - Adds a limit to storage capacity
        - queue
        - We will store the U_t when we were in that shema state in this queue.
        - F optimizes the samples in its queue to approximate with minimum error
            - Regulation Process
        - Limited memory capacity contributes to plasticity
    - Summary: Assimilation and Adjustment
        - By selecting the shema with the smallest model error, we can identify the shema to which the target belongs (assimilation).
        - The object is recorded in the shema. The function of the shema is optimized to represent the object (adjustment).
    - differentiation
        - The model error at time t is calculated from the model error at time t....
        - confidence variable
        - If the adjustment of F is not sufficient, the denominator of R will also be larger in the same dimension
        - An increase in R can be recognized as some change outside the system

- Acquisition of action shema through reinforcement learning
    - Bishema-based reinforcement learning

Hierarchical modular learning machine

- Resources on sensory-motor learning are
    - [[context]] of the subject's interaction with the outside world,
    - [[corporeality]] of the subject.
    - [[resource constraint]] on memory

- Piaget's Shema is divided into two parts, the action Shema and the perception Shema -> twin Shema

- Bi-Schema is a cumulative modular learning device based on Piaget's theory of the Shema, in which an autonomous robot acquires Shema (concepts) corresponding to models of the environment/object through interaction with the environment (2005).


- The idea of symbolic grounding ignores the robot's own subjective world; instead of starting with human symbols, symbols for the robot must be generated through its own memory organizing mechanisms
- [[Umwelt]] = [[subjective world as seen by some creature]] = [[cyclic world]].
    - J. Uexkull Biological Semiotics


- Meanings of symbols do not exist objectively, but are formed through cognitive developmental processes and social communication


---
This page is auto-translated from [/nishio/双シェマモデル](https://scrapbox.io/nishio/双シェマモデル) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
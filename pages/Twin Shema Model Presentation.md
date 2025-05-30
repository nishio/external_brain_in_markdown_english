---
title: "Twin Shema Model Presentation"
---

## [[Reinforcement Learning]] Part 5
.
# twin-shema model
.
- 2017-07-14 @ [[Machine Learning Study Group]].
- Cybozu Labs NISHIO Hirokazu


What is the twin-shema model?
    - [[Tadahiro Taniguchi]] , [[Tetsuo Sawaragi]]. "[[twin-shema model]] ." Transactions of the Japanese Society for Artificial Intelligence 19.6 (2004): 493-501.
- Subtitle [[Proposal of a Self-Organizing Machine Learning Method for Autonomous Agents]].

- First, the developmental psychology side of the story.
- Then we talk about learning algorithms.


Who is Shema?
- The [[Shema Theory]] of [[Piaget]].
- French reading of [schema
- Translated as shema in the field of developmental psychology and [[schema]] in cognitive science and artificial intelligence research


Piaget's Shema Theory
- Through the process of [[shema equilibration]] and differentiation
- Shema's response to the outside world becomes more detailed.
- Shema is discrete and finite
- The process by which the Shema is created is
    - Representing an object with discrete symbols
    - Bottom-up language acquisition


Equilibration and differentiation
- I'll start with the equilibration and elaborate.
- Equilibration consists of two processes: assimilation and regulation.
    - Assimilation: incorporating information from the outside world into the Shema
        - A choice is made as to which shema to incorporate.
    - Regulation: changing the shema to take in information from the outside world


- Compare with [[k-method]].
- Data are classified into clusters with the closest representative points
    - = Assimilation: incorporating information from the outside world into the Shema
        - A choice is made as to which shema to incorporate.
- Cluster representative points are updated to the average of the data classified into clusters
    - = regulation: changing the shema to take in information from the outside world
- In this case [[cluster = shema]].


[[Differentiation of Shema]]
- The balancing process can "cluster a fixed number of clusters" as in the k-means method.
- But the number of clusters does not change.
- The process of differentiation creates new shemas.
- When data comes in that is far from the existing shema, a new shema is created, and this is differentiation.


What is Futatsuchema?
- Based on Piaget's Shema theory,
- Through the interaction of an autonomous robot with its environment
- Acquire a shema (concept) corresponding to a model of the environment/object
- Cumulative Module Learner (2005)

- Tadahiro Taniguchi, and Tetsuo Sawaragi. "[[Symbolic Emergence through Interaction between Body and Environment]]." Transactions of the Association for Systems, Control and Information Sciences 18.12 (2005): 440-449.
    - [[interaction with the environment]] / [[interaction between the body and the environment]] / [symbolic emergence (springing up from a seedbed, esp. as a result of an explosion of symbols)

robot
- Assume a robot with sensors and motors
    - Sensor input is a finite-dimensional real-valued vector
    - Based on sensor inputs, the internal processing system makes decisions and produces action outputs.
    - The action output is a real-valued vector of several dimensions


Value at time t
- Sensor input, perceptual vector: $S_t$
- Action output, action vector: $A_t$
- Experience vector $U_t = (A_t, S_t, S_{t+1})$


Futa Shema
- Split the Viaje shema into [[perceived shema]] and [act of shema
- Perceived Shema: $\hat{F}=(F,\alpha): A_t = F(S_t, I_{t+1}) + \alpha\delta_t$
- Act Shema: $\hat{G}=(G, \beta): I_{t+1} = G(S_t) + \beta\delta_t$
    - where $I_{t+1}$ is the perception that the subject wants to obtain at time t+1 ([[intention]] : Intention)
    - Ideally $S_{t+1} \simeq I_{t+1}$
    - : $\delta$ is a random number


Program of action
- The combination of the two selects actions from inputs from the outside world.
    - The program of an action is a function that determines A from S $A_t = H(S_t)$.
    - This can be written in terms of a combination of two shema's like this $A_t = F(S_t, G(S_t))$.


assimilation
- Whether the experience vector $U_t$ satisfies the function F of the perceptual shema
- This corresponds to whether the shema is appropriate as a symbol to represent an object existing in the external world.
- = Assimilation process
- If the model error $(A_t - F(S_t, S_{t+1}))^2$ is small, the target belongs to the perceptual shema with F
    - Do you take the margin of error there?$(S_{t+1} - I_{t+1})^2$ではなくて？<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
    - (2005), which was the L1 norm for it.
- If the error is too large, it is discarded without putting it in any shema, and if it continues, a new shema is created, but that's a differentiation process, so I won't explain it here.


control
- Each shema has a finite cue
- The experience vector $U_t$ is stored in this queue
    - When full, forget about the oldest first.
    - The authors argue that this [[finite memory capacity]] is important
- Update the internal function so that the empirical vector entering the shema can be approximated with the smallest error.
    - Incidentally, in (2004), linear approximation + steepest descent method


Equalization process = unsupervised learner
- The paper (2004) verifies that the equilibration process (assimilation + regulation) acts as an unsupervised learner in experiments with physical robots, but, well, I don't particularly disagree with that.
- Let's look at the differentiation process.


Differentiation Process
- If it's off, a new Shema is created.
- Need a definition of "misalignment"
- Error $E_{U_t} = ||A_t - F(S_t, S_{t+1})||$
- Error Mean $E_{F,G} = \frac{1}{\# \mathcal{U}_{F, G}}} \sum_{U_t \in \mathcal{U}_{F, G}} E_{U_t}$
- [[Subjective error]] $R_{F, t} = E_{U_t} / E_{F, G(t)}$
    - In addition, F is the perceived shema


slippage
- When a new experience $U_t$ is out of the perceived shema $F_n$, there are three causes
    - 1: Insufficient learning about the current environment
        - In other words, lack of equilibration.
    - 2: Noise has temporarily entered
    - 3: The environment at the time of equilibration and another environment

Dealing with misalignment
- 1: Insufficient learning about the current environment
    - 1: The denominator of the subjective error is also larger, so the subjective error is not larger
- 2: Noise has temporarily entered
    - We should not create a new Shema.
    - We need to observe for a while.
- 3: The environment at the time of equilibration and another environment
    - Creating a New Shema


Create a new shema?
- [[Perceived Shema Activity]](2005)
- $V_n(t+1) = pV_n(t) + (1-p)\exp(-\frac{1}{2}R_n(t)^2)$
- (1) If the activity of all perceptual shema does not exceed a predefined threshold $V_{turn}$, it means that there is no suitable shema, so we create a new one
- (2) Otherwise Select the oldest one whose perceived shema is above the threshold
    - Not the most active or the one with the smallest margin of error?<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
    - It says "select the module with the smallest error, never" or something like that, so I guess it's intentional...
    - Q: What is "old"? A: The earliest Shema
- The definition of shema activity in (2004) is slightly different, but the description says "$\Phi$ is a monotonically increasing function satisfying the conditions $\Phi(0) > 0$ and $\Phi(\infty) < 0$", which is not clear to me, so I passed.


Experimented differentiation flow
- Show the robot a stationary ball.
- The equilibration will allow you to gaze at a stationary ball.
- Move the ball left and right
- Shema's activity level goes down.
- A new Shema is created.
- Equilibration is performed for spheres moving left and right.


The authors claim ([[the problem of categorization from distance information]])
- It is important to note that the categorization is not based on distance information in the sensor input space."
- In the clustering method by giving distances (or assuming Euclidean distance, etc. unconsciously), we end up with a form of external giving what to focus on.
- I feel that it is important that the robot itself has made the division of the concept from its own experience.


Relationship to Reinforcement Learning
- In both (2004) and (2005), the act shema is given by humans.
    - The act of trying to catch the ball in the middle of the field of vision is giving the Shema.
- (2006) attempts to acquire in reinforcement learning
    - Reinforcement learning rewards what is good.
        - The control of the ball on the board, the closer to the middle, the higher the reward.
    - I don't think there is much difference...

- (2006)  [[Adaptive acquisition of generalized action concepts]]
    - Tadahiro Taniguchi, and Tetsuo Sawaragi. "Adaptive Acquisition of Generalized Action Concepts." Transactions of the Society of Instrument and Control Engineers 42.3 (2006): 255-264.


- [[Relationship between the amount of shema created and physical performance.]]
- Not much shema is created by high or low physical ability.
- The most is made when it is medium (2005).
![image](https://gyazo.com/7d28dd595d1a76509ec651bc618f7cf6/thumb/1000)


Relationship between the amount of shema created and physical performance.
- Robot with wide field of view OR high time resolution
    - I see where the ball is.
    - Just keep your eyes where the ball is.
    - No need to symbolize ball movement patterns
- Medium Robot
    - You see the ball, but you lose it easily (probably).
    - If you understand the ball's movement pattern, you can say, "It's in circular motion mode now, so it should be around here next time."
    - Creating symbols improves performance.
- Low performance robot
    - I keep losing sight of the ball and can't find a meaningful movement pattern.


The Language of Mankind and the Language of Machines
- There is a huge physical difference between humans and machines.
- The difference is going to cause a difference in the language that is created.
- Although humans think in Boolean as "being an apple" or "not being an apple",
- A machine can be thought of as a real vector with a probability of 0.8 that it is an apple and 0.2 that it is a pear.
- [[Humans are weak at vector arithmetic]], they cannot communicate vectors in words. Machines are the opposite.
    - [[A physically capable robot does not need to create a language.]]


From the Machine's Perspective
- A complex system of symbols created by less capable creatures in an attempt to somehow increase their abilities.
- Do we need to understand and do this...(do we need natural language processing?)
- Why don't you just concentrate on what you do best, create value, and communicate it to them in your own words?
- If the value is clear, they will be invested in understanding your language


Apply to groupware domains
- The original research was on robots
- What is "[[corporeality]]" as applied to groupware?
- Not necessarily manipulate and influence the outside world.
    - In this experiment, they're just moving the camera.
- I am affecting my sensor inputs by my outputs.


- [[ability to judge whether a particular action is appropriate or not]]
![image](https://gyazo.com/4d50d5f630dd97a02f0d2b343670a551/thumb/1000)
- Even infants can gaze at either one of several inputs
- It is believed that we gaze at the more favored


ability to judge whether a particular action is appropriate or not
- Get less detailed information from multiple sources and choose which information to enter in more detail
    - The usual sense of natural language processing would say, "Why not just put it all in without selection?" but the assumption that it can handle all the data is equivalent to a "robot with very high physical capabilities," so it would not be able to generate symbols.
- For example, get the title of the link from the page you are currently eyeing on Wikipedia, and from there choose "which page to look at next".
    - Does "Français" make you avoid links?
- For example, choose which of the groupware postings to look at in detail based on the number of characters or the frequency of occurrence of each type of character.
    - Avoid things like pasted log output?


- [[act of shema]]
- It is up to the act shema to avoid or prefer.
- (2004) gives the action shema of "catching the ball in the center of the field of view"
- (2006) also defined [[reward]] and gave it to a human in order to acquire the action shema in reinforcement learning.
- Or, instead of being predefined by a human, we can use a neural net with random connections to produce a 1D real value and call it a reward.
    - = [[natural preference]].
- Raise 100 or so random types, kill the ones that behave badly for humans, and breed the remaining ones.
    - Darwinian [[optimization by natural selection]].


summary
- Learned about the "bishema model" in which robots acquire concepts through interaction with their environment.
- It seems possible to give physicality to software that does not have a physical body
- It would be interesting to observe the emergence of language
    - There is still a gap between what is practical for humans
- Physical ability does not create language.
    - Even if a machine, whose physical capabilities differ greatly from humans, were to produce a language system, it would probably be very different from the human language system (so much so that the difference between Japanese and English would seem small).
    - Human understanding of that language would be even more difficult than translating between Japanese and English!


References
- (2004) Twin-shema model
    - Tadahiro Taniguchi, and Tetsuo Sawaragi. "The Bishema Model." Transactions of the Japanese Society for Artificial Intelligence 19.6 (2004): 493-501.
    - Subtitle Proposal of a Self-Organizing Machine Learning Method for Autonomous Agents
- (2005) Symbol Emergence through the Interaction of Body and Environment
    - Tadahiro Taniguchi, and Tetsuo Sawaragi. "Symbol Emergence through Interaction between Body and Environment." Transactions of the Institute of Systems, Control and Information Engineers 18.12 (2005): 440-449.
- (2006) Adaptive acquisition of the generalized action concept.
    - Tadahiro Taniguchi, and Tetsuo Sawaragi. "Adaptive Acquisition of Generalized Action Concepts." Transactions of the Society of Instrument and Control Engineers 42.3 (2006): 255-264.

---
This page is auto-translated from [/nishio/双シェマモデル プレゼン](https://scrapbox.io/nishio/双シェマモデル プレゼン) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "Think of society as a human computation"
---

Think of society as a human computation
- Voting, a component of democracy, is a calculation, as is the market, a component of capitalism.
- Let's look at "society" as "human computation" and see how we can improve it from the perspective of computer science.

Emergence of computers that are better at computation than humans
- As the name "computer" (= something that does calculations) implies, computers are good at calculations.
- During World War II (1939~1945), the American ENIAC (in operation in 1945) was developed to calculate artillery shell trajectories for the US Army.
- This task used to be calculated by hand by human women called "computers".
    - ![image](https://gyazo.com/dec28da7392b23f633866150e13b4adb/thumb/1000)
        - Computer room in 1949
        - [Computer (occupation) - Wikipedia](https://en.wikipedia.org/wiki/Computer_(occupation))
    - Computational strength led to military power.
- Peaceful use of computing power
    - The ENIAC case is well known, but there is an interesting case a little earlier
    - The 1880 U.S. Census took about eight years to compile.
    - To solve this problem, engineer Herman Hollerith invented the Tabulating Machine, a punch card-based automatic tabulating machine.
        - [Tabulating machine - Wikipedia](https://en.wikipedia.org/wiki/Tabulating_machine)
    - With the use of Hollerith's tabulating machine, the 1890 survey was completed in less than a year. This was a technological innovation of its time that had a major impact.
        - Hollerith founded the Tabulating Machine Company in 1896.
        - This would later lead to IBM (International Business Machines, 1924)
    - In the early days, IBM grew by providing punch card equipment for government, insurance, railroads, and other industries that required high-volume aggregate processing.
    - The innovation of the punch card has increased IO bandwidth.
        - Until then, the census was conducted by human eyes reading "responses on paper" and tabulating them by hand. Inefficient.
        - With punch cards, the information was encoded directly as a physical hole that could be read by the machine.
            - The edge of formalizing and externalizing the implicit aggregation, categorization, and decision-making processes that society used to perform in the human brain.
    - This is to gather a lot of information from society and calculate
        - Although not as sophisticated as ballistic calculations, the Hollerith tabulator was also a mechanization of calculation in the sense that it accurately and rapidly replaced "the simple and enormous tabulation work that was done by humans.
        - Work that would have taken 8 years by human labor is now completed within a year, more than 8 times more efficient
- Elections are also "a process of putting information on paper and tallying it up."
    - In Japan, people still write letters on paper with a pencil, but in the U.S. punch cards were widely used from the 1960s until the 2000 presidential election, and now most states have switched to optical scanning
    - Audrey Tang says "[[Elections are slow communications, sending 5 bits every four years.]]" and "[Digital natives don't think that once-every-four-years upload bandwidth is enough.
        - As a recent specific example, in the national proportional for the 2025 House of Councillors election, 172 people ran and voters wrote in one name, which is 7~8 bits in 3 years.
    - I'd really prefer to be able to post in writing about my problems and what I'd like to see resolved, etc., and I'd prefer to be able to express my opinions on specific agendas.
        - Young people are less psychologically challenged to express their opinions in text format since the spread of SNS (compared to the days when the only way to do so was by writing letters to newspapers).
    - This "narrow election bandwidth" problem had no technology to solve it until recently
        - Large volume of text format opinions received could not be processed
        - However, technological innovations underway as of 2025 are changing the picture: the development of LLMs (Large Language Models).
        - This innovation can be thought of as a paradigm shift in "the way we calculate.

A paradigm shift in "how we do math."
- How to design a "calculation
- Early programming was a design concept of combining components with true/false as input/output
    - This design concept was widely used because it was easy to make it worthwhile even with early, poor computers
    - Evaluate conditional expressions in if statements and switch processing content depending on whether they are true or false.
    - This conditional expression is created by assembling smaller conditional expressions with and and or
        - Reference: [[From if statements to machine learning]].
    - A paradigm that combines "parts with true/false as input/output" (logical blocks, rules)
        - Rule-based design philosophy
    - True/False, Yes/No, Good/Bad and binary expression
        - When a problem is discovered that cannot be divided well, a conditional branch is added.
        - As we improve it while operating it [[it becomes more and more complex conditional branches]].
- Methods other than rule-based methods existed in detail.
    - 1943 McCulloch-Pitts Artificial Neuron
        - ![image](https://gyazo.com/3730d37393dbba26d99c86e0771bb793/thumb/1000)
            - [Artificial neuron - Wikipedia](https://en.wikipedia.org/wiki/Artificial_neuron)
        - Weight and add together the inputs
        - Design philosophy based on weighted sums
            - Logistic regression, used in the 1940s and 1960s in medicine and the social sciences, is a similar concept.
                - <img src='https://scrapbox.io/api/pages/nishio-en/o3/icon' alt='o3.icon' height="19.5"/>D. R. Cox formulated maximum likelihood estimation and hypothesis testing in a 1958 paper, completing the framework as a general-purpose binary regression model
                    - [https://www.scirp.org/reference/referencespapers?referenceid=1680101](https://www.scirp.org/reference/referencespapers?referenceid=1680101)
            - Convergence leads to Perceptron (1958, Rosenblatt)
- Difference in ability to express oneself
    - If you want to execute when both condition x1 and condition x2 are true, you can do this
pseudo code

```
if(x1 and x2){ ... }
```

    - In the case of weighted sums, assuming x1 and x2 take the values 0~1
pseudo code

```
if(x1 + x2 >= 1.5){ ... }
```

    - This is equivalent to AND.

    - rule-based paradigm
        - Space can only be divided in a plane perpendicular to the axis.
    - weighted Japanese paradigm
        - Space can be divided on any surface.
    - ![image](https://gyazo.com/130be77d52b07b7ca56038aa0892031d/thumb/1000)


    - What if we want to run when two of the three conditions x1, x2, x3 are true?
pseudo code

```
(x1 and x2) or (x2 and x3) or (x3 and x1)
```

    - For weighted sums
pseudo code

```
x1 + x2 + x3 >= 1.5
```

    - (Exercise: Create a conditional expression in both paradigms that is true when 3 of the 5 conditions x1 ~ x5 are true)
    - Thus, depending on the content of the conditional branch to be described, the weighted sum paradigm is easier to describe than the rule-based paradigm
    - The examples listed here have not yet utilized weights.
        - By adjusting the weights, you can reflect the level of importance in your judgment, such as "whether x1 is true is important, whether x3 is true is not so important".
        - This is a machine learning method called "supervised learning," in which the weights are not adjusted by humans, but by using "teacher data," which is the result that is expected under these conditions.

Familial similarity and weighted sums
- Whether an element is a member of a certain group may not be determined by common characteristics.
- Ludwig Wittgenstein, in his "Philosophical Investigations," pointed out that concepts such as "language," "games," and "numbers" do not have features that are common to all their objects, but are only loosely connected as a whole by partially common features, which he named family resemblance (Family He named it "family resemblance.
- In fact, this weighted sum decision method is suitable for decisions based on familial similarity. This is because whether or not a person is an element of a set is not determined by a small number of attributes, but by the degree of commonality of a large number of attributes.
- In fact, it seems that there are cultural differences in this judgment style.
    - Norenzayan, A., Smith, E. E., Kim, B. J., & Nisbett, R. E. (2002). Cultural preferences for formal versus intuitive reasoning. Cognitive science, 26(5), 653-684.
- ![image](https://gyazo.com/06c3b8cf1bbbf5bdd1323efe70f86ed8/thumb/1000)
    - Is the target right flower Group 1 or Group 2?
- Do you think the flowers on the right of the target should be in Group 1 or Group 2? Orientals tend to choose Group 1 and Westerners tend to choose Group 2.
    - ![image](https://gyazo.com/307a8349e3031d6a1584edc2a8c61498/thumb/1000)
- Let's delve into the two ways of thinking.
- This flower has four attributes.
    - Attribute 1: Target petals are round, Group 1 has 3/4 petals round, Group 2 has 1/4 petals round
    - Attribute 2: Target flower center is a single circle, 3/4 of Group 1 is a single circle, 1/4 of Group 2 is a single circle
    - Attribute 3: Target has leaves on it, Group 1 has leaves on 3/4, Group 2 has leaves on 1/4
    - Attribute 4: Target stems are straight, Group 1 has 0/4 stems straight, Group 2 has 4/4 stems straight
- In this situation, would you put the target in group 1 or group 2?
    - Oriental type: the idea that since three of the four attributes indicate that "Group 1 is closer", it should be placed in Group 1.
    - Western: Attributes 1-3 do not clearly separate the groups. The idea is that Attribute 4 is the criterion that separates these two groups, and if you follow that criterion, you should be placed in Group 2.
- Western types can easily explain to others the reasons for their decisions. It can be made into a clear proposition: "If the stem is straight, it is group 2." On the other hand, it is vulnerable to noise. In this example, attribute 4 could cleanly separate the two groups, but if noise is introduced and even attribute 4 could not separate the two groups, the Western type will fall into the trap of thinking, "There is no clear criterion to distinguish between the two groups. It is also weak when some of the attributes are unobservable.
- The oriental type is resistant to noise and to unobservables. However, the reason for the decision cannot be simply explained. If we dare to explain, the rule would be: "If the petals are round, one vote for group 1; if the center of the flower is a single circle, one vote for group 1; if it has leaves, one vote for group 1; if the stem is straight, two votes for group 2. The rule is: "The group with the highest total number of votes shall be the group with the highest number of votes.
- Each set can be viewed as [[supervised learning]] since it is labeled and given a priori. We show that oriental-type thinking can be emulated by logistic regression, one of the methods of weighted sums.
- Represent petal, inflorescence, leaf, and stem features as (1, 1, 1, 1) targets
- Group 1
    - (1, 1, 1, 0)
    - (1, 0, 1, 0)
    - (1, 1, 0, 0)
    - (0, 1, 1, 0)
- Group 2
    - (0, 0, 1, 1)
    - (0, 0, 0, 1)
    - (0, 1, 0, 1)
    - (1, 0, 0, 1)
- Let us call the axes (a, b, c, d), respectively
- Western identification discards information other than the d-axis to identify
- Oriental-type identification uses all axes.
    - [[logistic regression]] would determine "group 1 with probability 55%".
python

```
import numpy as np
from sklearn.linear_model import LogisticRegression

X = np.array([

 (1, 1, 1, 0),
 (1, 0, 1, 0),
 (1, 1, 0, 0),
 (0, 1, 1, 0),

 (0, 0, 1, 1),
 (0, 0, 0, 1),
 (0, 1, 0, 1),
 (1, 0, 0, 1)])

Y = np.array([0, 0, 0, 0, 1, 1,	1, 1])

m = LogisticRegression()
m.fit(X, Y)
```


:

```
In []: m.coef_
Out[]: array([[-0.47815958, -0.47815958, -0.47815958,  1.16980067]])

In []: m.predict_proba([(1, 1, 1, 1)])
Out[]: array([[0.54564474, 0.45435526]])
```

- The probability that predict_proba is in each group. `[0.54564474, 0.45435526]` indicates a decision of "group 1 with probability 55% and group 2 with probability 45%".
- coef_ is the weight of each attribute. a, b, and c axes are -0.48, i.e., weakly implying group 1, while d axis is +1.17, i.e., strongly implying group 2.
- Logistic regression adds them together, so the decision on the axes a, b, and c wins and makes the decision that the group is group 1 by a narrow margin.

- On the other hand, [[decision tree]] would judge 100% as group 2.
python

```
from sklearn.tree import DecisionTreeClassifier
m = DecisionTreeClassifier()
m.fit(X, Y)
```


:

```
In [7]: m.predict_proba([(1, 1, 1, 1)])
Out[7]: array([[0., 1.]])
```

- This time predict_proba was `[0., 1.]`. This indicates a "100% group 2" decision.
- In the learning process, the decision tree looks for "which of the axes can be divided most neatly" and naturally draws the conclusion that "d is the best way to make a decision. As a result, it does not look at any axis other than d during the identification phase.
- ref
        - [[familial resemblance]]
        - [[Orientalists are logistic regression and Westerners are decision trees.]]

- [[Epoch when the rule-based paradigm lost to the weighted sum paradigm]]
- In 2012, the rule-based paradigm loses to the weighted sum paradigm.
- In the ILSVRC-2012 (ImageNet Large Scale Visual Recognition Challenge), a contest for image recognition accuracy, AlexNet, created by deep learning in the weighted sum paradigm, won by a wide margin over a rule-based implementation devised and designed by humans. AlexNet won the competition.
- The contest challenged participants to correctly classify 50 images in each category for testing, using 1,300 images in 1,000 categories each. While the previous year's winner had failed to classify 26.2% of the images, AlexNet improved by more than 10 points all at once to win at 15.3%.
- It has been demonstrated that a mechanism to adjust weights performs better than a human working hard to design features and describe them as rules.
    - Research in this direction has since accelerated, and in 2015, ResNet-152 reached a failure rate of 3.57% with a consensus of six models with different parameters. Since the failure rate for humans is 5.1%, the performance of ResNet-152 exceeded that of humans in this contest.




statistical language model
- This paradigm shift spread to other areas.
- For example, machine translation
    - Humans had a unit called "word" and an attribute called "part of speech" in a "sentence" and tried to combine them with the rules of "grammar" to understand sentences
    - This process of chopping sentences into words and identifying parts of speech is called "morphological analysis," which many readers may have heard of.
- In 2018, a study was published showing that statistically separating sentences into words in morphological analysis improves machine translation performance rather than separating sentences into words. One of the authors is Taku Kudo, a well-known developer of the morphological analyzer MeCab. Unlike conventional Japanese morphological analyzers, the proposed "SentencePiece" does not have a Japanese-specific dictionary or grammatical rules.
- In the past, humans created the concept of "word," and then created a system based on the idea that "words must be divided into word units. In fact, however, the "word-by-word segmentation" was a restriction created based on an assumption, and the performance of machine translation was improved by removing this restriction.


Large-scale language model (LLM)
- As of 2025, computers now have the ability to understand language at the college level
    - This is due in large part to the language-independent tokenizer mentioned earlier. The language-independent tokenizer enables the centralized handling of data on the Internet that is written in a variety of languages, and sometimes in a mixture of languages.
    - ChatGPT was released in November 2022, and the GPT-3.5 used inside it is said to have the language understanding capability of a college student. As of July 2025, a model with performance equivalent to GPT-3.5 can be run on a laptop computer without an expensive GPU.
- This greatly lowers the language barrier.
    - Let's divide them into "language barriers between people and computers" and "language barriers between people and people."
- Language barriers between people and computers
    - Until now, computers lacked the ability to understand human language, so humans learned a "programming language" and used it to give instructions to computers. That is "programming.
    - Programming languages have strictly defined grammars, so the meaning is determined on a rule basis. This is the reason why they could be used even by computers with limited language comprehension ability.
    - As computers become more capable of understanding language, it becomes more cost-effective to give instructions to computers in natural language. Andrej Karpathy (one of the founding members of OpenAI), who coined the term "[[vibe coding]]," says he doesn't even touch the keyboard because voice input is sufficient.
    - Many may not yet consider it a decent programming method because of its high failure rate, but within a few years it will perform well enough for most use cases.
    - ![image](https://gyazo.com/78a6a9aa82f0d0f623829f63637a7c73/thumb/1000)
            - [[Part of it disappears, part of it remains, and a new one is born.]] X shifts to X'. a: what disappears b: what remains c: what is newly born
    - What is now considered the work of software engineers will surely disappear in part. Some will remain, and new areas will be created.
- Language barriers between people
    - The author believes that there will be fluctuations in society as a whole that are incomparable to the fluctuations in the field of software engineering.
    - This is because the number of cases in which "something that acts as if it were a person" is not a person increases to a non-negligible percentage.
    - Services that allow AI to directly control the browser are emerging, such as Cognition AI's Devin and ChatGPT's Operator mode, which is still only available in the U.S. As of 2025, AI can obtain its own email address, get past the [[CAPTCHA]] to repel robots, and create accounts for various services, It can create accounts for various services. Any service open to the Internet can be used by [[non-human users]].
    - Many of you have probably seen accounts on X (Twitter) that hang on to posts that have attracted attention. You can tell when you see one that is poorly done, but there will be some that successfully pretend to be human. Soon the time will come when it will be impossible to tell whether the person on the other end of the phone is a human or a machine.
    - AI allows one person to pretend to be 10,000 people. Human thought patterns that lead people to believe what many people are saying can be easily controlled by the entities operating such systems. This risk is often discussed in terms of [[cognitive warfare]] and [[public opinion polls]].
    - It's not all bad. For example, advances in machine translation have made it easier to cooperate with people who speak different languages. Difficult texts can be explained and furigana added for elementary school students. What used to be done through language becomes generally less expensive.
- Advances in LLM will bring about major cost structure changes in "communication", a major component of "society".
    - Something similar has happened many times in history in the form of letterpress (≈books), radio, and the invention of the Internet
    - Society is greatly affected each time and cannot return to its previous form.
        - The advent of books made it possible to understand the Bible in one's native language. This broke the clerical monopoly of knowledge held by the Latin language and led to the Reformation and the development of science.
        - The advent of radio made it possible for a sender to communicate information to a country's population in a highly real-time manner. 1933 saw the spread of inexpensive radio under Hitler's regime, and the simultaneous listening of many citizens to broadcasts from the Ministry of Propaganda influenced the formation of consciousness in society as a whole.
        - It is impossible to explain in a few words what the advent of the Internet has changed.
        - How will the advent of LLM change society in the future?

LLMs don't just change communication.
- So far, we have seen a number of cases where the "computation" that humans have worked hard to define, construct, and design rules for has been defeated by the "computation" learned by the neural net.
- Could the same be said of the rules called "laws" that humans have created to describe social systems?
    - The phrase "[[Law is the operating system of society]]," but doesn't continuing to use an old operating system prevent the system from adapting to the new environment, or make society vulnerable to security problems that are discovered and not addressed?
- A "society" described by law may lose in performance to a "society" weighted by neural nets.
- In what form would this "performance difference" manifest itself? Will it be a difference in economic growth rates? Or will it be, as in the case of ENIAC, "the difference between computational power and military power"? A few days before writing this article, I saw a news report that 30,000 attack drones equipped with image processing AI and capable of automatically tracking targets were exported to the ongoing war between Russia and Ukraine. The day before that, a drone had invaded a nuclear power plant in Japan, causing a commotion. I believe that the social changes that are currently taking place are not far-fetched.
    - Footnote: [Kyushu Electric Genkai Nuclear Power Plant, drone intrusion?


Ideology in the 21st Century
- Today, in 2025, there are three ideologies of "what kind of society is better" as technology transforms society
    - (This is discussed in the book "Plurality" written by Audrey Tang and Glen Weyl in 2024.)
- Simply put, efficiency, freedom, and cooperation.

Focus on efficiency
- Let's leave everything to AI, humans are inefficient."
- Some people believe that the ideal situation is one in which AI does all the work and humans can live without having to do anything.
    - Maybe in the distant future there will be a future where humans don't have to do anything.
    - But in the near future, the division of labor will be such that "AI will do what is more efficient to do, and humans will do the rest.
    - The problem here is that if the AI is better at decision making, the AI will make the decisions and the human will have to work as an unwilling tool!
    - For example, in the shipping process in a huge warehouse like Amazon's, the AI knows what is on what shelves and decides which route to take, and the human takes it off the shelves and puts it in the box as instructed.
- Efficiency and freedom are often trade-offs
    - When AI can direct optimal behavior, human free will is a detrimental efficiency loss
    - There will be financial penalties for inefficiency, etc., to train people not to try to make free decisions.
- Many of our readers may have received their school education in Japan, where peer pressure is strong. In order for a small number of teachers to manage a large number of students, many of them may have been taught to act collectively by watching their surroundings and reading the atmosphere, rather than moving freely and arbitrarily. In an efficiency-oriented society, this atmosphere will prevail.

Emphasis on freedom
- Strongly opposed to the efficiency-oriented approach is the freedom-oriented approach.
- The idea is that it is more important for each individual to be free to do what he or she wants to do than to be efficient as a whole.
- We believe that laws and regulations should be relaxed and privacy should be strengthened to prevent the government from observing individual behavior.
- destruction of public property
    - The trouble is, there are many types of things in society that break down when everyone gives them free rein!
        - It's a case of personal freedom having a negative impact on others.
    - Classic analogy [[Tragedy of Common Land]].
        - The metaphor that if everyone fed the cows freely in a shared pasture, the pasture would die.
        - Should the free release of gases that degrade the global environment be promoted?
        - On a more individual level, is it a freedom that should be promoted to "mix and discard properly because it is a hassle" in an area where the rule is to separate garbage and throw it away? Is it acceptable for people who do not know how to dispose of mobile batteries to mix them with regular trash? Restoration is estimated to cost billions of yen. Since the cost of public facilities is ultimately covered by your taxes, a few tens of yen of your taxes will be used for the restoration.
        - [[How to deal with the tragedy of shared lands in OSS]]
        - In 2022, the developer of the open source library "colors.js" refused to "work for free" because of economic hardship and intentionally tampered with the library
        - OSS "free to use" leads to financial ruin for maintainers as "no one pays for its upkeep"
        - How can we better fund this type of public good?
- Freedom widens the gap.
    - Freedom widens the gap between those who can take advantage of that freedom and those who cannot
    - For example, Japan's Foreign Exchange Law was amended in 1998 to allow, in principle, free investment in foreign stocks and other securities. This is in contrast to China, where foreign currency purchases and remittances are limited to US$50,000 per year.
    - Thanks to this freedom, Japanese people have the freedom to buy tens of millions of yen worth of U.S. stocks. However, this "everyone has the freedom to do it" does not mean "everyone can do it. Many people may not have the political and financial means to buy tens of millions of yen in U.S. stocks.
    - Those who have bought U.S. stocks in the past decade have, on average, earned 10~20% annual gains, increasing their assets by about 3~6 times in 10 years. On the other hand, nominal wages for the average Japanese worker have only grown by about 4% over the past decade, and have rather decreased when prices are taken into account. And for those who can move their assets to growing foreign countries, there is no real personal harm if Japan does not grow and workers' wages do not increase.
- Only those who were able to learn about the beneficial alternatives from the large number of choices and could afford to take those alternatives could reap the benefits of freedom.
    - Meanwhile, in China, where foreign currency restrictions were strict, bitcoin became an attractive investment as a way to circumvent regulations. The use of bitcoin as a means of anonymously transferring funds out of the country began to spread rapidly around 2013, and the authorities decided to close exchanges in 2017 and ban bitcoin altogether in 2021.
    - So advances in cryptography provide enhanced privacy, which is a means of increasing freedom for those who want to act without being monitored by the government. And the extent to which governments allow freedom varies from country to country. Japan is tolerant of individuals investing in foreign stocks, but it is not entirely free. For example, "cases where people want to act without being monitored by the government" include funding for terrorism and money laundering of criminal proceeds. The Japanese government is considering thoroughly "ascertaining the identity of the sender and receiver" in order to prevent these activities, but there are various technical challenges in the situation due to the combination of cryptocurrencies' high degree of anonymity.
- This tradeoff between efficiency and freedom is also related to the classic [[Big Government and Small Government]] debate.
    - Centralized mechanisms tend to increase the efficiency of public goods supply, but uniform regulation tends to undermine freedom.
    - Leaving it to the market will increase autonomy and freedom of choice, but it will also reduce efficiency due to free-riding and external diseconomies, and will lead to widening inequality.
    - Balance is important, not one extreme or the other; which balance is appropriate?


Emphasis on cooperation
- The "trade-off between efficiency and freedom," the "big government/small government dichotomy," and "how to balance the two" are false assumptions
    - [[Big government/small government" is a false dichotomy.]]
    - The claim that there is a third pole
    - Elinor Ostrom, 2009 Nobel Prize in Economics
    - from  [[ostrom]]
        - > Ostrom studied [[public goods (i.e. goods or services such as parks or highways)]] and [[shared resources]] ([[CPR]], [[Common-pool resource]]). He challenged the earlier assertion that either the government or the market would deal with the management of public goods and CPRs, and showed that the efficiency of managing resources is most effective when neither the market nor the government, but the community, plays a complementary role.
        - (The use of the word "efficiency" here is confusing.)
- The third axis of 21st century ideology is "Let's use technology to help people cooperate".
    - Audrey Tang: [[Connections between indivisuals as first-class objects]]
- Model society as an [[intersecting group]] rather than as a single system or as a collection of disparate individuals
    - ![image](https://gyazo.com/6372900530b7163c3ae1bcacc73be72f/thumb/1000)
        - from [[intersecting group]]
    - Overall Optimization -> Thinking to optimize the whole as a single instance
    - Maximizing individual freedom -> thinking to optimize the individual as a single instance
    - Individuals belong to a number of small groups.
        - Family, community, company, region, ...
        - We will make sure that better teamwork occurs within this small group.
- This small group is generated and extinguished.
    - ![image](https://gyazo.com/996f462ac6623efec6a8a467e9dd76ee/thumb/1000)
        - For example, people belonging to different groups come together temporarily to work together on a project.
        - At this time, groups that straddle "group boundaries" are being created.
        - We consider it a good thing that this "bridging group" is being created more and more.
- From the union of different things, something new is born.
    - Why is it good if a "bridging group" is created? Because better results are achieved when people belonging to different groups bring their wisdom together.
    - And [[one cannot estimate the value of a new thing before its appearance]].
        - So we're going to create a lot of opportunities, some of which will lead to big results that can't be predicted in advance.
    - Streamlining communication lowers "bring it on" costs.
        - Lower language barriers are also relevant here.
            - Not only Japanese-English translation, but also within the Japanese language, there are "seemingly identical Japanese speakers who cannot communicate with each other," and we will smooth out these language barriers that are difficult to see and have not been invested in resolving until now.


As of 2025, how are society's calculations being updated?
- The "Plurality" by Audrey et al. is a more detailed catalog.
- The major technological trends occurring as of 2025 will be the development of LLM and the development of world computers.

Development of LLM
    - [[broad listening]]
    - ![image](https://gyazo.com/8aed1a6ee239c672d1e504cdb48d0e9e/thumb/1000)
        - The development of technology to duplicate and distribute information has made it easier for one person to communicate ideas to a large number of people.
        - However, when a large number of people transmit information, the volume of information received by one person becomes enormous, and the person drowns in the flood of information.
        - In a society and company where people actively communicate, technology that supports listening to the opinions of many will be important.
    - Talk to the City] created by the American non-profit organization [[AI Objectives Institute]] and [[public information AI]] developed by the Japanese [[Digital Democracy 2030]] project based on it.
    - Several political parties in Japan have taken advantage of this system, using visualizations created by this system for questions in the Diet and for reinforcing their policies.
            - [[Example of Talk to the City being used by the opposition in the National Assembly to question the Prime Minister.]]
            - [[Japan Restoration Association Broad Listening Case Study]]
    - How Talk to the City and Wide Hearing AI work
        - ![image](https://gyazo.com/c8d972283424ae2476ca9b8b9a836acf/thumb/1000)
        - From data such as people's statements, LLM first extracts fine-grained expressions.
            - The data can be anything as long as it is a list of strings. In the past, there have been examples such as extracting data containing specific keywords from SNS via API, collecting opinions on a subject using Google Form, collecting reviews written in a specific area of Google Map, collecting comments on games on Steam, etc. The following is a list of some of the examples.
            - A "fine-grained expression" is a short sentence, e.g., "opinion." Other types of expressions can also be extracted, such as "questions," "criticisms," and "problem statements. What is extracted can be specified in the prompt to the LLM; prior to Talk to the City, these were "keywords" or "topics. The shorter sentences allow for better retention of meaning than the amount of information.
            - The next step uses LLM to embed that short sentence in a high-dimensional space of several thousand dimensions. Now that this is possible, it is useful to extract short sentences rather than keywords as a fine-grained representation in the previous step.
            - There are diverse variations thereafter. For example, UMAP can be used for dimensionality reduction and visualized as a two-dimensional scatter plot, clustering can be applied to create groups of "opinions with similar meanings," and LLM can be used to generate explanations of what kind of opinions the groups are.
            - The features of the Wide Hearing AI are hierarchical clustering, which allows for group drilling, and the ability to focus on groups with high density. iv
- pro-social media
    - Let us imagine, for example, an electronic bulletin board on the Internet. Roughly speaking, for every 100 people on the Internet, there will be at least one person who makes a personal attack or has a harsh tone. Once such a person appears, about 3 out of 100 people will begin to emotionally rebut him or her, or say, "That kind of language is not good," or attack the individual who made the assertion in a harsh manner. Once this cycle begins to turn, the place for productive discussion is destroyed.
    - Audrey et al. describe social media as having become "anti-social media" by participating in a direction that breaks social bonds. media" by participating in the direction of breaking social bonds.
    - Can we design social media in such a way that more productive discussions can take place? This is the idea of pro-social media
    - For example, [[Polis]], developed by The Computational Democracy Project, an American non-profit organization, and made famous by Audrey Tang's use in Taiwan, is designed to allow people to vote for or against an opinion and to draw attention to what is commonly agreed upon by different opinion groups. It is designed to encourage radical and divisive views. Opinions that are radical and divisive are immediately hidden from view.
        - Motomi Hori describes it as "[Existing social networking sites focus on the individual, but Polis focuses on the group, not the individual.
    - Your Priorities, developed by an Icelandic non-profit organization [[Citizens Foundation]], is a system for posting opinions for and against a topic. This also does not allow replies to specific opinions.
    - In Paul Graham's "Life is Short," he also discusses the detrimental effects of feeling "attacked" by an online discussion, and then responding with a "defensive" response. This concept is not unique to digital; for example, mediation procedures in courts involve "[[separate mediation]]," in which the parties take turns meeting with a mediator rather than arguing directly.
    - In the words of Audrey Tang, "[[If]] the left is making a good argument, what the right should be doing is making an equally good argument, not fighting."
    - Design UX and incentives that do not allow humans to directly attack others so that better discussions can take place.
- Support for deliberative discussions
    - Broad Listening is using LLM to "augment the ability to hear many voices."
    - pro-social media was designed to help people discuss things better using pre-LLM technology
    - The development of LLM allows for a system that directly supports people to better discuss
    - Researched around the world
    - For example, Google DeepMind's Habermas Machine takes as input the opinions and short critiques posted by people, and the AI generates group "consensus statements," which are then revised by the AI after repeated human ranking votes and critiques.
    - In a paper published in Science (2024), experiments using the Habermas Machine showed that consensus text generated and revised by AI was rated higher in terms of information, clarity, and fairness than consensus text created by human moderators, and the division of participants' opinions was reduced.
    - In Japan, the Digital Democracy 2030 project is developing the [[IIDOBATA system]]. As of the summer of 2025, several political parties are using this system.
    - The system uses AI interviewers to chat with individuals, helping them verbalize their thoughts by answering questions from the AI.
    - There are several variations in the use of hearing results, depending on the purpose.
    - For example, from the interview results, what each person perceives as a problem and how they think it can be solved can be extracted, which can then be compiled into a report and shared. In an actual application example, 150 people discussed with the AI for 5 minutes on YouTube Live, and 230 issues and solutions were extracted.
    - In another application, a system was put into operation that allows a human to ask questions to the AI or suggest improvements to the AI, given a document in advance. In this case, too, the AI interviewer and the human could have an in-depth conversation about what questions they had, what they perceived as problems, and what kind of suggestions they wanted to make. The experiment yielded 9,000 suggestions for improvement, a remarkable result for a large-scale social experiment, but it also revealed a bottleneck in that the improvement suggestions were structured to be created as GitHub PR directly via MCP, making it difficult for AI to summarize them.
    - The Digital Democracy 2030 project is also discussing the design of the next version based on the results of this experiment, which is a party-neutral open source project that anyone can participate in if they are interested.

The world computer called Ethereum
- Another major technological innovation is the formation of a new computer called Ethereum. Let's look back at the stream of technological innovations driven by capitalism.
- Capitalism that created a worldwide division of labor and cooperation
    - About 70% of international trade today consists of global value chains in which parts and services cross borders many times. People in different parts of the world, who do not know each other face to face, divide and cooperate in manufacturing through the medium of capitalism.
    - Audrey et al. believe there is a tradeoff between depth and breadth in cooperation. Capitalism is a very broad and shallow form of cooperation.
    - We believe that technological advances should enable us to make this a much deeper cooperation.
    - ![image](https://scrapbox.io/files/68abf3f915304bc63b3d46cf.png)
- In 2015, Ethereum begins operating. It is the birth of "a general-purpose computer that performs the same state transitions while being distributed on a global scale.
    - While Bitcoin, which went live earlier, in 2009, was designed to create "money," Ethereum was designed to create computers.
        - (Supplement: [[Bitcoin is money, Ethereum is a computer.]])
    - A common "state" is written and shared worldwide on the blockchain, and an EVM (Ethereum Virtual Machine) deterministically executes the bytecode, leading to identical state transitions on all nodes.
    - This created a "world computer" that is globally distributed and logically performs a single calculation, in which anyone can participate and which will not stop as long as someone else participates.
        - It is often said that Web3 technology is characterized by being decentralized, but Ethereum creator Vitalik Buterin thinks differently. It is hardware decentralized; no computer is a single point of failure. It is politically decentralized; no one person or organization is in control. Yet it is logically centralized, state transitions are uniformly agreed upon, and the entire system behaves like a single computer. This is what Ethereum brings. (Reference: [[Three axes of centralization]])
        - This created a global variable in the literal sense of "Globe = Earth.

- Automation of Execution
    - In the past, human societies used a system in which "contracts" were made on paper, and when those contracts were broken, civil lawsuits were filed and eventually enforced by state power. The cost of these contracts and civil suits is very high.
    - On the other hand, the implementation of "what process is to be performed under what conditions" as EVM code has made it possible to automatically enforce contracts in a way that does not depend on the power or legal knowledge of a particular state. This is the smart contract.
    - Prior to this, software services were still able to provide functionality to the entire world. The advent of smart contracts became a source of trust in contracts that did not depend on "trust in the operator or the state in which it resides. (Footnote: However, the automatic enforcement of smart contracts extends only up to the on-chain state; trust in the entity that performs them is required when they involve real-world events or transfers of rights.)
    - The NFT, which was briefly discussed in the context of Web3, is an object created in the aforementioned global scope, and its ownership means writing your address in the "owner field". The bytecode is written so that only the owner can execute the transfer function that rewrites this field.
    - This is one simple application of smart contracts. It is a "transfer of ownership" mechanism that allows only the owner to pass ownership to another owner, without depending on a specific service provider or the state.
    - However, several fraud cases have arisen due to people who mislead people into believing that they are acquiring legal rights such as copyrights, or who advertise as if it is inevitable that the price will increase in the future.

- prediction market
    - This trust through smart contracts has led to the revitalization of the forecasting market.
    - It is now possible to create a market anonymously, bet money anonymously, and take it from the losers and give it to the buyers through automated execution.
    - In the world's largest forecasting market [[Polymarket]] (2020~), for example, over USD 3.6 billion has been spent on who will win the US presidential election in 2024.
        - ![image](https://gyazo.com/7e4782c51c8cda9ffe98457e2bffb4be/thumb/1000)
            - [Polymarket | Presidential Election Winner 2024](https://polymarket.com/event/presidential-election-winner-2024?tid=1754025017161)
    - Anyone can say irresponsible things in social networking posts. You can make a strong claim that you are confident, even if you are not. But in the prediction market, how much you are betting on your opinion is a signal of confidence.
    - This makes the forecasting market a "collective knowledge system with confidence information" different from social networking.
    - In Japan, prediction markets have not received as much attention as in other countries because of the risk that prediction markets using real money are considered gambling. Although there is an argument that a prediction market using game money could be useful, the author believes that the existence of a prediction market that can be cashed in would be beneficial to society. This is because if the cash profit from disseminating radical opinions on social networking sites without doing proper research is outweighed by the cash profit from properly researching facts, making predictions, and disseminating them with confident information, there will be an incentive for people in society to do proper research and think properly. Since it is in the interest of society to conduct proper research, think properly, and disseminate information, it is preferable to have incentives to do so.
    - In Japan, the Diet passed the IR Implementation Bill (a.k.a. Casino Bill) in 2018, and horse racing and pachinko have been socially acceptable for some time. The boundary between what is and what is not gambling is not self-evident and is merely a "current decision" that can be changed by the legislative body.
- Decision-making algorithms
    - One algorithm is to vote [[one person, one vote]] to decide the majority.
    - One algorithm is to let the prediction market decide
        - At present, the commodity futures market is still considered to be a mechanism for predicting the supply and demand of commodities and determining future prices.
        - Expanding this to more diverse is the forecasting market.
    - In our time, when capitalism has spread beyond the boundaries of a single country to a global scale, money already determines many things.
        - However, many people may not like the idea of money determining things.
        - A nice algorithm has been proposed by Glen Weyl, author of the aforementioned Plurality book
    - [[Quadratic Voting]]（QV）
        - [[one person, one vote]], but a system in which the cost of a vote increases on the order of the square. While preventing the tyranny of the majority, even a minority can exert influence if there is a strong interest.
        - When collecting data on the strength of people's opinions, for example, if one were to ask people to "answer on a scale of 1 to 100," it would not work as a means of collecting accurate information, since everyone would write 100 because writing a large number is more advantageous for getting their opinion across. Therefore, it is necessary to collect costs according to the "strength of opinion" by some function. This paper shows that if the strength of opinion is $x$, it is appropriate to charge a cost of $x^2$.
    - [[Quadratic Funding]]（QF）
        - Proposed by [[Vitalik Buterin]], founder of Ethereum, in collaboration with Glen Weyl (2018)
        - A good mix of crowdfunding and voting, with Quadratic Voting cost payments as the donation amount.
        - Funds are allocated from the matching pool in proportion to the square sum of donations. This ensures that public goods that garner broad support receive more funds.
        - [[Gitcoin Grants]] launched in 2019 with this structure and distributed a cumulative total of over $66.65 million to open source projects through December 2024.
    - Intuitive explanation of the meaning of square root
        - ![image](https://gyazo.com/7de5f0eae25deb83ad3ae020628a2fd5/thumb/1000)
            - In QF, 1 million yen (=1000 voting power) from 1 person and 100 yen (=10 voting power) from 100 people have the same power.
            - $1 person \times \sqrt{1000000 yen} = 100 people \times \sqrt{100 yen}$
        - ![image](https://gyazo.com/b7b59fcc5cc066b7adaf26378206f3f6/thumb/1000)
            - If 1 million yen is divided among 100 people, each person gets 10,000 yen.
                - A person who thinks plan A is good pays 10,000 yen per person to 100 people who think plan B is good (= can pay up to 100 yen).
            - Even those who think Plan B is better are paying 10,000 yen for one person who prefers Plan A, divided among 100 people.
            - In other words, there are incompatible decision-making options in society, and no matter which one is chosen, there will always be "people whose opinions are not accepted. The opinion of the side that can offer more compensation to this "person whose opinion does not agree with mine" will be adopted.
    - [[Retroactive Public Goods Funding]](RPGF)
        - Vitalik Buterin proposed a more advanced public goods funding mechanism for 2021. It is Retroactive Public Goods Funding. It is designed based on the idea that "it is easier to build consensus by looking back on achievements that have already been useful than by predicting future usefulness.
        - A large-scale social experiment is underway at Optimism's RetroPGF, with USD 120~150 million distributed over 3 years.
        - Conventional public subsidies and public solicitation require judges to have the ability to predict the future because they review and evaluate projects at the planning stage, saying, "If we build this, it should be worthwhile. Even if the project sponsor has knowledge that "that approach will not produce the results that the client thinks it will," there is no merit in being honest about it, so there is an incentive to hide the information and make the project be overvalued. On the other hand, since the RPGF will review and reward the project after it has achieved results as a public good, there will be an incentive to work hard on implementation and dissemination.
        - Of course, there is the problem of not having enough money up front to start a project, so Vitalik thinks that a hybrid format is better, where the seeds are widely sown in QF, and after a while they sprout and begin to grow, and then the healthy-looking shoots are fertilized with RPGF.
    - [[Futarchy]]
        - [[Futarchy]] is a governance system proposed by Robin Hanson in 2000 that incorporates predictive markets.
        - It came to attention in 2014 when Vitalik wrote an introductory article on the Ethereum Foundation Blog.
            - ([[An Introduction to Futarchy]])
        - Futarchy has only been experimented with a maximum of 1,600 people. It is introduced here because it is close to the cutting edge of the direction of considering society as a calculation and how to update it.
        - The basic idea is to let the prediction market determine whether a policy is good or bad. [[Futarchy]] votes on what it wants to achieve and leaves it to the prediction market to decide how to achieve it. Let's consider a concrete example. Suppose that the KPI to be aimed at is "disposable income per capita in five years. Let us assume that there are the following three specific policies.
            - A: Corporate tax rate remains unchanged at 30
            - B: Reduce corporate tax rate to 25
            - C: Significant reduction in corporate tax rate to 20%.
        - Each of the three is made into a forecast market that predicts "disposable income per capita five years from now if this policy is adopted. The policy with the highest predicted disposable income after a certain period of time is automatically enforced.
        - This alleviates concerns about voting with money as the vote. If this were simply a vote for money, the concern would be that business owners would vote with lots of money to lower the corporate tax rate above the appropriate level. In the case of a prediction market, however, those who spend lots of money will have a strong incentive to "increase per capita disposable income five years from now. It is a mechanism that encourages people to cooperate with the objective.

I have explained the technological trends that are changing society as of 2025.
- This is an area that is often summarized as AI and Web3, but we did not use this term because we considered the resolution of this expression too coarse and harmful.
- A paradigm shift in computational design is making people's conversations computable objects, creating a structure of communication among people in a form that never existed before
- Automated enforcement by world computers has created a way to motivate humans without human intervention across borders.

Think about the future from here.
- At the 2025 World Exposition, the story that "humans were once smart creatures" and that smarts will now be just a "bonus" became the talk of the town.
    - This means that AI is surpassing the smartness of mankind and mankind is relinquishing its position as the primate of all things. I personally believe that there will come a time in my lifetime when most people will feel that humans are not the smartest beings in the world.
    - This is not a "0% or 100%" story where everything is taken away from humans in one moment, but a story where humans will transfer many things to AI over the next few decades.
    - Some of the things that humans used to do will be done by AI, a few things that humans continue to do will remain, and then humans will do something new.
    - ![image](https://gyazo.com/78a6a9aa82f0d0f623829f63637a7c73/thumb/1000)
        - Rephrase: [[Part of it disappears, part of it remains, and a new one is born.]] X shifts to X'. a: what disappears b: what remains c: what is newly born
- There is no doubt that the long-term future will be "that kind of world," but this "that kind of world" has low resolution.
    - We tend to think of it as a point, but it actually has a range.
    - ![image](https://gyazo.com/b7dd5bb4d745ad34170d065c4d41f9c6/thumb/1000)
    - We need to be careful not to walk into a hole by looking only at the distant stars.
    - In other words, we must look carefully at what the next step should be in the current reality.
    - I think the key to this is the design of the objective function.

Objective function design
- Futarchy is an interesting application, but I don't think it is a cure for any problem.
- The reason is that the "voting" method of determining the "objective" is a postponement of a difficult problem.
    - The progress made by Futarchy lies in the automatic algorithmic determination of the means of achieving objectives and the automatic smart contractual execution. The method of determining the objective is left untouched.
- A compactly verbalized objective function that can be subject to voting is only a small part of the space of possible objective functions, and perhaps the optimal solution is not in that space
- Often the option of a weighted sum of A and B is ignored when discussing the choice A or B
    - Although "A 100% B 0%" and "A 0% B 100%" are simpler and easier to understand and tend to focus attention on the extremes, in reality there are cases where blends such as "A 70% B 30%" and "A 40% B 60%" are the optimal solutions.
    - An automatic adjustment mechanism for weights is needed because the burden is too heavy for human thinking ability and optimization is not being performed.
- The author believes that even if there were automatic adjustment of the weights of the options, it would not be enough.
    - The appropriate social objective function is in a space that cannot be represented by a weighted sum of alternatives
    - This is due to the fact that each individual has different values

Attributes in trade-offs
- Where the optimal balance lies depends on individual values.
- For example, there is a tradeoff between "camera resolution" and "low price" for smartphones.
- ![image](https://gyazo.com/eb354d53b78e3b88717b0932285530b0/thumb/1000)
        - Trade-off between high camera resolution and low price
- Do you prefer a higher resolution or a cheaper resolution? or "Do you prefer cheaper?" However, there is no such thing as the world's highest resolution and cheapest smartphone. People have to choose from among the available smartphone options.
- At this point, people differ in how important they consider each attribute. Therefore, there is a wide variety of products in the world, and people buy different products from different people, not just one product.
- This means that each attribute is weighted differently in the function of individual well-being.

Efficiency and Freedom
- Increasing the individual's freedom to pursue happiness implicitly assumes an objective function with the individual as the domain of definition. It is a model in which each individual is self-reliant and optimizes with his or her own objective function.
- The goal of total optimization of society as a whole implicitly assumes an objective function that takes society as a whole as its domain of definition. When this objective function is simple, differences in people's values are considered noise.
- If we respect the differences in individual values, then the objective function of society as a whole becomes a function with a number of terms proportional to the number of human beings.

How to define the objective function
- Should it be designed by humans thinking linguistically? Or should it be acquired through learning by collecting large amounts of data?
- Given the history of rule-based design losing out to machine learning, the author feels that the latter is the way to go.
- Before that, humans may not be able to design objective functions that respect individual differences in values.
- Influenced by their own values, they impose their idea of happiness on others.
- In the long run, AI will become smarter than humans and AI will govern humans. In that case, AI will rule "to make people happy. The definition of "people's happiness" by some humans would be an imposition of values.
- So by this time, there must be a mechanism that can construct the objective function of "people's happiness" in a way that is not determined by a few people.

Grip the steering wheel and proceed with caution.
- Both extremes, 100% efficiency and 100% freedom, probably lead to tragic futures. There are many other tragic futures besides the extremes that are generating the gravitational pull. It is like a road with cliffs at both ends and many pitfalls in between.
    - ![image](https://gyazo.com/5cd0defbde524a26d7c83a2275eed30a/thumb/1000)
        - Both bridges of the road are cliffs, and the road between them has a number of pitfalls.
- It is important that people hold the steering wheel firmly. If we are somehow moving forward, we will fall on either side. This is a future in which a type of state that sacrifices the freedom of its citizens for the efficient operation of the state gains influence backed by strong military power, etc., and a future in which individuals who have accumulated private property as a result of too much loosening of state control for the sake of individual freedom gain strong influence through capitalism.
- It is also necessary to observe one's surroundings, recognize hazards early, and avoid them.
    - Cognitive capacity needs to be augmented in order to observe well.
- It is good to be on the side of the telescope when it is invented and not to be on the side of those who criticized it without looking through it.
    - Just as mankind gained the ability to see at a distance with the invention of the telescope, mankind gained the ability to know the feelings of many others with the invention of broad listening.
    - While utilizing this, we must avoid pitfalls and move forward to a better future.

summary
- I thought about "society" as "human computation" and how it could be improved from the perspective of computer science.
- Throughout history, from the punch cards of Hollerith to ENIAC to the modern LLM and Ethereum, mankind has externalized "the vast amount of computation done in society" and replaced it with faster and more accurate computation.
- This expansion of computational power is beginning to affect not only the military and public administration, but also the very foundations of society, such as elections, policymaking, and funding for public goods.
- LLM, one of the technologies that is having a major impact, has followed history to confirm that the shift in the computational paradigm is a source of strength.
- The rule-based design paradigm is losing ground to the weighted sum = learn paradigm and is reaching beyond human performance in image recognition, translation, and dialogue.
- In addition, experiments are underway to link funding and decision-making, such as Quadratic Funding/RetroPGF/Futarchy by the world computer Ethereum. These have dramatically lowered the cost of "execution" while leaving the fundamental issue of "what is the purpose?
- The design of this "objective" will be important in the future. In order to ensure diverse human happiness under AI governance, it is essential to have a system that can take in multiple values from many people and dynamically adjust the weights of those values. Using broad listening and prediction markets as a telescope, we must steer clear of "pitfalls.
- Let's design an operating system for a new society as the last work of Homo sapiens.

---
This page is auto-translated from [/nishio/社会を人間による計算として考える](https://scrapbox.io/nishio/社会を人間による計算として考える) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
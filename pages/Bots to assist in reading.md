---
title: "Bots to assist in reading"
---

- Organize the ideas you have written down in [[Thinking about speed reading]].

- We need clarity of purpose.
    - The goal of eliminating piles of reading
        - Newly arrived books can now be looked through on the same day.
- The following achievable objectives need to be identified

- It's not a good idea to leave a "I meant to read it, but I didn't."
    - If you decide to read it, you should.
    - If you don't read it and keep it.
        - If you expect to get a search hit in the future when you need it.
        - You should make sure you get a hit in your search.
    - If it's neither, it should be discarded.
    - Should be "handled" one way or the other
- We should "look over" everything at a level high enough to determine that.
    - Some of the things that are being "looked over", including books, should be read more carefully


- If you download a paper you intend to read, you should look over it that day.
- When you receive a subscription to an academic journal or other publication, you should look through it that day.
    - [[Should→why?]]

- What was not worth reading today will be worth reading tomorrow?
    - Can't say I wouldn't get it...
- Should I read what I have already accumulated?



- What does "reading carefully" mean?
    - To "read well" means to invest more time in reading the book
    - Investments are made with the indication that more new ones are likely to be obtained.
    - What's the point of reading a book to gain new insights?
        - Trying to answer this question in general would be too abstract.
            - = Contrary to the fact that goals must be specific
        - General answer
            - To improve the model in one's brain and increase the probability of being able to cope with possible unknowns in the future.
            - To improve my model, I need to encounter things that cannot be explained by my current model or that contradict the explanation in my model.
            - It's what you can't easily swallow that's worth chewing on.

                - [[Don't aim to encounter the unknown.]]
                - It reduces motivation because the effort is not reliably accomplished.
                    - Really?
                        - When it comes to work that is assigned to you, if you don't get results despite your efforts, you feel demotivated.
                        - But from a [[flow theory]] point of view, a success rate of 1/3 is the most exciting.

- Goals for a quick sense of accomplishment are different from goals for a sense of accomplishment
- Probabilities cannot be known in advance, so it's difficult to adjust them yourself.
- Is it easier to get into the flow if you can adjust the difficulty of the task yourself?
    - A near and surely achievable goal is to keep track of the number of books you read and the amount of time you spend reading them.
        - Now they're being recorded individually.
            - How many books have you read in total?
            - And how long did that take?
            - How about visualization?
    - The goal, which is a distant and challenging one, is to find something interesting.
        - Related: [[Stretch Goal Setting]].
        - n or more per week.
            - With this way of setting up, you can adjust by increasing the amount of reading or daring to try different fields when you cannot find them.
            - Record the time taken.
            - You can measure the difficulty and adjust n to achieve a reasonable balance.
        - You can blog about interesting things you find.
            - Reinforcement of preferred behavior by linking it to the need for approval.

- First, a tally of what we've done so far, then measurements for the future.
- Attending study groups, like reading, is also a mess where you invest time to get something interesting.
- Let's record everything.
    - Let's tally up, week by week, the time and money invested and the interesting things gained.
- Do not envision a system that is too complex from the start.
    - I hate it all when I fail to execute due to my poor administrative skills.
    - First, it should be implemented minimally to validate value.
- I would like to support this with a bot.
    - Recommendation from sentence to sentence
    - Suggestions with sources in blog corpus and library corpus
    - Enhanced with a like.

- I'm thinking of the hippocampus model.
- Image of a rat running around
    - Running or turning at zero knowledge is randomly determined.
    - Take actions that seem good when you have knowledge, but also explore, i.e., [[reinforcement learning]].
- Running hits the wall.
    - Recognize wall condition
- Do we have different states of each step in short term memory, or is it a gradual differentiation of the identical?
    - If you're walking down the street and the unification happens at "oh, this is where I've been before," then you've had it separately until then.
    - But what is that unify? If you equate states when given the same input, they don't become separate in the first place.
    - If the input is not identical due to some noise or historical information, the UNIFY side will have to allow for some error, and we are back to square one.
        - (2019 comments <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>)
            - If unification occurs by similarity of input vectors, then it's just [[k-means]].
            - Unify mechanism different from normal distance is needed here.
            - It's "whether or not it's close to the time we threw out the information on a particular axis."
            - It's a comparison with some of the input vectors set to zero.
                    - [[dimensionality reduction caution]]
    - Is the Blue Star Algorithm relevant?
        - <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>That possibility cannot be ruled out, especially in the sense of [[Pattern discovery from time series input]].
    - For this issue to be resolved, it would mean that UNIFY is not a zero-one.
    - That is, the states are not a discrete set, but are distributed over a continuous space, with distances far and near.
        - [[Distributed representation of states]]
        - <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/> [[Vectorization of states]]
    - Grid cells just happen to be a grid because the state of the grid is two-dimensional, but it's a distributed representation.
        - <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Of course I think so.

- Need a mechanism to do this:.
    - Hitting a wall.
    - I feel discomfort.
    - As we move forward, we'll anticipate feeling discomfort again and avoid it.
- Needs a distributed representation of the state and a neural net that takes the next action as an argument and predicts the reward to be obtained
    - This can be learned every step of the way.
    - Returning a reward with the state and next action as arguments is [[Q-function]].
- I'm sure my brain simulation will learn to make a U-turn when I hit a wall, for now.
    - If we can understand that "where there was nothing before, there will remain nothing."
    - After making a U-turn, he's going to turn and explore as he sees fit.
- How is a distributed representation of the state created?
- If the CA3 recurrent is randomly initialized, it would be possible to randomly initialize the variance representation, since we'd get an appropriate value at each step anyway.
- Is there a grid-cell-like cycle in the time direction as well?
    - <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/> [[Hippocampal time compression]]
- To make the state of nearness near.
- If a neural net has been trained to return a state from a previously experienced state-input pair, where the input returns the state for the argument, then it seems possible for the recurrent net to relearn, but in that case the firing pattern is just an ID, not a distributed representation
    - Is that still okay?
    - Then the incoming states of similar inputs come to fire together, which is redundant, so compressing them allows unification.
    - I think I can do it if I put sparse constraints on it.
    - Then it's going to be a place cell thing.
- If this is a distributed representation with sparse constraints, would it be a grid?
    - Not so easy.
- It is a good thing if a place cell is created.
- Once we have a model that can produce place cells, let's feed them natural language as input.
    - I hope the rat has a neural net that receives the state and returns the next action, and that guy is initialized randomly at first.
    - Then you're repeating the same behavior.
    - How to do something like UCB1 with neural nets
    - A mechanism that narrows when nothing happens.
        - [[Thompson sampling]] or
    - No, I guess not.
    - Need a neural net that can express confidence
    - Is it enough to have lots of outputs?
    - There is a randomly initialized net that takes a state and returns an action, with several outputs for each action and a majority vote.
        - <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>If there are multiple identical networks with different random initial values, the outputs will be disparate with little learning, and similar outputs will emerge as the learning progresses, thus expressing "[[degree of confidence]]".

- The condition looks better coming in before the sparse.
- Actually, maybe the behavior is a distributed expression, too.

- Realization of delayed compensation
    - If we used rewards directly to learn this state-action mapping, we would not be able to deal with delayed rewards, so life began to predict and estimate the value of the next state sometime in the future.
    - We have to do something here, because if the rats don't run around, the map won't be made, and if they don't understand the delayed rewards, they won't run around.
    - All you need is a lot of output from a neural net that takes a state and an action and returns a value.
    - The distribution of output is uniformly distributed since it is initially initialized at random
        - Sharp distribution as learning is repeated.
    - If we choose the largest randomly selected one of these outputs, it is roughly Thompson sampling
    - Oh, you don't have to work hard to realize Thompson sampling or UCB1, or even epsilon greedy.
    - If only we could have introduced neurons that randomly select

- After sparsing the state, it's normal reinforcement learning, so we should implement it normally and first test the expectation that nets from input to state and recurrent nets and sparsing will produce place cells.
- So far, we have created cells that respond to specific locations, but their positioning is still in question.
- I wonder if it learns state transitions even after sparsing...
- There is no recurrent over here, though.
- Hourly average.
- How to make states that transition closer and states that do not transition farther away
    - Stimulated neurons remain active longer than the temporal resolution of other neurons
    - Its neurons act as a compression of the time axis.
- The orientation cells are born here because "running straight" is a frequent, natural behavior of rodents.
- I hope the duration of the firing is determined by some concentration, and that there is a concentration gradient along the hippocampus.
- I don't know why it's on the grid...
    - Surprisingly, you might be able to get a grid just by compressing time averaging into two dimensions.
        - My guess is negative.
- It seems to be born out of the behavior patterns of rats.
- My interest is in natural language anyway, so I don't care about the grid.
    - It would be amazing if we could inadvertently grid
- What happens when you create and nurture an [[intelligence form]] that can only read and write?
---
This page is auto-translated from [/nishio/読書を支援するボット](https://scrapbox.io/nishio/読書を支援するボット) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
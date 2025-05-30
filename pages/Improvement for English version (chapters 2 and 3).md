---
title: "Improvement for English version (chapters 2 and 3)"
---

Click here after chapter 4 [[Improvement for English version (chapters 4 and 5)]].

- For example, a good cook can wash the cutting board used to cut the ingredients while waiting for the pot to heat up and the ingredients to cook, or prepare a plate to serve the cooked food. But someone just starting to learn to cook cannot do that. Those who are good at it know how long to wait for the food to cook and how long it takes to wash the cutting board. So they can make the decision, "I can wash the cutting board during the time it takes to wait for the fire to come on. Those who are just beginning to learn cannot make this judgment, so they cannot process in parallel.

+ For example, a good cook can perform multiple cooking tasks simultaneously. While the ingredients are heating, they can wash the cutting board used to cut the ingredients or prepare a plate to serve the heated ingredients. But someone who is just beginning to learn to cook cannot do so. Those who are good at it know how long it takes to heat the ingredients and how long it takes to wash the cutting board. So they can determine that they can wash the cutting board while they are waiting for the ingredients to heat up. A person just beginning to learn does not know how long it takes. They cannot make this judgment. So they cannot do parallel processing.

- Even when it appears that you are working on multiple tasks in parallel, you are doing one task at a time, switching between them as you go. Running multiple tasks in parallel means that you have the additional task of "making the decision to switch between tasks". If you are trying to do multiple tasks and feeling unmotivated or confused, first narrow it down to one thing to do and get it done one at a time.

+ Even when it seems that we do multiple tasks in parallel, we do only one task at each moment. We switch the target task rapidly. The switching cost is not zero. Executing multiple tasks in parallel has an additional task: the decision of task switching. The cost of switching is low for experts, high for novices. If you are trying to do more than one task and you are not motivated, let's focus on one thing first and finish them one by one.

- Because of the high cost of cleaning up "the whole room."
+ Because cleaning up "the whole room" takes time.

The cost in this case is time cost, so I specified it clearly.

- In these situations, we often try to prioritize tasks.
+ In these cases, we are often advised to prioritize tasks.

- Sorting Computational Complexity
+ A burden of sorting

I guess it's "hard to keep them in line."

- In fact, many people have probably experienced spending more than three seconds thinking, "Which should I do first?
+ In fact, many people spend more time wondering which task to prioritize.

- There is a naive definition of magnitude for one-dimensional values, and many people agree on it, so there are few discrepancies.
+ There is a naive definition of magnitude for 1-dimensional values, and many people agree on it, so there is less disagreement about magnitude. Which do you think is bigger, 2 or 5?

I filled in the blanks because it was unclear what the discrepancy was. Concrete examples were also added.

- If we consider x and y equally important and compare them by x + y, then C is the most important. if x is twice as important as y, then 5 * 2 + 2 == 4 * 2 + 4, so B and C are of equal importance.
+ C is the most important because if you consider x and y equally important, you are comparing by the magnitude of x + y. If you consider x twice as important as y, you are comparing by x * 2 + y. Then, 5 * 2 + 2 == 4 * 2 + 4, so B and C are of equal importance.

- Discussing in advance will prevent time from being spent discussing what should be prioritized in a situation where time is short and tasks must be discarded.
+ Discussing in advance prevents time from being spent discussing which tasks should be prioritized in a situation where time is short and tasks have to be discarded.

Clarification since "what" is ambiguous.

- Discussing in advance will prevent time from being spent discussing what should be prioritized in a situation where time is short and tasks must be discarded.
+ Often, situations arise where team members do not have time to perform all tasks and must choose which tasks to perform. By discussing this in advance, you can prevent time from being spent discussing what should be prioritized in this time-poor situation.

- Is that really the right thing to do?
- Is it really the right thing to do? Are the pre-determined priorities correct?

- This argument assumes that the importance of tasks is independent, but in real software development, there are complex dependencies such as "doing task D will increase x in task A" or "doing task E will lower the implementation cost of task B" or "it is cheaper for one person to implement tasks F and G together than to implement them separately. Tasks F and G are complexly intertwined with dependencies, such as "the cost of implementation is lower if one person implements tasks F and G together rather than separately.
+ This argument assumes that task importance is independent. However, this is not the case in real software development. For example, the following phenomena occur.
- If you do task D, you increase x in task A.
- Doing Task E lowers the cost of implementing Task B.
- Tasks F and G are easier for one person to implement together than separately.
Real-world tasks are interdependent and complex.

Split because it is wordy.

- In fact, when we asked some people, they responded that they would try a few times and choose the best one.
+ In fact, when we asked some people, they responded that they would try each slot machine several times and choose the one with the best results.

- I also added "do not play slots" as an option and ran a simulation experiment with 600 agents playing 1,000 times.
+ I conducted a simulation experiment in which 600 agents made 1,000 decisions in an environment with three slot machines. The decisions were made by each agent to choose one of four options: one of the three slot machines or "don't play".

- Each agent was made to work with an algorithm that first played each slot three times and then chose the option with the highest expected value based on past experience. We prepared a "value slot machine" in which some slots have a 0.3 probability of winning. Of course, each agent does not know this. Can the agents find the "good deal" slot machine through their trials?
+ Each agent will first play each slot machine three times. Then, after that, they choose the option with the highest expected value based on their own past experience. We have prepared a slot machine that has a 0.3 probability of winning 500 yen. The expected value of this slot machine is 150 yen; putting 100 yen into this slot machine is a good deal, so the optimal solution is to keep playing this slot. Of course, each agent does not know that such a slot machine exists, nor does he or she know which one it is. Will the agents discover through their experience the slot machine that offers the best value for their money?

- The results of the experiment showed that a majority 57% of the agents were unaware of the value-for-money option and chose "do not play slots".
+ The results of the experiment showed that a majority 57% of the agents did not find the best slot machine. The majority of them chose "do not play slots".

- In the field of reinforcement learning, this problem is called the "exploitation exploitation tradeoff. If you only do what you "think is best based on past experience," you will never find a better behavior. That is not enough exploration. On the other hand, if all you do is "what you think is the best action based on past experience," you will not find a better action! and "inexperienced actions" only, you cannot take advantage of your past experience. That is lack of utilization.
+This problem is called the "exploration-exploitation tradeoff" in the field of reinforcement learning. If you only choose the option that you think is best based on past experience, you will not find a better option. That is not enough exploration.
+On the other hand, if you have been looking for better options and choosing only inexperienced options, you will not be able to take advantage of your past experience. It is underutilized.

> For example, in the UCB1 algorithm often used in computerized Go and Shogi,

Maybe you should add a heading in the front here.
Like the "UCB1 algorithm."

- For example, the UCB1 algorithm, commonly used in computerized Go and Shogi, adds a term that positively evaluates uncertainty before comparing alternatives.
+ The UCB1 algorithm is a common algorithm used in computerized Go and Shogi thinking engines. This algorithm provides hints on how to deal with uncertain situations...

Explain first why we are talking about UCB1.

- The wide confidence interval for A means that it may be much larger or much smaller than the average to date.
+ The confidence interval for A is wider than for B. This is because the uncertainty in A is higher; the advantage of doing A is that it may be much larger or much smaller than the average to this point in time.

- If we take this idea back to management, we are not judging by what we get on average by doing the task, but by what we get in the best case.
+ If we take this idea back to ### task
 management, let's decide whether to do a task based on what we will get out of it in the best case, rather than what we will get out of it on average.

- Cohn then insisted that we implement features with high monetary value and high risk first, then features with high monetary value and low risk, and finally features with low monetary value and low risk, but do not implement features with low monetary value and high risk.

Cohn then argued that
- Implement features with high monetary value and high risk first.
- Next, implement features with high monetary value and low risk.
- Finally, implement features with low monetary value and low risk.
- Don't implement features with low monetary value and high risk.

- In "Build a Base First" (* page), we first put the "tasks that must be done today" as the top priority, but is this really correct? Are all of those "tasks that must be done today" really "urgent and important"? We need to rethink this and say No to the unimportant ones.
+ In "Building a Base First" (* page), you first gave top priority to "tasks that must be done today". Now you have to think about whether those "tasks that must be done today" are really all that important. You need to find the ones that are not important and say no.

- It is easy to confuse "urgent" with "recently notified."
+ We often confuse "recently notified" with "urgent".

- If you don't write down your tasks, you might throw out the work you were doing and start on it because of the anxiety that you might forget if you don't do it right away.
+ If you have not written down the task, then you feel anxious that you might forget the task you have been notified about. This anxiety creates the misconception that you have to do that task immediately. You may end up throwing out the important but non-urgent work you were doing and start working on the notified task.

- Instead, let's consider whether it is possible to stop ❸.
+ Stop ❸ tasks that are not so important to you.

- For example, if an incoming task is a request from someone else, there may be room to negotiate whether it is possible to stop another ❸ task as an exchange for accepting the request.

- Covey said that what matters depends on your mission and values. However, if you have not verbalized your mission and values, you will not know what to base your decision on. How do you verbalize your values?

Is this a problem of "not knowing what to base importance on"?
Isn't the problem that without a handle on the concept, you can't manipulate it?

+ Covey said that what matters depends on your mission and values. In order to think with words, your mission must have a handle on it: words. How do you verbalize your mission?


- However, even if asked to clarify, many people may not be able to verbalize it quickly. Even if you make a decision in such a state, it may not lead to a good decision in your daily activities.

What does it mean to "decide appropriately?"
- [/intellitech-en/quick dicision](https://scrapbox.io/intellitech-en/quick dicision)

+ However, many people cannot tell their mission in their words yet. Even if they make quick decisions, the words will not connect with daily activities.

+ However, many people have not yet been able to speak about their mission in their own words. Even if they decide in haste and at random, those words do not connect well with their daily activities.


----
- Life goals are the top portion of the pyramid. Let's call it [[top-down]], meaning coming down from the top, to decide on this first and then bite off from there to decide on individual actions. [[Allen]] of [[GTD]] recommended [[bottom-up]], which is the opposite of top-down. 15 In this case, the bottom part is the daily actions.

The goal of life is the top part of the pyramid.
There are two directions to thinking about life goals.
One direction is descending from the top to the bottom.
In this case, we decide the goal of life first. And then, we judge the daily choice of actions. Let 's call the direction "[[top-down]]."

The opposite is "[[bottom-up]]."
In this case, we start from the daily choices. By observing daily decisions, we eventually find some common patterns from them. It is the [[information gathering]] and the [[pattern discovery]] we learn in Chapter 1. Through this [[abstraction]], we finally get our goal of life as our own words.

A reference to Chapter 1 was also added.

Life goals are the top portion of the pyramid. There are two directions to think about life goals. They are the direction of descent and the direction of ascent. Let's call it [[top down]] in the sense of coming down from the top, deciding on your life goals first and then chewing up from there to determine your daily actions. [[Allen]] of [[GTD]] recommended [[bottom-up]], which is the opposite of top-down.
This is the information gathering and pattern discovery that we learned about in Chapter 1. It is through the abstraction of this pattern discovery that we eventually verbalize our life goals.


- Is the task too large?
- The task is too big. Put another way, the goal is too far away. *1
*1: [/intellitech-en/1.2.2.2 Make the goal closer - the effect of tutorial](https://scrapbox.io/intellitech-en/1.2.2.2 Make the goal closer - the effect of tutorial)

- The fact that the task is too big and the goal is too far away, or that the task seems vaguely large due to lack of estimation of the task size, seems to be holding them back.
+ They think the task looks big because they can't estimate the size of the task. That undermines their motivation.

- The population here is precisely the 52% of those who answered that they would not be able to finish in four hours, and who were able to answer what they would do in the first 25 minutes, and 58% of those who were motivated by being told to do that.

To be precise, the denominator is A-C below.
A: Respondents who answered that they would not be finished within 4 hours
B: 52% of A: those who could answer what they would do in the first 25 minutes
C: 58% of B: Those who were motivated by being told to do it

- Since many people cannot write in this kind of large task state, it is common to divide the task into a "set a deadline for each chapter" task division.
+ If we regard writing as a big task, writing motivation is difficult to keep.
+ Therefore it is common to divide the task into each chapter and set the deadline for each chapter.


- The intellectual production task I am working on right now, "writing a book," is another task that is too large to estimate the time involved.
+ I am working on an intellectual production task at this very moment: writing a book. This task is another task that is too big to estimate time.

- To motivate myself for this major task of writing a book, I divide the major task of writing a book into three phases: writing down ideas and making a fusen, rearranging the fusen to come up with a structure, and drafting the manuscript based on the structure.


To motivate me for this big task of "writing a book",
I have broken down the task into the following three phases

- Write down ideas and make a fusen
- Rearrange the fusen and think about the structure.
- Create a manuscript based on the composition

- For example, [[Tadatsugu Kobayashi]] argues that the maximum duration of human concentration is 2 hours, so if the breakdown of a task is longer than 2 hours, it is necessary to break it down further and clarify the goal of each task. For example, [[Tadatsugu Kobayashi]] argues that the maximum duration of human concentration is two hours, so if the result of breaking down a task is more than two hours, it is necessary to break it down further and clarify the goal of each task.
+ - It is believed that there is a limit to how long humans can sustain [[(powers of) concentration]]. For example, [[Tadatsugu Kobayashi]] argues that human concentration can last up to 2 hours, and if a task takes longer than 2 hours, it is necessary to break it down into smaller tasks and clarify the goal of each task.


2.3.2.1 Limitations of Concentration Within
In terms of volume, "Imagine hiking on a mountain trail." It would be better to have a subheading before the
With "hiking parables," for example.

- Time, which tends to be viewed as continuous, is cut into pieces of a fixed length and named "pomodoro," and the size of the task is estimated by the "number" of pieces.
+ "Time" is often seen as continuous. Cut off a fixed length of time and name it "Pomodoro". This allows us to estimate the size of the task in terms of the "number" of pomodoros.

- Note 20: Some people mistakenly think that the length of 25 minutes has some profound meaning, but length has no meaning. For those who cannot concentrate for 25 minutes, I suggest shortening it to 10 or 15 minutes.
+ Note 20 Some people mistakenly think that 25 minutes has some profound meaning, but length has no meaning. If you have trouble concentrating for 25 minutes, I encourage you to try shortening it to 5 or 10 minutes.

Stop being indirect and be direct. Shorter time.

- Make a list of tasks for the day.
- Estimate the size of the task in terms of the number of pomodoros.
- + 1 pomodoro (25 minutes) timer starts at the beginning of the task
- During one pomodoro, focus on one thing without changing tasks.
- If an interruption by you or others occurs, record it.
- 1When you are able to continue in a pomodoro focused state, switch perspectives by standing up and taking a few steps, etc. Note 21

- If the Pomodoro timer had not sounded, I might have continued to work in a bad way without realizing a better way, with a narrow perspective that kept my viewpoint close to the problem.
+ If I had not used the Pomodoro timer I would have continued to work in a bad way without realizing a better way. Concentration brings perspective closer to the problem and narrows the field of view.

- To estimate how many pomodoros each task can be done in, first estimate the amount of tasks that can be done in one pomodoro, actually do them, and observe the discrepancies. Gradually, the accuracy of estimation improves.
+ To be able to estimate how many pomodoros each task can be done in, you first need to know how many tasks you can do in one pomodoro. Through the experience of completing tasks that you thought could be completed in one pomodoro but were not, or conversely, completed quickly, you will gradually improve your estimation accuracy.

- Note 22 This is much like conducting experiments to verify understanding.
+ Note 22 Observing the gap between estimated and actual time taken is much like an experiment to verify understanding. In an experiment, one observes the gap between expected and actual results.

This" is unclear, and "similar" is unclear as to how they are similar.

- Since then, I have decided to start a 25-minute Pomodoro timer when replying to emails that might take a long time.
+ Since then, I have decided to start a 25 minute Pomodoro timer when replying to emails that might take me a while. Even if I don't think it will take long, I have decided to start a 5 minute timer. This is because my estimates can be wrong.

If you don't write the second half, your explanation is one-sided.

- It is not "do it because it's a job," nor "do it because it's a plan," but "let's measure first.
+ The idea is not to use time because it is work, nor because it is a plan, but to first measure and clarify how you are using your time. This is a common concept in the Pomodoro Technique and Task Shooting.

I have been writing about these similarities with the feeling that "you don't have to specify because I wrote it a few pages back," but I reconsidered that I should specify because they are actually missing from my short-term memory in the use case of "reading an open page" or "reading little by little".

- "When you want to speed up a program, you should first measure (profile) in detail where it is slow."
+ "When you want to speed up a program, you should first measure (profile) in detail which code is taking time."

Clarification.

- Due to the number of pages, we could not write everything, but we will link to the system for identifying the causes of lack of motivation and its research results from the book's official website. If you are interested, please see there.

→I'd like to make an English version at some point, but I haven't gotten around to it yet, so I'm putting it on hold.
I should link to the Japanese version, but I haven't gotten around to that either.

three wins
- It depends on whether what is gained by one cycle is accumulated.
+ It depends on whether the knowledge gained by one cycle is accumulated.

clarification

- Specifically, drugs that block NDMA receptors in the hippocampus were injected into the hippocampus.
+ To disrupt hippocampal function, specifically, drugs were injected into the hippocampus that block NDMA receptors in the hippocampus.

- A normal rat is probably using the information from "landmark visibility" that it can directly observe to create a memory of "scaffold location" that it cannot directly observe. This is why they can quickly reach the scaffold even if they start from a different location. On the other hand, rats with a broken hippocampus may have memorized the specific steps of how they swam to the scaffold after being dropped into the water. So, when they started at a different location, they looked around for the scaffold just as if they had not learned anything.
+ In Morris' water maze experiment, rats cannot directly observe the location of the scaffold, but rats can observe the surrounding landmarks. Normal rats probably create a memory of the location of the scaffold that they cannot directly observe, based on how they see the landmarks that they can directly observe. So, even if they start from a different location, they can quickly reach the scaffold.
+ On the other hand, a rat with a broken hippocampus would only remember the specific steps of how it swam to the scaffold after being dropped into the water. This method can still reach the scaffold efficiently if you start from the same place. However, if you start from a different location, you will have to search around for the scaffold as if you had not learned anything.

- Repeated learning increases the number of synapses themselves.
+ Repeated learning increases the number of synapses.

This one is clearer.

- In the case of the person whose hippocampus was removed, he could not recall memories up to several years before the surgery, but he could recall his childhood memories without difficulty in speaking.
+ In the case of the person whose hippocampus was removed, he could not recall memories up to several years before the surgery. However, he had no difficulty in speaking and could recall memories of his childhood.

- And if the same stimulus comes before the memory disappears, another step is taken to create a more long-lasting memory.
+ And if the same stimulus comes before the memory disappears, another step is taken to create a more lasting memory.

- Memories are created in stages and stored in a gradual, long-lasting way through repetition.
+ Memories are created incrementally through repetition and are gradually converted into long-lasting memories.

- If there is one thing that gradually gets stronger with repeated use, it is muscles. Creating a memory is more like training a muscle than keeping a file.
+ What is one thing that gradually gets stronger with repeated use? One example is a muscle. Creating a memory is more like training a muscle than keeping a file.

- The brain has a mechanism that makes it easier to temporarily consolidate memories when we experience strong fears or other experiences. However, it is not something that can be used as a tool for memory on a daily basis, so I omitted an explanation.
+ The brain strongly consolidates memories when it experiences strong fears and other experiences. However, this mechanism is not something that can be used as a tool for memory on a daily basis, so I omitted to explain it.

- remember
+ Inscription
The latter may be a more major translation of "memorization" in the field of psychology.

- This is a mechanism for ignoring unhelpful stimuli, similar to the way we become bored when we are forced to read the same sentence over and over again.
+ This is a mechanism for ignoring useless information. It is similar to how repeating similar tasks becomes increasingly tedious.

There is not enough of a relationship to connect them with "ga".
Stimulus → information, related to the below

- What does "useful" mean to the brain? It means "to be rewarded.
+ What is "useful information" to the brain? It is "rewarding".

Specify clearly so that it is easy to see that you are writing about the opposite pattern of the paragraph above.

- Theta waves, which are generated in the hippocampus when information is input, work to compress time by a factor of about 10.
+ Theta waves are generated in the hippocampus when information is input. These theta waves work to compress time by a factor of about 10.

- So the process of creating abstract information from concrete information is at work here.
+ So the process of creating abstract information from concrete information is at work in the hippocampus.

- The percentage of correct answers increased to 47.4% when the test was taken on the day the textbook was read and a second test was taken seven days later.
+ The percentage of correct answers increased to 47.4% when the test was taken on the day the text was read and a second test was taken 7 days later.

- The fact that the test will take place and the timing is confidential to the subject.
+ The test is unannounced. Subjects do not know at the time they read the text that they will be tested later.

- The correct answer is a "difficult problem" that cannot be successfully identified by a weak discriminator alone because of the staircase-like arrangement of A and B.
+ This is a difficult problem for a single weak discriminator. This is because in the correct answer, A and B are arranged in a staircase-like pattern.

- I challenge you to do this.
+ How can we solve this problem with a weak discriminator?

- Put aside the weak learner ❶ who answered the first test and study the new weak learner❷. At this time, instruct the students to focus on the questions they got wrong the last time and remember them; suppose that in the second test, they focused on the fact that the top center is A, and answered "cut vertically" as in Answer 2. The answers of the weak learner ❶ and the weak learner❷ are combined and identified by majority vote (Summary of previous answers 2), but the two identifiers have different opinions on the two in the center. Therefore, these two are incorrect answers (Correctness Check 2).

+ Put aside the weak learner ❶ that answered the first test and study the new weak learner❷ next.
-+At this time, you have them remember to emphasize the problems they got wrong last time. This time, you emphasize that the top center is A.
+ Suppose that in the second test, the weak learner ❷ answers that it cuts vertically as in answer 2.
+ The answers from weak learner ❶ and weak learner❷ are combined by majority vote. (Summary of answers up to now 2)
+ This time there is a disagreement between the two identifiers in the center two. So we will consider these two incorrect (correctness check 2).

- The subjective "feeling of remembering" does not match objective test scores.
+ This is similar to the "not confident but high grades" phenomenon we saw on page 88. The subjective "feeling of remembering" does not match objective test scores.

- I realized that in the past I had made mistakes in the way I created the questions to be written on the cards.
+ I read this sentence and realized that I had made a mistake in the way I made my word cards. The way I made the questions was not appropriate.

- Of the 20 rules, I think the most important is "Rule 4: Stick to the [[Minimum Information Principle]]," which is to make the problem as simple as possible.
+ Of the 20 rules, I think the most important is "Rule 4: Stick to the [[Minimum Information Principle]]. This rule says to keep the problem as simple as possible.

- I would really like to explain it all, but the original text is 22 pages long, so that would be a whole chapter by itself.
+ I would really like to explain all the rules, but the original text is 22 pages long, so that would be a whole chapter by itself.

- The damage is greater if you don't understand and think you do, so let's err on the side of safety.
+ Understanding is a hypothesis. If you think you understand something when you don't, the damage is done. Test your hypothesis quickly.

- The book is not the only material to assemble.
+ Book content is not the only material to construct understanding.

The "Curse of speed reading" became "Curse of speed reading" in the process of English translation, but I'm not sure if I can match the Japanese version. Pending.
→Suffering of speed reading was fixed. Because it is not that the individual suffers from the curse of speed reading, but because of a mistake in personal self-perception.

- This is approximately the speed at which an announcer trained in reading aloud is comfortable listening. It would be a little faster if you read faster without worrying about readability,
+ This is approximately the speed at which a trained announcer reads aloud for ease of listening. It would be a little faster if you read faster without worrying about ease of listening,

Ease of listening, not ease of reading

- First of all, you have a false self-image that you can read at three times the speed you normally read and still retain comprehension. If you actually read at three times the speed, your comprehension will be reduced by one-third.
+ First of all, you have a false self-image that you can read at twice the speed you normally read and still retain comprehension. But if you actually read at twice the speed, your comprehension will be cut in half.

- Before deciding whether or not to read book X by an author, we can first get a sense of the book's place in the historical context.
+ Before deciding whether or not to read a certain book X, you can first get a sense of its place in the context of history.

- Before deciding whether or not to read an author's book X, one can first know the place of that book X in the context of history. For example, philosopher Immanuel Kant's Critique of Pure Reason is a book that marks a significant turning point in the history of Western philosophy, taking a critical stance against the mathematician Gottfried Wilhelm Leibniz's (Leibniz) and others' argument for the correctness of reason on the assumption that God is right  About 100 years later, it led the philosopher Friedrich Wilhelm Nietzsche (Nietzsche) to say "God is dead" in "Pleasant Knowledge" ...... You don't have to read the book at all to know that this is the case. This is the "book I have not read at all" Note 10.
↓
Divided into five paragraphs.

Before deciding whether to read a book X, you can know the position of the book X in the context of history. For example, Philosopher Immanuel Kant wrote "Critique of Pure Reason."

Before the book, a mathematician Gottfried Wilhelm Leibniz argued the correctness of reason on the assumption that God is right. Kant took a critical position against the opinion.

The book is a turning point of the history of the philosophy.

A hundred years later, the philosopher Friedrich Wilhelm Nietzsche said "God is dead" in his book "Amazing Knowledge." Kant triggered Nietzsche to say that.

Even if you do not read these two books, you can know this information. This is the class "A book that you have never read."

- Next, you can ask people about the content. You can ask someone close to you who is familiar with the field, or, in this day and age, you can search for book reviews.
+ Second, you can get information from others who have read the book. You can ask friends who are experts in the field, or in this day and age, you can search the Internet for book reviews.

- It's a more realistic goal setting than stressing yourself out by thinking you have to "read well" more books than you can read!
+ If you think about reading more books than you can read well, the idea creates stress and suffering. Letting go of reading well is a more realistic goal setting.

- Please note that I have read the book I am referring to in this book four times. I read the book at least once in the planning stage to come up with the idea of mentioning the book, read it a second time so that I can figure out which pages have the content I want to mention before writing the manuscript, read it a third time carefully to find the parts I want to mention, and close the book while writing the manuscript because it would become overly detailed if I write the manuscript while reading it, Finally, I read it a fourth time for confirmation. However, if you only read through the book thoroughly, you have only read it 0 to 1 time.
+ I have referred to the contents of many books in this book. If you only call reading through the book thoroughly "reading", then I have read most of the book only once. What exactly is your reading process? I have read a book once in the past, just enough to come up with "I'll mention that book" in the planning stage. Then I read it a second time so that I know which pages I want to mention before writing the manuscript. Just before writing, I read carefully the section I want to mention. This is the third time. I do not look at the book when I am writing the manuscript, as reading the book while writing can lead to excessive detail. Finally, I read the book a fourth time to make sure the content is correct. In other words, if you count a rough reading as one reading, I read the book at least four times.

- How to "find" readings in less than 2 seconds per page
+ How to read a page in 2 seconds to find information

- If this is to be effective, I believe that it will be by giving people who are in the habit of reading at the speed of reading aloud without speaking out loud a chance to break out of the habit by experiencing and training them to read at a faster rate.

- Masatsugu Terada considers the value of reading to be the product of three forces: "the power of the book's author," "your experience," and "your business power." Divided by the time spent reading, this is the return on investment of reading.
Terada Masatsugu thinks that the value of reading is the product of three powers:

- "author's power" x "your experience" x "your business strength"

You spend the time to read books. It is an investment. The efficiency of the investment is the value per time.

- This "your experience" seems to include "your ability to gather information to extract useful information from books," "the experiences you have had," and "your ability to construct models based on your experiences and information gathered from books.

This doesn't have all three types, does it?

"Your experience points" is a metaphor of role-playing games. By collecting the experience points, the ability of the in-game character grows. For reading, there are three ability:

- the ability to collect useful information from books
- the ability to recall your experiences including information you learned before
- the ability to build models based on your experiences and information from books

- I learned that there are similarities between reading source code and reading books, where the focus is on the folder hierarchy and table of contents.
+ I learned that reading source code and reading books have something in common in that they focus on folder hierarchies and tables of contents. Both are hierarchical, location-based organizations of information.

- If you compare the writings of an old person in his/her youth with those of his/her later years, you will find that the content has changed unexpectedly. If this is the case, then it is highly likely that the author of a book released this year will think differently 30 years from now!
+ The philosopher Wittgenstein pointed out a serious error in a book he had written some 25 years later. Since even a smart person like him can make mistakes, the authors of the books released this year will make mistakes too.

- However, new evidence may be discovered that changes the interpretation of the old history, or even the more recent history may be interpreted differently by neighboring countries, causing controversy.

This is more of a science story than a history story.


-4.4.1.2 Books that require external reference
-Whether the reader has the knowledge that the author assumes also has a significant impact on how the book is read.

+ The author does not know what knowledge the reader has. So the author assumes that the reader has some knowledge.
+If the reader does not have the required knowledge, he/she must first refer to an outside book to gain the required knowledge in order to understand the book's content.

- So the author thinks, "This is something that can be easily found by searching the Internet without having to devote paper space to explain it.
+ Even if a piece of knowledge is unknown to the reader, the reader can quickly learn it by searching the Internet. If the author thinks so, the author will not devote paper space to explaining that knowledge.

- The climbing type of book is a type of book that builds up concepts. If you neglect the front part of the book, you will have problems later. The hiking type is a book that describes various concepts one after another.

- Because you don't know the total amount of "what is in the book", you cannot judge on your own whether you have understood 100% of it.
+ Because you don't know the total amount of "what the author wanted to convey in this book," you cannot judge on your own whether you understood 100% of the book.

- In some cases, the value is not in extracting the content of a single book, but in combining the content of the book with the rest of the knowledge.
+ We tend to focus our attention on the information "inside" a book. Often, however, there is value in combining the information inside the book with information outside the book.

- I have listed several purposes for reading, but my best recommendation is to use it for the purpose of creating review material.
+ So far we have introduced three purposes for reading. In this section, we will introduce another purpose. It is to create material for review.

We have reconsidered that we should not say "the best recommendation" when we are trying to present various options and encourage readers to make a choice based on their individual situations.

> I advocated that we should concentrate and create "[[Leverage memo]]".
after
+ Here's the leverage memo I made after reading this book
> 80% of the content of a text is in 20% of the text; take 80% in 20% of the time, leverage notes and discard the original. Read it repeatedly and enrich it further.
Add

- However, by designing memos that had to be enriched or added to when they were read back, memos that I couldn't think of anything in particular to edit accumulated as tasks waiting to be worked on.

+ However, because I defined "to review" as "make it shorter or longer," the review process becomes painful. I made a "to review" list in the service. If a note has nothing to remove or add, it remains in the list. The pile of tasks harms motivation.
+ In hindsight, I should have kept the cost of review as low as possible. Editing is too costly; a review in Anki is one click away. That's why it can be done in short gaps of time.

- You are betting on the possibility that by making it public, you will plant a seed, which will gradually grow as you receive feedback, and over time, your understanding will grow into a large tree.
+ By making it public, you plant a seed, which gradually grows with feedback, and over time, the understanding within you grows into a large tree. Would you like to bet on this possibility?

The subject matter was unclear.

---
This page is auto-translated from [/nishio/英語版作成に伴う推敲(2,3章)](https://scrapbox.io/nishio/英語版作成に伴う推敲(2,3章)) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
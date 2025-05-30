---
title: "Corrected differences for the 4th printing"
---

In the interim between the decision to reprint the fourth edition and the decision to print the fourth edition, we began working on the English version.
I have improved the parts where I felt "the original Japanese was unclear". [[Improvement for English version (~1 chapter)]]. This is only a rough note because the priority at the time of writing this was to create the English version. Since it is not in the form of revised diffs, I will make it in the form of revised diffs for the 4th edition.
Note that there are some items written here that will not be included in the fourth edition due to the publisher's desire not to include corrections that would change the number of pages in a paper book.

iv
diff:0.1.1

```
- I believe that generating new knowledge on one's own is important for high-value intellectual production.
+ For high-value intellectual production, it is important to generate new knowledge oneself.
```


vi
diff:0.2.1

```
- In addition to reading, "sutra copying," a technique of imitating and typing, is also often used.
```

Considering the simplicity of the story, it would be better not to mention the sutra at this stage.

diff:0.2.1

```
- This book also presents a number of intellectual production challenges and solutions. This is like sample programming code.
+ Programming textbook presents challenges and the programs that solve them. This book presents challenges and solutions to intellectual production. The same structure.
```

The concept of "model" is highly abstract, so at this juncture it is better to open it up more concretely to "pattern discovery."
In conjunction, the title of this section, "Abstraction and Modeling" should be changed to "Compare and Find Patterns". (Another idea
: "Abstraction occurs when patterns are discovered.")
The words "information gathering, modeling, and verification" in the text of v should also be "information gathering, abstraction, and verification". The same applies to the figure captions. I was concerned that the word "abstraction" was not easy to grasp, but since the figure depicts that "abstraction" is a concept that specifically includes "modeling and pattern discovery," there should be no problem.

vii
diff:0.2.2

```
- In this book, we hope to help you create your own model of intellectual production by comparing intellectual production techniques.
+ In this book, we hope to help you discover common patterns of intellectual production by comparing several intellectual production techniques.
```


:

```
- Now you have the ability to find a pattern and come up with, "If I want to output "Bye, world!" in Python, why don't I just write it this way?" You now have the ability to come up with "If I want to output "Bye, world!
+ What if I want to output "Bye, world!" in Python? Now that you have found the pattern, you have the ability to come up with an implementation.
```


viii
diff:0.3

```
- Chapter 1, "How to Learn Something New," considers how to learn something for which there is no right answer. It details how to learn through a cycle of learning so that you can apply what you learn to situations rather than memorizing it.
+ Chapter 1 is "How to Learn Something New." Just learning the answers does not mean that you will be able to apply them to your situation. To acquire the ability to apply, you need to go through a three-phase cycle: information gathering, abstraction, and practice. This chapter will explore each phase in detail.
```


ix
diff:0.3

```
- Many people buy too many books and end up with piles of them.
+ Have you bought too many books and left them unread?
```

The problem is not that they are physically piled up, but that they are bought but not read.

diff:0.3

```
- However, I believe that what is a more important question than how. In Chapter 7, "How to Decide What to Learn," we will consider this question.
+ However, I believe that deciding what to learn is more important than devising how to learn. Chapter 7, "How to Decide What to Learn," describes decision-making strategies for deciding what to learn.
```

I made it specific because "think about this question" is vague.

p.3
> - Information gathering is the image of collecting boxes. Here, information is likened to boxes. Information gathering is the process of collecting and arranging many boxes. However, even if you only collect a lot of information, the boxes will not be piled up in a flat line.
>  + Let's compare information to boxes. Information gathering is the process of collecting and arranging many boxes. If you only do a lot of information gathering, the boxes will just line up flat. You will not be able to reach high places.
The metaphor made clear what the problem was with just lining up flat.

p.4
> - For example, the text in a book is abstract information that has been stripped away from the author's specific experiences during the writing process.
> + Consider, for example, the process by which a book is written. Before writing a book, the author has many specific experiences. However, it is not possible to write everything in a book. Most of the specific information is stripped away.
This increase in volume will increase the number of lines, so delete one line from the bottom paragraph.
> - Boxes can collapse while being stacked. Math knowledge is a true square block. On the other hand, blocks in other areas of the field are a bit snug. In mathematics, the blocks are stacked so precisely that you can build very tall towers. You can reach a very high level of abstraction. But in other fields, if you try to stack them in the same way as in mathematics, they collapse. So you have to collect a lot of information and stack it like a pyramid, with many boxes to support it.
> + Math knowledge is a true square block, but blocks in other areas are a bit snooty. True square blocks can be stacked precisely, so you can build very tall towers. So we can reach a high level of abstract knowledge through a series of reliable logical expansions. However, if you pile up snoring boxes in the same way, they will collapse. So you need to collect a lot of information and pile it up like a pyramid, supported by many boxes.

p.5
>  - I'm trying to find out what the difference is and
>  + I'd use a search engine to see what the difference is.
>  I made it specific.

> - I would rewrite the parts of the program that are written in lists to be tuples.
> + Rewriting a list in a program to a tuple or
simplify

> - Even when they repeat experiments to create something and then present it, they don't talk much about the prototypes that didn't work out.
> + Suppose you repeatedly experiment to produce something and eventually succeed. When you present your results, you do not mention all the experiments that did not work.
It doesn't fit on p.5, but there is a margin at the end of p.6, so it looks like you can push one line.

p.6
>  - To what extent is it working as expected and to what extent is it not?
>  + How far does the source code behave as expected? Where does the behavior start to differ from expectations?

>  - After clarifying this question and making numerous corrections, the program will finally work correctly.
>  + After finding the answer to this question and modifying the source code many times, the program finally works correctly.

> - I don't often show this process of trial and error to others, but I do at least many times more trial and error than the success stories I publish, and I think anyone who is trying to answer a question that has no textbook answer is doing so.
> + I have not published all of my trial and error process either. However, I have at least three times as many attempts as I have published success stories. I think anyone who is trying to answer a question that has no textbook answer is doing so.
Decomposition of complex sentences and clarification of criteria

p.6 Figure Caption
Trial and error is difficult to see." → "Trial and error is difficult for others to see."

p.7
>  - You do not get to choose which textbooks you use.
>  + You cannot choose your own textbooks.
>  - You also decide which textbooks you choose.
>  + Choose your own textbooks.

p.8
>  - The questions on the final exam in middle school are designed so that if you follow the "correct method" that you have been taught, you will always get the answer.
>  + The questions on the final exam in middle school are designed to be solved. If you correctly follow the method your teacher taught you, you will get the answer.

p.9
>  - Suppose you are a working adult and now you are thinking, "I should learn that.
>  +Suppose you are a working adult and there is something you think you should learn now.

p.10
>  - The same is true of learning a programming language; it is unclear how far along you have to go to feel that you have "mastered" it.
>  + The same goes for learning a programming language. You don't know how much you need to learn to feel that you have "mastered the language".

>  - Also, that goal should be as close as possible. It is reckless to try a full 42-kilometer marathon from the start. It is important to start with a shorter distance and feel the joy of reaching the finish line and the sense of accomplishment as soon as possible. This is utilized in the "tutorial" often used in games.
>  + Also, that goal should be as close as possible. For example, it is reckless to try a full 42-kilometer marathon from the start. It is important to start with a shorter distance and feel the joy of reaching the finish line. To stay motivated, it is important to feel a sense of accomplishment quickly. This is utilized in "tutorials," which are often used in games.

p.12
> - Also, some people have the misconception that going to college will teach them secret knowledge that they cannot get anywhere else, but that is not what college is about.
>  + Some people have the misconception that going to college will teach them secret knowledge that they cannot get anywhere else. However, college is not a place where secrets are given away.

>  - Universities that are proactive in accepting working graduate students have adopted systems that make it easier for working people to learn, such as holding classes on weekends and weekday evenings.
>  + Some universities are proactive in accepting working graduate students. Those universities have adopted a system that makes it easier for working people to learn, such as holding classes on weekends and weekday evenings!

The section title, "Should I Reenter College?" and the phrase "re-enter college" on p. 12 and 13, "enter" is appropriate, not "re-enter".

p.14
>  - These cost reductions have made it harder to function as an indicator of quality, as projects that would not have passed muster in the past have now become possible to pass. In this day and age, it can no longer be said that a book is good because it is a paper book.
>  + These cost savings have led publishers to accept more and more publishing projects. In this day and age, paper books no longer serve as an indicator of quality.

p.15
>  - A bestseller is a book that many people have bought. You might think this would be social proof too.
>  + Bestsellers are books that many people have bought. You might think this is another indicator of quality.
Since you have not explained the term "[[social proof]]."

p.15
> - Now, let's delve into each of the three processes of learning: information gathering, modeling, and validation. First, let's talk about information gathering.
>  Now let's delve into each of the three phases of the learning cycle. In this section we will first delve into information gathering.

p.16
> - If you view "information gathering" as vague, it is hard to know where to start. The conditions for accomplishment are unclear. So, let's first divide it into smaller units and aim to run to a near goal. So let's consider how to divide "information gathering" into smaller units.
> +If you view "information gathering" as vague, it is hard to know what exactly you need to do. The task of information gathering has unclear conditions for accomplishment. So, let's first divide it into smaller units to make the goal closer and clearer. Here are three ways to divide information gathering.

>  - Especially in situations where there is something specific you want to create is an opportunity.
>  + If you have something specific in mind that you want to make, here's your chance.

p.18
>  - The key to motivation is not to aim for such a distant goal, but to aim for a closer "what I want to do now".
>  + Don't aim for such distant goals. Aim for a near goal such as "what I want to do now. That's the key to increasing your motivation.

> - I hope you could sense the similarities among the three.
> + I hope you have sensed a common pattern among the three.
The "point" is ambiguous. It would be better to read "pattern" explicitly, since we have been talking up to that point about the importance of finding common patterns from multiple examples.

p.19
> - So you need a goal that is a good distance away for you. This requires you to decide what goals are appropriate for you, not what others are setting for you.
>  + You need a goal that is not too far away that you can reach. Other people's goals are irrelevant. You need to decide on a goal that is appropriate for you.

> - For example, let's say someone who is just starting to learn a programming language wants to make an awesome game as a goal. This is a good future direction, but do you know how to achieve it?
> + Let's say, for example, you are about to learn a programming language. And let's say your goal is to create an awesome game. Aiming for an awesome game is not a bad long-term direction. But how would you know now how to achieve it?

>  - Trying to know everything in detail from the beginning is bad goal setting.
>  + Trying to know everything in detail is bad goal setting.

> - This is just like trying to figure out the layout of all the stores in the world from the beginning is an absurd goal setting. You can start with a rough map and gradually become more detailed.
>  + It is a foolhardy goal to figure out the placement of items in every store in the world. It is the same thing. You can start with a rough map of where all the stores are located and gradually become more and more familiar with them.

The revisions on p.19 are generally stretched, but there is no room on the front and back pages or on p.19 itself. It may be necessary to remove some detail.

p.20
> - In addition, with the advent of web services Note 1 that allow users to post issues they wish to solve and other users to post their solutions, a search for a specific programming issue has a fairly high probability of finding a solution.
>  + Another question-and-answer service has emerged. This is a web service that allows users to post issues they wish to solve and other users to post their solutions. With the advent of this service, a search for a specific programming issue has a high probability of finding a solution.

> - New means of gathering information, such as "search in English and visit question-and-answer websites," have also emerged.
> + Question and answer sites are a new source of information, different from books. A new way to gather information has been created.

> - In the days of paper books, the ability to see the big picture and think "it should be somewhere around here" was very important.
> +In the days of paper books, it was very important to get the big picture. Search costs were high and it was necessary to narrow down where the information you wanted was located.

> - The misconception is that the goal you reach after studying a lot is to "get the big picture".
> + It is a misconception that after a lot of study you can finally get the big picture.

- I drew [[Diagram of the three methods of information collection]], but I doubt it will be included in the 4th edition.

p.21 Footnotes
> - The specificity of the objectives is the same as in the previous section of this chapter.
>  + The concretization of the objective is the same as the "Prerequisite for learning from where you want to know: the goal has been clarified" described in the previous section of this chapter.
Be specific about "content."

p.23
> - Instead of the unclear and distant goal of "understanding the paper in detail," you created a clear goal by dividing the time and tried to get the general structure in your head.
>  + Instead of the unclear and distant goal of "understanding the paper in detail," you created a near and clear goal by dividing your time and focusing only on the broad structure.
I was trying to get the rough structure in my head instead of the goal, because it sounds like you were trying to get the goal in your head."

p.23
>  - On the other hand, when you are trying to discuss something, you must know where to find the article to which you should refer and be able to read there.
>  + On the other hand, when you try to discuss something, you need to refer to an article. So you have to know where the article is located.

> - The difference is that it is drawn in a tree-like format so that the hierarchy above and below can be quickly found, and it is on one large sheet of paper so that the whole can be viewed without turning the page.
> + The difference is the form of the information. Information will be drawn in a tree-like format so that you can quickly find the hierarchy above and below. It will also be on one large sheet of paper so that the entire page can be viewed without turning the page.

> - During class, when referring to a particular article, we look at this map many times to see "where" the article is located. For example, Article 570, "Seller's Liability for Defects," is in Part 3, "Claims," in Chapter 2, "Contracts," in Section 3, "Sales and Purchase," and so on. Every time you mention an article, it is in Part 3, Claims, Chapter 2, Contracts, Section 3, Purchase and Sale, Article 570: ...... and you will see the information in the higher levels over and over again, so it will naturally enter your mind. I found that tracing the map back to the root each time was a useful way to systematically store a vast amount of information in my brain.
>  + During class, when referring to a particular article, look at this map to see where that article is located, and vocalize it in order, starting at the top level. For example, Article 570 "Seller's Liability for Defects" is located in Part 3, "Claims," in Chapter 2, "Contracts," in Section 3, "Purchase and Sale. Therefore, it is vocalized as "Part 3 Claims, Chapter 2 Contracts, Section 3 Sales and Purchase, Article 570 Seller's Liability for Defects.
>  + This activity will cause the information in the upper levels of the tree to be seen many times. The closer the information is to the root of the tree, the more frequently it appears. Therefore, we memorize it naturally. Tracing back from the root each time is a useful way to systematically store a vast amount of information in the brain.
I made it more specific.

p.25
> - If you can't gather information in broad strokes, you have to do it from one end of the spectrum to the other. If you are unable to get a general overview of the situation, you lack the material to construct an understanding. If you can't get an image in your mind after reading a general description, then you lack the knowledge to form an image in the first place.
>  It is common for people to step back and think, "What is the most efficient way to learn? However, at first we do not even have the materials to determine "what is efficient to learn from". So we need to get the materials first, without stepping on toes there.

> +If you can't gather information in broad strokes, you have to do it from one end. Sometimes you read the table of contents in an attempt to get a general overview, but you still don't know what you're looking for. This phenomenon often occurs when learning something new. This is caused by not having enough material to construct an understanding. Often, the words in the table of contents are already an abstraction. If you do not have the knowledge that can support the concepts in that abstraction, then reading the table of contents will not help you understand it.
>  We often think about what is the most efficient way to learn. However, it is a waste of time to try to figure that out when we do not even have the materials to determine what would be efficient to learn from. We need to get the materials first.
Discussion of this correction: [[Not enough material to construct an understanding.]]

p.27  [[Sutra is an auxiliary wheel]]
> Suppose you can copy, say, 5 pages in 25 minutes. 〜You can stop copying when you think you don't need it anymore.
Overall reconfiguration

- Suppose you can copy, say, 5 pages in 25 minutes. If the textbook is 300 pages, the estimate is that it would take 25 hours to copy the entire book. Looking at this estimate, you may be discouraged, thinking, "I have to spend 25 hours. But that is a mistake.
- Scripture is not the objective. The goal is for you to be able to understand the textbook. The sutra is like an auxiliary wheel until you can ride a bicycle. When you read a book and have no understanding of it, it is the same as when you ride a bicycle and keep falling over and not moving forward. By putting on an auxiliary wheel, you will be able to move forward. And as they ride with the wheels, they improve their riding skills and become able to ride without the wheels.
- If you look vaguely at a book you read but do not understand, you will not feel that you have gained anything. On the other hand, if you do sutra copying, your writing will remain in a form. This is easier to maintain your motivation. This is the effect of having a clear goal. And it is easier to stay motivated if your goal is not 25 hours from now, but 25 minutes from now. This is the effect of making the goal closer, as we learned in "Tutorials Make the Goal Closer" (page 10)
- As you learn more and more efficiently, you will feel less and less need for sutra copying. You will realize why I compared sutra chanting to an auxiliary wheel. You can remove the auxiliary wheels when you feel that you no longer need them. In other words, you can stop sutra chanting when you feel that you no longer need to do it.

p.31
> - When a programmer has a problem with a program, he or she may guess correctly that the problem might be in this area of processing before looking at the actual source code. How is this possible?
>  + A good programmer can sometimes predict the cause of a problem in a program without ever looking at the source code. How is this possible?

p.31 This section is in one undivided chunk, but it would be easier to understand if it were divided with subheadings as in the next module section.
- Models & Models
        - Using Models for [Saving Thought
        - > Models are simplified representations to explain how the real world works. Since the phenomena occurring in the real world are complex, we simplify them by trimming away the unimportant parts so that even limited human cognitive abilities can handle them. For example, in high school physics, air resistance and friction are assumed to be non-existent. The air resistance and friction that exist in the real world are ignored to simplify the problem so that high school students can handle it.
        - >  Since the model is an excerpt of reality, it does not perfectly match reality. This is what is referred to as "all models are wrong" Note 31.
    - Models allow low-cost experimentation.
        - > The value of a model is not how well it matches reality. It is how much less expensive it is to manipulate the model compared to directly manipulating realityNote 32.
        - >  In particular, a model expressed in the form of a mathematical formula is called a "mathematical model. When a model is created in the form of a mathematical equation or program, it is easier to conduct experiments. This is because there is no need for physical experimental equipment.
        - >  When a programmer has a problem with a program, he or she can predict the problem and guess correctly before looking at the actual source code. How is this possible? He has a model of the program in his brain, and he can experiment in his brain to see what phenomena occur when he breaks various parts of that model. He then picks out the phenomena that occur as a result of the breakage that are similar to the actual observed facts.

p.39
> - For new insights, we need to compare "similar" things that are neither "the same" nor "different", but partly the same and partly different.
>  +To discover new patterns, we need to compare things that are neither "the same" nor "different", but rather "similar" to each other, partly the same and partly different.
Although the word "awareness" is undefined, the closest existing term is "pattern discovery," so we have chosen to use that.

p.40
>  - Parables are often used to convey abstractions.
>  + Parables are often used to convey abstract concepts.
I made it specific because "thing" is ambiguous as to what it means.

I drew figures for some of the sections, but probably won't be able to include them in the 4th edition. [[Figure 2019-01-23.]]

p.41
>  - It is easy to get caught up in finding commonalities, but it is also easy to simply gather information, saying "this is similar, this is similar". After some familiarity, it is easier to focus on differences and think about seemingly contradictory things.
>  + It is easy to find commonalities, but it is also easy to simply gather information, saying "this is similar, this is similar". Focusing on differences and thinking about seemingly contradictory things can easily lead to more abstraction.

p.43
>  - You might think that you don't have to discover the patterns yourself, you can just read a book that describes the patterns. This seems reasonable at first glance, but in reality, I think people often feel that it doesn't ring a bell, or that it is too abstract to understand.
>  + You might think that you can learn a pattern by reading a book with patterns in it, without having to discover the pattern yourself. However, when you actually read a pattern book, it often seems abstract and difficult. Even if you read a pattern book, you may not be able to learn a pattern.
Clarified since "good" is ambiguous.

p.43 Footnotes
> - A similar concept is expressed by saying that giving a hungry person a fish will only keep him hungry for a day, so instead of giving him a fish, teach him how to fish.
>  + A similar analogy is that if you give a hungry man a fish, he will only go hungry for a day, so instead of giving him a fish, you should teach him how to fish.

p.44
> - On the other hand, explaining "why it is similar" in your own words, changing it to another example, or applying it when you realize that the problem you want to solve is solved by public-key cryptography is not possible for someone who does not understand public-key cryptography.
>  + On the other hand, if you don't understand public key cryptography, you can't explain in your own words how it resembles a padlock. You cannot change it to another example. You cannot realize that the problem you want to solve is solved by public key cryptography. You cannot apply your knowledge.

> - It often happens that we assume we understand something when we really don't. It is important to verify our understanding in order to recognize the error and proceed with our learning.
>  + We often make the mistake of understanding. We feel that we understand a concept when we really do not understand it. It is important to recognize this misunderstanding and examine our understanding in order to improve our understanding.
Clarification of what is meant by "mistakes" and "advancing learning."

> - Just because you feel like you know something doesn't guarantee that you really do. You have to verify that the model in your brain that you think is correct is really correct by actually using that brain model and observing the results.
>  + Feeling like you understand something is no guarantee that you really understand it. The feeling of understanding occurs when a provisional model is created in your brain. You need to verify that the model is correct. Verification is done by actually using that model and observing the results.

p.45
>  -Programming is an area of learning that is very easy to verify.... Let's compare it to making a chair with woodworking, which is similar in terms of making things... Let's compare it to drawing a picture...
>  + Programming is a relatively easy area to verify understanding... Let's compare it to other areas of understanding. Woodworking is similar to programming in that it is also about making things... Let's compare it with another area of understanding. Drawing is also manufacturing...

Woodworking paragraphs
> Compare this to other areas of understanding. Woodworking is similar to programming in that it is also manufacturing. For example, let's say you are making a chair in woodworking and after cutting the wood, you realize that it doesn't fit together properly. You investigate why it doesn't come together and find that you accidentally cut the wood shorter than the required length. The wood is no longer usable, so you have to start over by cutting a new piece. Compared to woodworking, programming is very inexpensive because it uses digital data for manufacturing, so the cost of trial and error is very low.

p.48
> - It is an intuitive discovery from actual data and direct experience that says, "Oh, there seems to be a pattern like this.
>  + It is an intuitive discovery that "Oh, there seems to be a pattern like this" as you observe specific information.
Since we are here explaining the correspondence between Einstein's ideas and this book, it is better to give the terms of this book and not Einstein's terms to correspond.

> - In "Make and Verify" (* page), we talked about making something based on an understanding and verifying the correctness of the understanding by seeing if it works as expected. The understanding corresponds to axiom A, and based on that understanding, a concrete claim S is made, "If I build it like this, it should work like this," and then it is verified by comparing it directly with experience E to see if it actually works as it should.
>  + In "Verify by Making" (* page), we talked about verifying your understanding by making a program. Your understanding corresponds to Axiom A. You create a concrete program based on your understanding. This corresponds to the concrete claim S. You then observe whether this program behaves as you expect. The concrete behavior of the program corresponds directly to your experience E, and you verify it by comparing it to it.

> - Einstein thought that step 4 also belongs to intuition, because the relationship between the concepts that appear in S and direct experience is not logical, for example, there is no basis for mapping the word dog to what we directly experience when we see a dog. I guess this is related to the "all models are wrong" story, that since models are different from direct experience, we cannot logically say whether a newly observed direct experience corresponds to a particular model or not.
>  + Einstein considered step 4 to also belong to intuition, because the relationship between the concepts that appear in S and our direct experience is not logical. For example, the mapping between the word dog and what we directly experience when we see a dog has no logical basis. This idea is a related story to "all models are wrong. Since models are different from the real world phenomena themselves, the interpretation of a newly observed phenomenon by a particular model is not a logical decision, but a subjective human choice.

p.50
> - For example, a good cook can wash the cutting board used to cut the ingredients while waiting for the pot to heat up and the ingredients to cook, or prepare a plate to serve the cooked food. But someone just starting to learn to cook cannot do that. Those who are good at it know how long to wait for the food to cook and how long it takes to wash the cutting board. So they can make the decision, "I can wash the cutting board during the time it takes to wait for the fire to come on. Those who are just beginning to learn cannot make this judgment, so they cannot process in parallel.
>  + For example, a good cook can perform multiple cooking tasks simultaneously. While heating an ingredient, they can wash the cutting board used to cut the ingredient, or prepare a plate to serve the heated ingredient. But someone who is just beginning to learn to cook cannot do so. Those who are good at it know how long it takes to heat the ingredients and how long it takes to wash the cutting board. So they can determine that they can wash the cutting board while they are waiting for the ingredients to heat up. A person who is just beginning to learn does not know how long it takes and cannot make this judgment. So they cannot do parallel processing.

> - Even when it appears that you are working on multiple tasks in parallel, you are still doing one task at a time, switching between them as you go. Running multiple tasks in parallel means that you have the additional task of "making the decision to switch between tasks". If you are trying to do multiple tasks and feeling unmotivated or confused, first narrow it down to one thing to do and get it done one at a time.
>  + Even when it seems like we are working on multiple tasks in parallel, we are only doing one task at a given moment. We are switching between tasks quickly. This switching cost is not zero. Performing multiple tasks in parallel means that we have the additional task of "task-switching decision-making". The cost of this switching task is low for those who are used to it and high for those who are unfamiliar with it. If you are trying to do multiple tasks and feeling unmotivated or confused, focus on one first and get them done one at a time.

p.53
> - And one of the most common pieces of advice for people whose rooms are cluttered is "just get rid of everything.
> + One common piece of advice for people with cluttered rooms is "just get rid of everything," but it often doesn't work.
The structure is to give a bad example and then a good example, but the good example is on the next page, so it is hard to understand the structure, so I'll nail it down first.

p.54
> - Since cleaning up "entire rooms" is expensive
> + Since cleaning up an "entire room" takes so much time.
The cost in this case is time cost, so I specified it clearly.

p.55
>  - In these situations, we often try to prioritize tasks.
>  + In these cases, we are often advised to prioritize tasks.

> - Sorting Computational Complexity
> + The difficulty of lining things up.
Although the idea comes from the computational complexity of sorting, the heading "computational complexity of sorting" is not appropriate for readers who do not know it.

p.56
> - In fact, many of us have probably experienced spending more than 3 seconds thinking, "Which should I do first?
> + In practice, you will often spend more than 3 seconds wondering which task to prioritize.

> - There is a naive definition of magnitude for values in one dimension, and many people agree on it, so there is less discrepancy.
>  + There is a naive definition of magnitude for values in one dimension, and many people agree on it, so there is less disagreement about magnitude. Which do you think is bigger, 2 or 5? 5, of course.
Added object of "discrepancy." Added example.

p.57
> - If we consider x and y equally important and compare them by x + y, then C is the most important. if x is twice as important as y, then 5 * 2 + 2 == 4 * 2 + 4, so B and C are of equal importance.
> + If we consider x and y equally important, then we compare by the magnitude of x + y, so C is the most important. if we consider x twice as important as y, then we compare by x * 2 + y, so C is the most important. Then 5 * 2 + 2 == 4 * 2 + 4, so B and C have the same importance.

> - Discussing in advance prevents time from being spent discussing what should be prioritized in a situation where time is short and tasks have to be discarded.
> + Often a situation arises where there is not enough time to perform all tasks and you have to choose which tasks to perform. By discussing this in advance, you can avoid spending time discussing which task should be prioritized in this time-poor situation.
The "what" was unclear, so it was made more specific. The situation was also clarified.

> - Is that really the right thing to do?
>  + Is it really the right thing to do? Are your pre-defined priorities correct?
Clarified what is being questioned.

before
> This discussion assumes that the importance of tasks is independent, but in real software development, there are complex dependencies such as "doing task D will increase x in task A" or "doing task E will lower the implementation cost of task B" or "it is cheaper for one person to implement tasks F and G together than to implement them separately. Tasks F and G are complexly intertwined with dependencies, such as "the cost of implementation is lower if one person implements tasks F and G together rather than separately.
after
> This argument assumes that task importance is independent. However, this is not the case in real software development. For example, the following phenomena occur
- If you do task D, you increase x in task A.
- Doing Task E lowers the cost of implementing Task B.
- Tasks F and G are easier for one person to implement together than separately.
>  Real world tasks are interdependent and complex.
Bullet points are better than sentences.

p.58
> - In fact, when we asked some people, they responded that they would try it a few times and choose the best one.
> + I actually asked several people and they replied that they would try each slot machine several times and choose the one with the best results.

> - I also added "don't play slots" as an option and ran a simulation experiment with 600 agents playing 1,000 times.
> + I ran a simulation experiment in which 600 agents made 1,000 decisions in an environment with 3 slot machines. The decisions were made by each agent choosing one of four options: one of the three slot machines or "don't play".

> - Each agent was made to work with an algorithm that would first play each slot 3 times, and then choose the option with the highest expected value based on past experience. We prepared a "value slot machine" in which some slots have a 0.3 probability of winning. Of course, each agent does not know this. Can the agents find the best value slot machine through trial and error?
> + Each agent will first play each slot machine three times. Then, after that, they choose the option with the highest expected value based on their own past experience. We have prepared a slot machine that has a 0.3 probability of winning 500 yen. The expected value of this slot machine is 150 yen; putting 100 yen into this slot machine is a good deal, so the optimal solution is to keep playing this slot. Of course, each agent does not know that such a slot machine exists, nor does he or she know which one it is. Will the agents discover through their experience the slot machine that offers the best value for their money?

> - The results of the experiment showed that the majority 57% of agents were unaware of the value-for-money option and chose "do not play slots".
> + The results of the experiment showed that the majority of agents did not find the best slot machine. The majority of them chose "do not play slots".
Overall, 66% of the agents could not find the best slot machine, and 57% of all agents chose "do not play slots". The detailed numbers are unimportant and have been trimmed.

p.59
>  - This problem is called the "exploitation exploitation tradeoff" in the field of reinforcement learning. If you only do what you "think is best based on past experience," you will never find better behavior. That is not enough exploration. On the other hand, if you only take "inexperienced actions" and think "there might be something better out there! and "inexperienced actions" all the time, you will not be able to take advantage of past experiences. That is lack of utilization.
>  +This problem is called the "exploration-exploitation tradeoff" (exploration-exploitation tradeoff) in the field of reinforcement learning. If you only choose the option that you think is best based on past experience, you will not be able to find a better option. That is not enough exploration.
>  +On the other hand, if you have been looking for better options and choosing only options you have no experience with, you will not be able to take advantage of your past experience. It is underutilized.
I opened it because I don't think you get the message, even though "action" is a reinforcement learning term that means something close to "making a choice."

p.61
> For example, in the UCB1 algorithm often used in computerized Go and Shogi,
Maybe you should add the heading "UCB1 Algorithm" in the front here.

> - For example, the UCB1 algorithm, commonly used in computerized Go and Shogi, adds a term that positively evaluates uncertainty before comparing alternatives.
> + The UCB1 algorithm is a common algorithm used in computerized Go and Shogi thinking engines. This algorithm provides hints on how to deal with uncertain situations....
Explain first why we are talking about UCB1.

> - The wide confidence interval for A means that it may be much larger or much smaller than the average to this point.
>  + A has a wider confidence interval than B. This is because of the higher uncertainty in A. The advantage of doing A is that it may be much larger or much smaller than the average to this point in time.

>  - If we take this idea back to management, we are not judging by what we get on average by doing the task, but by what we get in the best case.
>  + To take this idea back to task management, let's decide whether or not to do a task based on what we will get out of it in the best case, rather than what we will get out of it on average.

p.61
before
>  Cohn then insisted that we implement features with high monetary value and high risk first, then features with high monetary value and low risk, and finally features with low monetary value and low risk, but do not implement features with low monetary value and high risk.
after
> And Cohn argued that
- Implement features with high monetary value and high risk first.
- Next, implement features with high monetary value and low risk.
- Finally, implement features with low monetary value and low risk.
- Don't implement features with low monetary value and high risk.

p.63
>  - In "Build the Base First" (* page), I put the "tasks that must be done today" first, but is this really correct? Are all of those "tasks that must be done today" really "urgent and important"? We need to rethink this and say No to the unimportant ones.
>  + In the "Build a base first" (* page), the first priority was the "tasks that must be done today". If you are busy every day, you need to question whether those "tasks that must be done today" are really all that important. Find the unimportant ones and make time to say no to them.
Is that correct?" was not clear what it was questioning, so it was clarified. The last phrase, "It is necessary," was also clarified since it was not clear what it was necessary for.

p.64
> - "Urgent" and "recently notified" are often confused.
>  + We often confuse "recently notified" with "urgent".

> - If you don't write down your tasks, you might throw out the work you were doing and start on it because of the anxiety that if you don't do it right away, you might forget about it.
>  + If you don't write down the task, you feel anxious that you might forget the task you were notified about. This anxiety creates a sense of urgency to get that task done right away. You may end up throwing away the important but non-urgent task you were working on and start working on the notified task.

> - Instead, let's consider whether it is possible to stop ❸.
>  + Stop ❸ tasks that are not so important to you.

> - For example, if the incoming task is a request from someone else, there may be room to negotiate whether another ❸ task can be stopped as an exchange for accepting the request.
> + For example, if an incoming task is a request from someone else, you may be able to negotiate to stop another ❸ task as an exchange for accepting the request.
Specifically, if one person says, "Do A," and then says, "Do B," you ask, "Which has priority, A or B?" and let them decide the order of priority, the one who is not prioritized will in effect have made the decision not to do it now.

> - Covey said that what matters depends on your mission and values. However, if you have not verbalized your mission and values, you will not know what to base your decision on. How do you verbalize your values?
> + Covey said that what matters depends on your mission and values. In order to think with words, your mission must have a handle on it: words. How do you verbalize your mission?
Because the problem is not that "I don't know what to base the importance on," but that without a handle on the concept, we can't manipulate it.

The second sentence has changed in the third edition, but it looks good because it replaces the first sentence with after. However, there are indications that it may not fit on the paper, so it needs to be discussed later. The following is also discussed

> - However, many people may not be able to verbalize their ideas even if they are asked to clarify them. Even if you make a decision in such a state, it may not lead to a good decision in your daily activities.
>  + However, many people have not yet been able to speak about their mission in their own words. Even if they decide in haste and at random in that state, those words do not connect well with their day-to-day activities.
Vague on "decide appropriately."

> - Life goals are the top portion of the pyramid. Let's call it [[top-down]] in the sense of coming down from the top, deciding on this first, and then chewing up from there to decide on individual actions. [[Allen]] of [[GTD]] recommended [[bottom-up]], which is the opposite of top-down. 15 In this case, the bottom part is the daily actions.
> + Life goals are the top portion of the pyramid. There are two directions to think about life goals. They are the direction of descent and the direction of ascent. Let's call it [[top down]] in the sense of coming down from the top, where you decide on your life goals first and then bite off from there to determine your daily actions. [[Allen]] of [[GTD]], on the contrary, recommended [[bottom-up]], coming up from the bottom.
>  Observe your daily activities and discover after the fact common patterns from them: the information gathering and pattern discovery you learned in Chapter 1. It is through the abstraction of this pattern discovery that we eventually verbalize our life goals.
The relationship with Chapter 1 was clearly stated.

p.67
>  - Is the task too large?
>  + Tasks are too big. The goal is too far away to motivate. (Footnote: See also: p.10 "Tutorials make the goal closer.")

> -- The task is too big and the goal is too far away, or the task seems vaguely large due to lack of estimation of the size of the task, which makes it seem too big.
> + (combined with previous paragraph) They feel the task is so large because they can't estimate the size of the task, and that undermines their motivation.

> - The intellectual production task I am working on right now, "writing a book", is also a task that is too big to estimate the time involved.
>  + I am working on the intellectual production task of "writing a book" right now. This task is also too big to estimate time.

> - In this kind of large task state, many people cannot write, so it is common to divide the task into "set a deadline for each chapter".
> + If you view the entire book writing process as one big task, it can be difficult to stay motivated. Therefore, it is common practice to divide the task into sections and set deadlines for each chapter.

footnote
> - The population here is precisely the 52% of those who said they would not finish in 4 hours who were able to answer what they would do in the first 25 minutes, removing the 58% who were motivated by being told they should do it.
Breaking it down into bullet points would be as follows, but it would be difficult to include this in the footnotes.
>  Precisely, the denominator is A-C below.
>  A: Respondents who answered that they would not finish within 4 hours
>  B: 52% of A: those who could answer what they would do in the first 25 minutes
>  C: 58% of B: Those who were motivated by being told to do it

p.68
before
> To motivate myself for this big task, I divide the big task of "writing a book" into three phases: writing down ideas and making fusen, rearranging the fusen and thinking about the structure, and drafting the manuscript based on the structure.
after
>  To motivate this large task, I have broken the task down into the following three phases.
- Write down ideas and make a fusen
- Rearrange the fusen and think about the structure.
- Create a manuscript based on the composition

> - It has long been believed that there is a limit to how long a person can sustain concentration. For example, Tadatsugu Kobayashi argues that the maximum amount of time a person can sustain concentration is two hours, so if the breakdown of work results in tasks that take more than two hours to complete, the tasks need to be further broken down to clarify each goal, He argues that
> + It is believed that there is a limit to how long humans can sustain concentration. For example, Tadatsugu Kobayashi argues that human concentration can last up to two hours, and if a task takes longer than two hours, it is necessary to break it down into smaller tasks and clarify the goal of each task.

p.69
2.3.2.1 Limitations of Concentration In terms of volume in "Imagine hiking on a mountain trail." It would be better to have a subheading before the It could be something like "A metaphor for hiking."

p.70
>  - Time, which is often viewed as continuous, is cut into pieces of a fixed length and named "pomodoro," and the size of the task is estimated by the "number" of pieces.
>  + "Time" is often seen as continuous. We cut it into pieces of a fixed length and name them "pomodoro". This allows us to estimate the size of the task in terms of the "number" of pomodoros.

itemization
- Make a list of tasks for the day
- Estimate the size of the task in terms of the number of pomodoros
- + 1 pomodoro (25 minutes) timer starts at the beginning of the task
- Focus on one thing without changing tasks during one pomodoro
- If interruptions by you or others occur, record them
- 1When you are able to continue in a pomodoro focused state, switch perspectives by standing up and taking a few steps, etc. Note 21
It was too obvious to me and I had left out the most important part for people with no experience.

> -Staffan recommends shortening the length to 10 or 15 minutes for those who cannot concentrate for 25 minutes.
> + Note 20 Some people mistakenly think that 25 minutes has some profound meaning, but length has no meaning. If you cannot concentrate for 25 minutes, I suggest you try shortening it to 5 or 10 minutes.
Stop being indirect and be direct. Shorter time.

Note 21
> - If the Pomodoro timer had not gone off, I might have continued to work in a bad way without realizing a better way, with a narrow perspective that kept my viewpoint close to the problem.
>  + If I had not used the Pomodoro timer I would have continued to work in a bad way without realizing a better way. Concentration brings your perspective closer to the problem and narrows your view.

p.71
> - To estimate how many pomodoros each task can be done in, first estimate the amount of tasks that can be done in one pomodoro, and then train yourself by actually doing them and observing the discrepancies. Gradually, the accuracy of estimation improves.
>  + To be able to estimate how many pomodoros each task can be done in, you first need to know how many tasks you can do in one pomodoro. Gradually, your estimation accuracy will improve as you accumulate the experience of completing tasks that you thought could be completed in one pomodoro but were not, or, on the contrary, were completed quickly.

>  - Note 22 This is much like experimenting to verify understanding.
>  + Note 22 Observing the gap between estimated and actual time taken is much like an experiment to verify understanding. In an experiment, one observes the gap between expected and actual results.
This" is unclear, and "similar" is unclear as to how they are similar.

p.73
> - Since then, I have decided to start a 25 minute Pomodoro timer when replying to emails that might take a while.
>  + Since then, I have decided to start a 25 minute Pomodoro timer when replying to emails that might take a while. Even if I don't think it will take long, I've decided to start a 5 minute timer. This is because my estimates can be wrong.
If you don't write the second half, your explanation is one-sided.

p.74
> - Not "do it because it's a job" or "do it because it's a plan", but "let's measure first".
>  + We don't use time because it's work, or because it's a plan, but first we try to measure and clarify how we are using our time. This is a common concept in the Pomodoro Technique and Task Shooting.
I clarified why I am referring to Drucker here. I've been writing about these similarities with the feeling that "I've written about them a few pages back, so you don't need to specify," but I've reconsidered that I should specify because they are actually missing from my short-term memory in use cases of "reading an open page" or "reading little by little".

> - "When you want to speed up a program, you should first measure (profile) in detail where it is slow."
>  + "When you want to speed up a program, you should first measure (profile) in detail which code is taking time."
Clarified "where is slow."

p.76
> - It depends on whether what is gained by one cycle is accumulated or not.
> + It depends on whether the knowledge gained by one cycle is accumulated.
Clarification of "stuff"

p.78
> - Specifically, we injected drugs into the hippocampus that block NDMA receptors in the hippocampus.
> + To disrupt hippocampal function, specifically, drugs were injected into the hippocampus that block NDMA receptors in the hippocampus.

p.79
> - I guess normal rats use the information of "landmark visibility" that they can directly observe to create a memory of "scaffold location" that they cannot directly observe. Therefore, they can quickly reach the scaffold even if they start from a different location. On the other hand, rats with a broken hippocampus may have memorized the specific steps of how they swam to the scaffold after being dropped into the water. So, when they started at a different location, they looked around for the scaffold just as if they had not learned anything.
> + In Morris' water maze experiment, rats cannot directly observe the location of the scaffold, only the surrounding landmarks. Normal rats probably create a memory of the location of the scaffolds that they cannot observe directly, based on how they see the landmarks that they can observe directly. So they can quickly reach the scaffold even if they start from a different location.
> + On the other hand, a rat with a broken hippocampus would only remember the specific steps of how it swam to the scaffold after being dropped in the water. This method can still reach the scaffold efficiently if you start from the same place. However, if you start from a different location, you will have to search around for the scaffold as if you had not learned anything.

p.83
> - Repeated learning increases the number of synapses themselves.
>  + Repeated learning increases the number of synapses.

> - In the case of the person whose hippocampus was removed, he could not recall memories up to several years before the surgery, but he could recall his childhood memories without difficulty in speaking.
> + In the case of the person who had his hippocampus removed, he could not recall memories up to a few years before the surgery. However, he had no difficulty in speaking and was also able to recall his childhood memories.

> - And if the same stimulus comes in between the time the memory is gone, another step is taken to create a more lasting memory.
> + And if the same stimulus comes before the memory disappears, another step is taken to create a more lasting memory.

> - Memories are created in stages and stored in a gradual, long-lasting way through repetition.
> + Memories are created incrementally through repetition and are gradually converted into long-lasting memories.

> - If there is one thing that gets progressively stronger with repeated use, it is muscles. Creating a memory is more like training a muscle than keeping a file.
> + What is one thing that gradually gets stronger with repeated use? One example is a muscle. Creating memories is more like training a muscle than keeping a file.

> - The brain has a mechanism that makes it easier to temporarily consolidate memories when we experience strong fears, etc. However, it is not something that can be used as a tool for memory on a daily basis, so I omitted the explanation.
> + The brain strongly consolidates memories when it experiences strong fears and other experiences. However, this mechanism is not something that can be used as a tool for memory on a daily basis, so I omitted the explanation.

p.84
> - Mention
> + Inscription

> - This is a mechanism for ignoring unhelpful stimuli, similar to how reading the same sentence over and over again can become tedious.
> + This is a mechanism to ignore useless information. It is similar to how repeating similar tasks becomes increasingly tedious.
Not related enough to be connected by "ga". Stimulus -> information, is related to the below

> - What does "useful" mean to the brain? It is "being rewarded".
>  + What is "useful" information for the brain? It is "rewarding".
Specify clearly so that it is easy to see that you are writing about the opposite pattern of the paragraph above.

p.58
> - Theta waves, which are generated in the hippocampus when information is input, work to compress time by a factor of about 10.
> + Theta waves are generated in the hippocampus when information is input. These theta waves work to compress time by a factor of about 10.

> - So the process of creating abstract information from concrete information is at work here.
> + So the process of creating abstract information from concrete information is at work in the hippocampus.

p.86
> - The percentage of correct answers increased to 47.4% when the test was taken on the day the textbook was read and a second test was taken 7 days later.
>  + If you take the test on the day you read the text and then take a second test 7 days later, the percentage of correct answers rises to 47.4%.

>  - The fact that the test takes place and the timing is confidential to the subject.
>  + The test is unannounced. Subjects do not know at the time they read the text that they will be tested later.

p.89
> - The correct answer is a "hard problem" that cannot be successfully identified by a weak discriminator alone because of the staircase-like arrangement of A and B.
>  + This is a difficult problem for a single weak discriminator. This is because in the correct answer, A and B are aligned in a staircase-like fashion.

>  - I challenge you to do this.
>  + How can we solve this problem with a weak discriminator?

>  - Set aside the weak learner ❶ that answered the first test and study the new weak learner❷. In the second test, the learner will focus on the fact that A is in the upper center, and will answer "cut vertically" as in Answer 2. The answers of the weak learner ❶ and the weak learner❷ are combined and identified by majority vote (Summary of previous answers 2), but the two identifiers have different opinions on the two in the center. Therefore, these two are incorrect answers (Correctness Check 2).
>
>  + Set aside the weak learner ❶ that answered the first test and study the new weak learner❷ next.
>  +At this point, I ask them to remember to emphasize the problems they got wrong last time. This time, you emphasize that the top center is A.
>  + Suppose that in the second test, the weak learner ❷ answered that it cuts vertically as in answer 2.
>  + Combine the answers from weak learner ❶ and weak learner❷ by majority vote. (Summary of answers up to now 2)
>  + This time there is a disagreement between the two identifiers in the center. So we will consider these two incorrect (correctness check 2).

p.92
> - The subjective "feeling of remembering" does not correspond to objective test scores.
>  + This is similar to the "no confidence but high grades" phenomenon we saw on page 88. The subjective "feeling of remembering" does not match objective test scores.
I should mention this explicitly because you may not realize that it is relevant.

p.94
> - I realized that in the past I had made mistakes in the way I created the questions I wrote on the cards.
>  + I read this sentence and realized that I had made a mistake in the way I made my word cards. The way I made the questions was not appropriate.

> - Of the 20 rules, I think the most important is "Rule 4: Stick to the principle of least information," which is to make the problem as simple as possible.
>  + Of the 20 rules, I think the most important is Rule 4: Stick to the principle of least information. This is the rule that says to keep the problem as simple as possible.
Clarification of "stuff"

footnote
> - I would really like to explain it all, but the original text is 22 pages long, so that would be a whole chapter by itself.
>  + I would really like to explain all the rules, but the original text is 22 pages long, so that would be a whole chapter by itself.

p.98
> - The damage is greater if you don't understand and think you do, so let's err on the side of safety.
>  + Understanding is a hypothesis. If you think you understand something when you don't, the damage is done. Test your hypothesis quickly.

p.107
> - The content of the book is not the only material to assemble
>  + Book content is not the only material to construct understanding
Objective is unclear.

p.109
> - This is approximately the speed at which an announcer trained to read aloud is comfortable listening. If you read faster without worrying about readability, it will be a little faster,
>  + A trained announcer's easy-to-hear oral reading is approximately this speed. If you read fast and don't care about ease of listening, it will be a little faster,
Ease of listening, not ease of reading

p.113
> - First of all, you have a false self-image that you can read at three times the speed you normally read and still retain comprehension. If you actually read at three times the speed, your comprehension will be reduced by one-third.
>  + First of all, you have a false self-image that you can read at twice the speed you normally read and still retain comprehension. But if you actually read at twice the speed, your comprehension will be cut in half.

p.114
> - Before deciding whether to read book X by an author, we can first get a sense of the book's place in the historical context.
>  + Before deciding whether or not to read a certain book X, you can first get a sense of its place in the context of history.

p.115
> - Before deciding whether to read book X by an author, one can first know the place of that book X in the context of history. For example, philosopher Immanuel Kant's Critique of Pure Reason is a book that marks a significant turning point in the history of Western philosophy, taking a critical stance against the mathematician Gottfried Wilhelm Leibniz's (Leibniz) and others' argument for the correctness of reason, which assumed that God is right.  About 100 years later, it led the philosopher Friedrich Wilhelm Nietzsche (Nietzsche) to say "God is dead" in "Pleasant Knowledge" ...... You don't have to read the book at all to know that this is the case. This is the "book I have not read at all" Note 10.
↓
Divided into five sentences.
↓
> + Before deciding whether to read book X by an author, we can first get a sense of the book's place in the context of history. Consider, for example, the Critique of Pure Reason by philosopher Immanuel Kant.
>  + Before this book, mathematician Gottfried Wilhelm Leibniz (Leibniz) and others had argued for the correctness of reason on the assumption that God is right. So Kant took a critical position against this.
>  + That makes this book a significant turning point in the history of philosophy.
>  + About 100 years later, philosopher Friedrich Wilhelm Nietzsche (Nietzsche) said in his "Eternal Knowledge" that "God is dead". Kant's assertion was the catalyst for this statement.
>  + Even if you haven't read this book, you can still find out this information. This is classified as a "book I have not read at all".

> - Next, you can ask people about the content. You can ask someone close to you who is knowledgeable in the field, or in this day and age, you can search and find book reviews.
> + You can also get information from others who have read the book. You can ask friends who are experts in the field, or in this day and age, you can search the Internet for book reviews.

> - It's a more realistic goal setting than stressing yourself out by thinking you have to "read well" more books than you can read!
>  + If you think about reading more books than you can read well, the idea creates stress and suffering. Letting go of reading well is a more realistic goal setting.

footnote
> - Please note that I have read the book I am referring to in this book four times. I read the book at least once so that I can come up with "I will mention that book" in the planning stage, read it a second time so that I can figure out which pages have the content I want to mention before writing the manuscript, read it a third time carefully for the parts I want to mention, and close the book while writing the manuscript because it would become overly detailed if I write the manuscript while reading it, Finally, I read it a fourth time for confirmation. However, if you only read through the book thoroughly, you have only read it 0 to 1 time.
> + I mention many of the books in this book. If you only call reading through the book thoroughly "reading", then I have read most of the book only once. What exactly is your reading process? I have read a book once in the past, just enough to come up with "I'll mention that book" in the planning stage. Then I read it a second time so that I know which pages I want to mention before writing the manuscript. Just before writing, I read carefully the section I want to mention. This is the third time. I do not look at the book when I am writing the manuscript, as reading the book while writing can lead to excessive detail. Finally, I read the book a fourth time to make sure the content is correct. In other words, if you count a rough reading as one reading, I read the book at least four times.

> - How to "find" readings in less than 2 seconds per page
> + How to read a page in 2 seconds to find information
The object would be clearer if it were changed to "The object is clear, but is it difficult because of the length or in relation to other section headings?

p.115
diff:4.3

```
- The rest is divided into "fast reading" above F and "slow reading" below. If we think in terms of a gradation of "find" and "build," the fast reading method focuses on the find side. Since existing fast reading techniques are helpful in learning this finding reading method, we will introduce two fast reading techniques.
+ The rest is divided into "fast reading" above F and "slow reading" below F. Reading has two purposes: finding information and constructing understanding. Fast reading focuses more on finding information. To learn how to find information, existing fast reading techniques are helpful. So, below are two fast reading techniques.
```


p.116
diff:4.3 before

```
[* Level 1 (25 min)]
	Look through the entire book and check the table of contents, chapter headings, and subheadings.
	Look through the entire book again, looking for mark 1 and read only there.
[* Level 2 (+30 min)]
	Look through the entire book again, looking for mark 2 and read only there.
[* Level 3 (+45 to 90 minutes)]
	Look through the entire book again, checking the headings and subheadings, looking for mark 3 and reading only there.
```

diff:4.3 after

```
[* Level 1 (25 min)]
	First, check the table of contents, chapter headings, and subheadings.
	Next, find the paragraph with mark 1 from the entire book and read only that.
[* Level 2 (+30 min)]
	In addition, look for paragraphs with mark 2 throughout the book and read only those.
[* Level 3 (+45 to 90 minutes)]
	Again, checking the headings and subheadings, look for paragraphs with mark 3 and read only those.
```


p.118
> - If this is going to be effective, I think it will be by helping people who are in the habit of reading at the speed of reading aloud without speaking out loud to experience and train themselves to read faster, thereby creating an opportunity to break out of the habit.
> + The main effect of this reading method may be to encourage people who have developed the habit of reading at the speed of reading aloud to break out of the habit by allowing them to experience and train themselves to read faster.

p.121
> - Masatsugu Terada considers the value of reading to be the product of three forces: "the power of the book's author" x "your experience" x "your business power," and dividing this by the time spent reading is the return on investment of reading.
> + Masatsugu Terada considered the value of reading to be the product of three things. The value of reading is the product of three things: the power of the book's author, your experience, and your business ability. You spend time reading. This is an investment to obtain value. The return on investment of reading is the value divided by the time, and it is important to increase the return on investment.

> -The idea is that the value of reading is not determined by the book alone.
>  + The interesting thing about this idea is that the value of reading is not determined by the book alone.

> - It seems to me that this "your experience power" includes "the ability to gather information to extract useful information from books," "the experience you have had," and "the ability to assemble models based on your experience and information gathered from books. Also, "your business ability" seems to include "the ability to gather information from customers," "the ability to assemble a model to understand customer needs based on your experience and information," and "the ability to create something that seems to meet customer needs, show it to customers, and verify their understandingNote 17.
> + If I were to use the words I have used in the previous chapters, I would describe "your experience" as a concept that includes "the ability to gather useful information from books," "the ability to recall experiences and things you have done and learned," and "the ability to construct an understanding based on your experiences and information gathered from books," and "your business skills" as "the ability to gather information from customers and "your ability to understand customer needs based on your experience and information" and "your ability to create something that might satisfy customer needs and to verify your understanding by showing it to customers.

p.125
> - I learned that there are similarities between reading source code and reading books in that they focus on the folder hierarchy and table of contents.
>  + I learned that reading source code and reading books have something in common in that they focus on folder hierarchies and tables of contents. Both are hierarchical, place-based organizations of information.

> - If you compare the writings of an old person in his youth with those of his later years, you may be surprised to find that the content has changed. If this is the case, then the author of a book released this year will most likely think differently 30 years from now!
> + Philosopher Wittgenstein pointed out a serious error in a book he wrote some 25 years later. Since even a smart person like him can make mistakes, the author of a book released this year will also make mistakes.
It had been a footnote, but we thought it would be better to be more specific in the text. The footnote was removed.

> - Universal is Right
> + Universal Correctness

p.127
> - Whether or not the reader has the knowledge that the author assumes also has a significant impact on how the book is read.
> + The author does not know what knowledge the reader has. So the author assumes that the reader has some knowledge. If the reader does not have the assumed knowledge, then in order to understand the content of the book, the reader must first refer to an outside book to obtain the assumed knowledge.

> - I believe that the appearance of informational services raises the level of knowledge expected of readers, as authors think, "This is something I can easily find on the Internet without having to devote paper space to explain it.

> + I believe that the appearance of informational services raises the level of assumed knowledge. Authors will be more likely to omit explanations because they will assume that even if the reader does not know a certain piece of knowledge, he or she can quickly learn it by searching the Internet.

p.128
> - There are two ways to approach the theory: a mountain-climbing type of book and a hiking type of book. The mountain-climbing type of book is one that builds up concepts. If you neglect the front part of the book, you will have problems later. A hiking-type book is one in which various concepts are presented one after another.
> + There are two ways to approach the story: the mountain climbing type and the hiking type. A mountain-climbing type book builds concepts step by step. If you cannot understand the first half of the book, you cannot understand the second half. A hiking book walks through various concepts. There is no harm in skipping some of the content.

p.133
> - because you don't know the total amount of "what is in the book" and therefore you cannot judge on your own whether you have understood 100% of it.
>  + Because you don't know the total amount of "what the author wanted to convey in this book", you can't judge on your own whether you understood 100% of it.

p.135
> - In some cases, the value is not in extracting the content of a single book, but in combining the content of the book with the rest of the knowledge.
>  + We tend to draw attention to the information "inside" a book. Often, however, there is value in combining the information inside the book with information outside the book.

p.137
> - I have listed several purposes for reading, but my best recommendation is to use it for the purpose of creating review material.
>  + So far we have introduced three purposes for reading. In this section, we will introduce another purpose. It is to create material for review.
The text makes it sound as if we are selecting recommendations from those we have presented in the past, but this is not the case, so we made it clear that we are adding to the list. We also reconsidered that we should not say "the best recommendation" when we are trying to present a variety of options and encourage readers to make a selection based on their individual situations.

> Naoyuki Honda, a management consultant, in his book "Leverage Reading," Note 36.
>  to extract and condense the important parts of the book and make "leverage memos".
>  advocated that it should be. Read this leverage memo repeatedly for further
>  So we are condensing the material. This is the equivalent of making material for review
>  > I will do so.
Add after
> The leverage memo I actually made after reading this book is this: 80% of the content of a text is in 20% of the text; take 80% in 20% of the time, leverage memo and throw away the original. Read it repeatedly and enrich it further.

p.139
> - However, by designing memos that had to be enriched or added to when they were read back, memos that I couldn't think of anything in particular to edit were accumulating as tasks waiting to be worked on.
> + But because I defined "read back" as "shorten or lengthen", reading back became a pain. Fragments that were not to be cut or added continued to remain on the list of "things to read back," and the pile of them undermined my motivation. In hindsight, I should have made the cost of rereading as low as possible. Editing is too costly; with Anki, described on p. 95, it only takes two taps to complete the processing of a single card. That is why it can be performed even in short gaps.

p.141
> - So you are betting on the possibility that by making it public, you are planting a seed, which will gradually grow as you receive feedback, and over time, your understanding will grow into a large tree.
> + By publishing, you plant a seed, which gradually grows as you receive feedback, and over time the understanding within you grows into a large tree. Would you like to bet on this possibility?
The subject matter was unclear.

p.147
> - If you could write 20 sheets in 5 minutes, a rough estimate is that you could have 100 sheets ready in 25 minutes!
> +In the previous section, you wrote out your time in 5 minutes. How many sheets did you spend, and if you could write 20 sheets in 5 minutes, a rough estimate is that you could prepare 100 sheets in 25 minutes.

> - I think that working people are very busy and it is difficult for them to take time to write in a coherent manner. This writing method does not demand that you sit at your desk all the time until you have written 100 pages.
>  + Even if you are too busy to take a coherent amount of time, this writing method allows you to make gradual progress; you don't have to sit at your desk all the time until you have written 100 pages.
It's not just for working people.

P.152
> - So it is designed to be placed on a desk by one person, and accordingly, the fusen are small and the pens are thin. This size of fusen, when placed side by side on an A4 sheet of paper, allows for 25 sheets to be pasted.
> +If you do it alone, you don't need to use large stickies. Smaller stickies can be arranged more in a limited space. So I use small sticky notes and a thin pen. This size sticky note can hold 25 sheets horizontally or 28 sheets vertically when placed side by side on an A4 sheet of paper.

p.153
> - I learned this technique of spreading out a fusen and moving nearby objects that seem to be related in "The Idea Method" written by Jiro Kawakita, a cultural anthropologist. It is called the KJ-method after his initialsNote 18, since at that time, glued Fusen paperNote 19 was not yet on the market,
>  + I learned this method of spreading out a piece of fusen and moving it closer to things that seem to be related in "The Idea Method" written by Jiro Kawakita, a cultural anthropologist. It is called the KJ method after his initialsNote 18, because this method was proposed in the 1960s and glued fusen paperNote 19 was not yet available at that time,
I don't know when "at that time" was, so I added it.

> - Many of us have experienced the KJ-legal method of moving a piece of paper with information on it.
> + Many of us have experienced the technique of moving a piece of paper with information on it.
KJ legal" is ambiguous.

p.155
Added reference to chapter 1 at the beginning of "Groupings are not objective" (backported from the English version)
- [[(5.2.4.1) Group organization is not objective]]

>  + In Chapter 1, we discussed finding patterns from concrete information; as introduced in the "Summary" section on p. 47, Einstein believed that axioms are generated by intuition, not logic. Group formation is similar to this. You do not create them by objective logic, but based on your subjective feelings.

p.157
> >- Understanding why we should not classify is very important in utilizing the KJ method.
> +Understanding the characteristics of the act of classification is (same text below)
In the chapters that follow, I will explain two disadvantages and one advantage of classification. So, not "why classification should not be done" but an understanding of what classification is.

p.160
> >- Jiro Kawakita only explains that you should collect things that "seem" related. This is another area where students of the KJ method tend to stumble. What exactly is a "relationship"?
>  >+Jiro Kawakita explained that you should collect things that seem to be related. This is another place where students of the KJ method tend to stumble. Let's delve into what a "relationship" is.

> -When we classify things, we put similar things into one group. When the KJ method says "collect things that seem to be related," this "relationship" is not limited to similarity.
> +There are many people who make the mistake of thinking that they need to gather similarities during the grouping phase. They only look at similar relationships. But there are many other relationships.
This is more easily connected to "for example, there is a relationship called ~".

Figure added.
[[(5.2.5.1) Relationship is not similarity]]

Added in its entirety.
[[(5.2.5.1-2) Not "related pieces" but "pieces likely to be related"]]
- P.35 of [[way of thinking]] contains the relevant content.

p.160
> -In learning the concept of group formation, Jiro Kawakita's expression "likely relationships" is difficult to grasp. In an attempt to remedy this, Masakazu Nakayama, author of "All About the NM Method," Note 25, advocated focusing on "opposing relationships.
> +To break the existing frame of thought that leads us to think "let's get similar things together" when "organizing groups," it is useful to focus on conflict. At a workshop I once held, a participant was having trouble forming groups. When I said, "You can put opposites in the same group, because opposites are a kind of relationship," the advice seemed to break her preconceived notions, and she was able to form a very good group. (new paragraph)
>  Masakazu Nakayama, author of "All About NM Law," Note 25, also advocated paying attention to "conflicts.

> -The KJ method is open to any relationship, including conflict. It is not necessary to be able to explain what the relationship is at the stage of creating a group.
> +NM method focused on the oppositional relationship, but in the KJ method, any relationship can be used, including oppositional relationships. In addition, it is not necessary to be able to explain what the relationship is at the stage of creating a group.
I would like to separate the clauses between these two sentences and include the story [[There is more than one conflict.]] in between, but I will not be able to make that correction in a non-expanded revision, so I will just add "also".

> >- The fusions that are in close physical proximity are images that speak on the same slide or on slides that are close in time.
>  >+ In the KJ method, stickies that are physically close together correspond to the same slide or slides that are close in time in the presentation.

p.163
>  -I explained at the beginning of this chapter that we first try to identify whether there is too much or too little information, and the 100 sheets of fusions was a good rule of thumb for this. Let's learn how the front cover creation works in a situation where a sufficient amount of information has been written out.
> +I explained at the beginning of this chapter that we first tried to identify whether we had too much or too little information. We then set a goal of 100 fusens. This is because the KJ method is a technique for taking a situation in which a sufficient amount of information has been written down and compressing it by creating a table of contents.
You wrote, "How does it work?" but I specified.

p.171
[[(5.3.1) Skip steps]]
In the English version, each step is restated, its purpose confirmed, and its omission is written under a subheading, well, it won't be in the 4th edition, so a note for the expanded edition.

> - Jiro Kawakita suggested repeating the process of table tag making and further grouping until you have several groups, but if you can understand what good grouping is after experiencing it a few times, you don't have to do it in your daily work. In my case, when I made a draft table of contents for a book from 600 sheets of fusen, I did the nameplate making, but for about 60-100 sheets of fusen divided by chapter, I did not make nameplates but directly arranged them in space.
> + Jiro Kawakita suggested repeating the table tag making and further grouping until several groups are formed. It is important to experience the table tag making process several times, as it is beneficial to understand what a good grouping is. However, once you have experienced it a few times and understand what good grouping is, you can skip it in your regular work.
> +In my case, when I made the proposed table of contents for the book from 600 sheets of fusen, I made a table of contents. Later, by dividing the book into chapters, the number of fusen was reduced to 60-100. For this, I did not make a front cover, but did a direct spatial arrangement.

p.173
> - I explained that cognitively advanced tasks such as thinking about meaning are more likely to be retained in memory. the KJ method is cognitively advanced processing and
> +I explained that cognitively advanced tasks are more likely to be retained in memory. Thinking about the meaning of a sentence is one of the cognitively advanced tasks; finding sticky notes related to the meaning of the KJ method, or making a table tag describing a group, are cognitively advanced processes.

p.175
> - For example, if I look at something I wrote three years ago and think it is still important today, I will revise it better now and post it again.
> +If, for example, I look at a text I wrote three years ago and find it still important today, then the text has long-term value. There would be value in improving and developing this text.

> Before I invented the above "system for saving labels," I used to throw away labels that had been used for presentations.
> Before I started using the system described on p.172, I used to throw away the labels after a presentation.
It's not so much an invention. I just put it in a clear file.
To be precise, there are a few cases where I have tried "keep them unfolded and attached to a wide polyethylene sheet," but this is wrinkled and not recommended at all. (and add a footnote in the expanded edition).

> - If the screen size were about twice as large, it would be realistic to do KJ method spatial placement on the screen.
> + Tablet devices support intuitive zooming in and out by pinch operation. This feature could solve the lack of space. In the not-too-distant future, monitors will surely double in size and accept pen input and pinch operation.

---
This page is auto-translated from [/nishio/第4刷に向けての修正差分](https://scrapbox.io/nishio/第4刷に向けての修正差分) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
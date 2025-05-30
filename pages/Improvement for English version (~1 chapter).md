---
title: "Improvement for English version (~1 chapter)"
---

This is not necessarily a mistake, but we have corrected what we felt was "unclear" in the original Japanese when translating it into English.
It's a long story, so here are the chapters after chapter 2
    - [[Improvement for English version (chapters 2 and 3)]]

diff:4.3

```
- The rest is divided into "fast reading" above F and "slow reading" below. If we think in terms of a gradation of "find" and "build," the fast reading method focuses on the find side. Since existing fast reading techniques are helpful in learning this finding reading method, we will introduce two fast reading techniques.
+ The rest is divided into "fast reading" above F and "slow reading" below F. Reading has two purposes: finding information and constructing understanding. Fast reading focuses more on finding information. To learn how to find information, existing fast reading techniques are helpful. So, below are two fast reading techniques.
```


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


In the first place, "X while looking through the whole book" was an unclear expression, and when I considered what was actually being done, I decided that it was "X for the whole book", not "X while looking through the whole book".

How can I explain that "checking headings and subheadings" and "finding paragraphs with mark 3" can be done simultaneously and in parallel?

0.3 Flow of this book
diff:0.3

```
- Chapter 1, "How to Learn Something New," considers how to learn something for which there is no right answer. It details how to learn through a cycle of learning so that you can apply what you learn to situations rather than memorizing it.
+ Chapter 1 is "How to Learn Something New." Just learning the answers does not mean that you will be able to apply them to your situation. To acquire the ability to apply, you need to go through a three-phase cycle: information gathering, abstraction, and practice. This chapter will explore each phase in detail.
```


If it is this commentary, shouldn't the title be "How to Learn to Apply"?

diff:0.3

```
- Many people buy too many books and end up with piles of them.
+ Have you bought too many books and left them unread?
```


With "piled up," you seem to be saying that physical bulk is the problem.
That's not the important part (the problem is the same if you buy the e-book).
The problem is that people buy books but do not start reading them due to high psychological hurdles to reading them, resulting in an accumulation of "books bought but not read". Even if unread books are stored, they do not add value.

diff:0.3

```
- However, I believe that what is a more important question than how. In Chapter 7, "How to Decide What to Learn," we will consider this question.
+ However, I believe that deciding what to learn is more important than devising how to learn. Chapter 7, "How to Decide What to Learn," describes decision-making strategies for deciding what to learn.
```


I made it specific because "think about this question" is vague.
In Japanese text, "how" and "what" are not so harmful because they appear to be keywords, but in English text, they are easier to read.

diff:0.1.1

```
- I believe that generating new knowledge on one's own is important for high-value intellectual production.
+ For high-value intellectual production, it is important to generate new knowledge oneself.
```


diff:0.2.1

```
- In addition to reading, "sutra copying," a technique of imitating and typing, is also often used.
+ In Japan, a technique called "Shakyo" is also often used.
+ (Footnote: "Shakyo" initially referred to a type of Buddhist training in East Asia in which sutras were transcribed by hand. Initially, the emphasis was on writing without changing a single word, but today in the context of programming education, it simply refers to reading a short piece of code, entering it into a computer, and then running it to see how it behaves.)

- This book also presents a number of intellectual production challenges and solutions. This is like sample programming code.
+ Programming textbook presents challenges and the programs that solve them. This book presents challenges and solutions to intellectual production. The same structure.
```




diff:0.2.2

```
- In this book, we hope to help you create your own model of intellectual production by comparing intellectual production techniques.
+ In this book, we hope to help you discover common patterns of intellectual production by comparing several intellectual production techniques.
```


The section title is "Abstraction and Modeling," but rather than mentioning the polysemous and confusing term "model" at this time, it would be better to use pattern discovery.
Abstract and make models into Compare and find patterns
[/intellitech-en/0.2.2 Compare and find patterns](https://scrapbox.io/intellitech-en/0.2.2 Compare and find patterns)

0.2.3
:

```
- Now you have the ability to find a pattern and come up with, "If I want to output "Bye, world!" in Python, why don't I just write it this way?" You now have the ability to come up with "If I want to output "Bye, world!
+ What if I want to output Bye, world! in Python? You have found a pattern and now you have the ability to come up with the following code.
```



I've mapped "compare" to "compare" in English, but this doesn't feel right.
>  [[information gathering]] is the image of collecting boxes. Here, information is compared to boxes. Information gathering is the process of collecting and arranging many boxes.
Information gathering is the process of collecting and arranging many boxes. Here we use the metaphor of boxes to represent information.


> - For example, the text in a book is abstract information that has been stripped away from the author's specific experiences during the writing process.
> + Consider, for example, the concept behind a book. Before writing a book, the author has many specific experiences. However, in the process of writing a book, he/she cannot write everything, and most of the specific information is stripped away.

> + I can stack boxes correctly in math, but they fall apart in other areas.

updated: [[revised diff#5d6b7623aff09e0000258c32 for 4th printing]].

> - Tuples and lists are very similar.
> + Lists and tuples are very similar.
according to the order of appearance.
- Corrected by the third edition.

- I'm trying to find out what the difference is.
+ Search engines to find out what's different.
made concrete

- You can rewrite the parts of the program that are written in lists to be tuples.
+ Rewrite the list in the program as a tuple, or
simplify

- Even when they repeat experiments to create something and then present it, they do not talk much about the prototypes that did not work out.
+ Suppose you repeatedly experiment to produce something and finally succeed. When you present your results, do not mention all the experiments that did not work.

- To what extent is it working as expected and to what extent is it not?
+ How far does the source code behave as expected? Where does the behavior start to differ from expectations?

- After clarifying this question and making numerous revisions, the program finally works correctly.
+ After finding the answer to this question and modifying the source code many times, the program finally works correctly.

- I don't show this trial-and-error process to others very often, but I do at least many times more trial-and-error than the success stories I publish, and I think anyone who is trying to answer a question that has no textbook answer is doing so.
+ I don't often show this trial and error process to others either, but I have at least three times as many attempts as I have published success stories. I think anyone who is trying to answer a question that has no textbook answer is doing so.
Slight correction [[corrected diff#5d6b7d42aff09e0000258c55 for 4th printing]].

Decomposition of complex sentences and clarification of criteria

1.3
- Now, let us consider in depth each of the three processes of learning: information gathering, modeling, and verification. First, let's talk about information gathering.
- If you take a vague view of "information gathering," it's hard to know where to start. The conditions for accomplishment are unclear. So, let's first divide it into smaller units and aim to run to a near goal. So let's consider how to divide "information gathering" into smaller units.
+Now, let's delve into each of the three phases of the learning cycle. In this section we will first delve into information gathering.
+If you have a vague idea of "information gathering," it is hard to know what exactly to do.
+The task of information gathering has unclear conditions for accomplishment. So, let's first divide it into smaller units to make the goal closer and clearer. Here are three ways to divide information gathering.

1.2.1
> The difference between learning as a student and learning from college
Hard to translate this title into English.
You use the words "passive and active learning" in the diagram and in the text...
The term "student learning and university learning" is not appropriate because "student" and "student" are distinguished in Japanese, whereas in English, university students are also students.

There is also the idea of before university / from university.
In that case, would the Japanese be "learning up to and from university"?

- You do not get to choose which textbooks you use.
+ You cannot choose your own textbooks.
- You also decide which textbooks you choose.
+ Choose your own textbooks.

- The questions on the junior high school final exam are designed so that if you follow the "correct method" as taught, you will always get the answer.
+ The questions on the final exam in junior high school are designed in such a way that if you correctly follow the methods your teacher taught you, you will always get the answer.
+ The questions on the final exam in middle school are designed to be solved. If you correctly implement the methods taught by your teacher, you will always get the answer.

- Suppose you are a working adult, and you are now thinking, "I should learn this.
+Suppose you are a working adult and there is something you think you should learn now.

- The same is true of learning a programming language; it is unclear how far along one has to go to feel that one has "mastered" it.
+ The same goes for learning a programming language. You don't know how far along you have to go to feel that you have "mastered the language".

- Also, that [[goal]] should be as close as possible. It is reckless to challenge a 42-kilometer full marathon from the start. It is important to start with a shorter distance and feel the joy of reaching the goal and the sense of accomplishment as soon as possible. This is what "[[tutorial]]" is often used for in [[game]].
+ Also, that [[goal]] should be as close as possible. For example, it is reckless to challenge a 42-kilometer full marathon from the beginning. It is important to start with a shorter distance and feel the joy of reaching the goal. In general, it is important to feel a sense of accomplishment quickly to stay motivated. This is what [[tutorial]], often used for [[game]], takes advantage of.

- Also, some people have the misconception that going to college will teach them secret knowledge that they cannot get anywhere else, but that is not what college is about.
+ I think some people have the misconception that going to college gives you secret knowledge that you can't get anywhere else. However, college is not a place where secrets are given away.

- Universities that are proactive in accepting working graduate students have adopted systems that make it easier for working people to learn, such as offering classes on weekends and weekday evenings.
+ Some universities are proactive in accepting working graduate students. Those universities have adopted a system that makes it easier for working people to learn, such as holding classes on weekends and weekday evenings!


I've used the expression "getting back into college," but since some of you have never been in one, "getting into college" seemed like a better way to describe it.

- These cost reductions have made it harder to function as an indicator of quality, as projects that previously could not be passed on are now being passed on. In this day and age, it can no longer be said that "a paper book is good because it is a paper book.
+ These cost savings have led publishers to accept more and more publishing projects. In this day and age, paper books no longer serve as an indicator of quality.

- A bestseller is a book that many people have bought. You might think this would be social proof, too.
+ A bestseller is a book that many people have bought. You might think this is another indicator of quality.

You didn't explain the term "[[social proof]]."

- This is especially an opportunity in situations where you have something specific in mind that you want to create.
+ If you have something specific in mind that you want to create, here's your chance.

- The key to increasing motivation is not to aim for such a distant goal, but to aim for something closer to "what I want to do now.
+ Don't aim for such a distant goal. Aim for a near goal such as "what I want to do now. That's the key to increasing your motivation.

- I hope you have sensed the similarities among the three.
+ You may have sensed a common pattern among the three.
The "point" is ambiguous. It would be better to read "pattern" explicitly, since we have been talking up to that point about the importance of finding common patterns from multiple examples.

- So you need a goal that is a good distance away for you. This requires you to decide what goals are appropriate for you, not what others have set for you.
+ In other words, you need a goal that is not too far from you. Other people's goals are irrelevant. You need to decide what goals are appropriate for you.

Goal=Goal, but maybe we should look at the entire perimeter and not unnecessarily sway the wording.
The title in Japanese is "Goal is achievable", but in English it is "Goal is achievable".
If you are going to use them differently, you need to specify the use, but I don't see any particular need to use them differently.

- For example, let's say someone who is just starting to learn a programming language thinks that his/her goal is to create an awesome game. This is a good future direction, but do you know how to achieve it?
+ Let's say, for example, that you are about to learn a programming language. And let's say your goal is to create an awesome game. Aiming for an awesome game is not a bad long-term direction. But how would you know how to achieve it?

- Trying to know everything in detail from the beginning is bad goal setting.
+ Trying to know everything in detail is bad goal setting.

It doesn't have to start at the beginning.

- This is just like trying to figure out the layout of all the stores in the world from the beginning is an absurd goal setting. You can start with a rough map and gradually become more detailed.
+ Trying to figure out the placement of goods in every store in the world is a foolhardy goal. It's the same thing. You can start with a rough map of where all the stores are located and gradually become more and more familiar with them.

- In addition, the emergence of Web servicesNote 1 that allow users to post issues they wish to solve and other users to post their solutions has made it possible to find solutions to specific programming issues with a fairly high probability when searching for them.
+ Another question and answer service has emerged. This is a web service that allows users to post issues they wish to solve and other users to post their solutions. With this emergence, a search for a specific programming issue has a fairly high probability of finding a solution.

Sentence complexity.

- New ways of gathering information have also emerged, such as "searching in English and looking at question-and-answer websites.
+ Question and answer sites are a new source of information, different from books. A new way of gathering information is being created.

-In the days of paper books, the ability to see the big picture and think, "It should be around here," was very important.
+In the days of paper books, it was very important to get the big picture. Search costs were high and it was necessary to narrow down where the information you were looking for was located.

- It is a misconception that the goal to be reached after a lot of study is to "get the big picture.
+ It is a misconception that after a lot of study you can finally get the big picture.

Add figure
After translating so far, I felt sad that there were no pictures about the three methods of information gathering, so I drew them
Bundled: [[Diagram of the three methods of information collection]].

- The concretization of objectives is the same as in the previous section of this chapter.
+ Specificity of purpose is the same as "Prerequisites for learning from what you want to know > Goals are clearly defined" described in the previous section of this chapter.

- So instead of the imprecise and distant goal of "understanding the paper in detail," you created a clear goal with time segments and tried to get the general structure in your head.
+ Instead of the unclear and distant goal of "understanding the paper in detail," you have created a close and clear goal by dividing your time and focusing only on the broad structure.

I was trying to get the rough structure in my head instead of the goal, because it sounds like you were trying to get the goal in your head."

- On the other hand, when you are trying to discuss something, you must know where to find the article to which you need to refer and be able to read there.
+ On the other hand, when you are trying to discuss something, you need to refer to an article. So you have to know where the article is located.

- The difference is that it is drawn in a tree-like form so that the hierarchy above and below can be quickly found, and it is on one large sheet of paper so that the entire page can be viewed without turning the page.
+ The difference is the form of the information. Information is drawn in a tree-like format so that you can quickly find the hierarchy above and below. It will also be on one large sheet of paper so that the entire page can be viewed without turning the page.

- During class, when referring to a particular article, we look at this map many times to see "where" the article is located. For example, Article 570 "Seller's Liability for Defects" is in Part 3, "Claims," in Chapter 2, "Contracts," in Section 3, "Purchase and Sale," and so on. Every time you mention an article, it is in Part 3, Claims, Chapter 2, Contracts, Section 3, Purchase and Sale, Article 570: ...... and you will see the information in the higher levels over and over again, so it will naturally enter your mind. I found tracing the map from the root each time to be a useful method in systematically storing a vast amount of information in my brain.
+ During class, when referring to a particular article, look at this map to see where that article is located and vocalize it in order, starting at the top level. For example, Article 570 "Seller's Liability for Defects" is located in Part 3, "Claims," in Chapter 2, "Contracts," in Section 3, "Purchase and Sale. So, whenever the article is mentioned, it occurs as "Part 3, Claims, Chapter 2, Contract, Section 3, Purchase and Sale, Article 570, Seller's Liability for Defects".
+ This activity causes the information in the upper levels of the hierarchy to be seen many times. The closer the information is to the root, the more frequently it appears. Therefore, we memorize it naturally. Tracing the map back to the root each time is a useful way to systematically store vast amounts of information in the brain.

I made it more specific.

-
+If you can't gather information in broad strokes, you have to do it from one end of the spectrum to the other.
+If you read the table of contents in an attempt to get a general idea of the big picture, you may not understand anything. This phenomenon often occurs when learning something new. This is caused by not having enough material to build an understanding.
+Often, the words in the table of contents are already an abstraction. If you don't have the knowledge to support that abstraction, you won't be able to read the table of contents and understand it; if you don't have the knowledge to support that abstraction, you won't be able to understand it.
+We often think about what is the most efficient way to learn. However, it is a waste of time to try to figure that out when we do not even have the materials to determine what would be efficient to learn from. We need to get the materials first.

-
+ You may look at this estimate and be demotivated, thinking you have to spend 25 hours. But you are wrong; you do not have to spend 25 hours.

- Even in the worst case scenario where you are unable to learn effectively, you can estimate that if you continue to copy sutras for 25 hours, you will have copied a textbook, which will make it easier to stay motivated than if you vaguely think, "I have no idea what I am reading, but I must do my best to learn. The "I don't know what I'm reading, but I have to work hard to learn it.
Wordy

- When a programmer has a problem with a program, he or she may guess correctly that there may be a problem around such-and-such a process before looking at the actual source code. How is this possible?
+ A good programmer sometimes predicts the cause of the problem without having to look at the actual source code. Why is it possible?

> Models are simplified representations that explain how the real world works.
This is directly connected to the previous paragraph, but I think it would be better to split it up one more level, just like the next module section.

- Use models to save thought.
    - > Models are simplified representations to explain how the real world works. Since the phenomena occurring in the real world are complex, we simplify them by trimming away the unimportant parts so that even limited human cognitive abilities can handle them. For example, in high school physics, air resistance and friction are assumed to be non-existent. The air resistance and friction that exist in the real world are ignored to simplify the problem so that high school students can handle it.
    - >  Since the model is an excerpt of reality, it does not perfectly match reality. This is what is referred to as "all models are wrong" Note 31.
- Models allow low-cost experimentation.
    - > The value of a model is not how well it matches reality. It is how much less expensive it is to manipulate the model compared to directly manipulating realityNote 32.
    - >  In particular, a model expressed in the form of a mathematical formula is called a "mathematical model. When a model is created in the form of a mathematical equation or program, it is easier to conduct experiments. This is because there is no need for physical experimental equipment.
    - >  When a programmer has a problem with a program, he or she can predict the problem and guess correctly before looking at the actual source code. How is this possible? He has a model of the program in his brain, and he can experiment in his brain to see what phenomena occur when he breaks various parts of that model. He then picks out the phenomena that occur as a result of the breakage that are similar to the actual observed facts.
- The order of the sentences was switched in the process of carving them up.

- In reality, there are gradations: some are exactly the same, some are very similar and largely the same but slightly different, some are hardly similar but have a little bit in common, and some are completely different.
+ In reality, it is a gradient.

It is quite muddled when translated into English.


- For new insights, we need to compare "similar" things that are neither "the same" nor "different," but partly the same and partly different.

The "new awareness" here refers to pattern discovery.

- Parables are often used to convey abstractions.
+ Parables are often used to convey abstract concepts.

I drew a diagram.
    - [[Figure 2019-01-23.]]
    - [/intellitech-en/1.5.1.2 Metaphor](https://scrapbox.io/intellitech-en/1.5.1.2 Metaphor)
    - [/intellitech-en/1.4.7 Why is abstraction necessary?](https://scrapbox.io/intellitech-en/1.4.7 Why is abstraction necessary?)
    - [/intellitech-en/1.4.3.2 Hide non-critical parts = Extract important parts](https://scrapbox.io/intellitech-en/1.4.3.2 Hide non-critical parts = Extract important parts)
    - [/intellitech-en/1.4.4 Model / View / Controller](https://scrapbox.io/intellitech-en/1.4.4 Model / View / Controller)
    - [/intellitech-en/1.4.3.1 Restrict interaction](https://scrapbox.io/intellitech-en/1.4.3.1 Restrict interaction)
    - [/intellitech-en/Column: Naming the pattern](https://scrapbox.io/intellitech-en/Column: Naming the pattern)

- Finding commonalities is easy to get used to, but it is also easy to simply gather information, saying "this is similar, this is similar". Once you have some familiarity with it, it is easier to focus on the differences and think about seemingly contradictory things.
+ People tend to focus on common parts. However, collecting common parts is unlikely to lead to abstraction. Focusing on differences and contradictions is more likely to lead to abstraction.

- You might think that you don't have to discover the patterns yourself, but that you can just read a book that describes the patterns. Although this seems reasonable at first glance, in reality, I think people often feel that it doesn't ring a bell, or that it is too abstract to understand.
+ You might think that you can learn patterns by reading books with patterns in them, without having to discover them yourself. At first glance, this seems reasonable. But when you actually read pattern books, you often find them abstract and difficult to understand.

Good" is ambiguous.

- On the other hand, explaining "why it is similar" in one's own words, changing it to another example, or applying it by realizing that the problem one wants to solve can be solved by a public companion cipher cannot be done by someone who does not understand public companion ciphers.
+ On the other hand, if you don't understand it, you can't explain in your own words why it is similar. You cannot change it to another example. You cannot realize that the problem you want to solve is solved by public key cryptography. You cannot apply your knowledge.

- It often happens that we assume we understand something when we really don't. It is important to verify our understanding in order to recognize the error and continue learning.
+ We often misunderstand our own understanding. We often feel that we understand a concept when we really do not. It is important to recognize this misunderstanding and examine our understanding in order to improve our understanding.

- A similar concept is expressed by saying that giving a hungry person a fish will only keep him hungry for a day, so instead of giving him a fish, teach him how to fish.
+ A similar analogy is given to the saying, "Give a hungry man a fish, but teach him how to fish, because he will only go hungry for a day.

- Even if you feel like you know something, it is no guarantee that you really do. You have to actually use the model in your brain that you think is correct and observe the results to [[verify]] whether it is really correct.
+ Feeling like you know something is no guarantee that you really know it. The feeling of understanding occurs when a provisional model is created in your brain. Whether that model is correct or not needs to be verified. Verification is done by actually using that model and observing the results.

-Programming learning is an area that is very easy to validate.... Let's compare it to making a chair with woodworking, which is similar in terms of making things... Let's compare it to drawing, which is another similarity in terms of making things.
+ Programming is a relatively easy area to verify understanding... Compare this to other areas of understanding. Woodworking is similar to programming in that it is also an action of making things... Let's compare it to another area of understanding.

Let's compare with the understanding in other domain. Woodworking is an act similar to programming in that it is to make things.

- It is an intuitive discovery, based on actual data and direct experience, that says, "Oh, there seems to be this pattern.
+ It is an intuitive discovery that "Oh, there seems to be a pattern like this" while observing specific information.

Since the correspondence between Einstein's ideas and the book is explained here, it is better to explain it in the terms of the book rather than in Einstein's terms.

- In "Make and Verify" (* page), we talked about making something based on our understanding and verifying the correctness of our understanding by seeing if it works as expected. The understanding corresponds to axiom A, and based on that understanding, a concrete claim S is made, "If I build it like this, it should work like this," and then it is verified by comparing it directly with experience E to see if it actually works as expected.

+In "Make and Verify" (* page), we talked about verifying your understanding by creating a program. Understanding corresponds to Axiom A. You create a concrete program based on your understanding. This corresponds to the concrete claim S. You then observe whether this program behaves as you expect. The concrete behavior of the program corresponds directly to your experience E, and you verify it by checking it against it.

- Einstein thought that step 4 also belonged to intuition, because the relationship between the concepts that appear in S and direct experience is not logical, for example, there is no basis for mapping the word dog to what we directly experience when we see a dog. I guess this is related to the "all models are wrong" story, that since models are different from direct experience, we cannot logically say whether a newly observed direct experience corresponds to a particular model or not.
+ Einstein considered step 4 to also belong to intuition, because the relationship between the concepts that appear in S and our direct experience is not logical. For example, the mapping between the word dog and what we directly experience when we see a dog has no logical basis. This idea is a related story to "all models are wrong. Since models are different from the real world phenomena themselves, the interpretation of a newly observed phenomenon by a particular model is not a logical decision, but a subjective human choice.


---
This page is auto-translated from [/nishio/英語版作成に伴う推敲(~1章)](https://scrapbox.io/nishio/英語版作成に伴う推敲(~1章)) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
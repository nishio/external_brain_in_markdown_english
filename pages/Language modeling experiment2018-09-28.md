---
title: "Language modeling experiment2018-09-28"
---

![image](https://gyazo.com/6c848c9690a3289e512c09cb3f72cc35/thumb/1000)

Study the main text part of the Intellectual Production Techniques of Engineers with [[LSTM]] #LSTM-RNN
:

```
%run train_rnnlm.py
#vocab = 7069
epoch       iteration   perplexity  val_perplexity
3           500         207.066     168.164         
7           1000        55.6905     88.8363         
11          1500        32.3283     83.8262         
15          2000        19.5342     96.141          
19          2500        12.4958     115.902         
23          3000        9.15305     138.699         
26          3500        6.81103     159.106         
30          4000        5.71608     178.38          
34          4500        5.07816     201.215         
38          5000        4.33354     223.951         
test
test perplexity: 333.32472655247705
```

I'm not sure you could have stopped at 15 epochs.
- →I've tried to generate sentences with the model at about 2000 iterations, but subjectively the last model seems to be better.

Sentence generation experiments using LSTM language models:.
- >  Intellectual big direction / Realistic :Compare pictures of tuples and repeat cycle again.
- >  7 Engineer's Wall of 7 Ideas That Haven't Came Out of Consciousness ❹Ideas come up with new ideas.
- >  Remember the abstraction about growing up, and understanding is 8 hours frequent "This has to do with
- >  Understanding. It is UC V for philosophical language. Not one side of the table of contents, but the table of contents is back
- >  Repeat reading. Think first before you stand up. For example tree Mihaly (Edison), climbing
- >  because I am looking at access to James Webb Young. I agree, and "U Theory."
- >  Edison, during maintenance and engineering)❸ To instruct as often as you edit
- >  Wife guru research expeditions use state actively. The break-even point is past this design

The local word connections are pretty smooth, but, well, the sentence as a whole is meaningless.

The above output gives one word and then generates 20 words, but I think it often outputs sentences that have a better mood if they run for a while

- > The wife's mastery research expedition uses the state positively. So the break-even point stops with the intention of "I can't proceed with the game I thought I needed such a table of contents" when the answer is "it seems relevant" out of the products past this design. For example, this somewhat relationship is the origin of the word 15 difficult. On the other hand, it is a way of ceasing to read while moving one's hand, not something that goes actively learning to a physical teacher. It is important not to be able to distinguish between the two hares when the thought comes to mind, "He who pursues two hares will not get one hare." The task that had been first of all to get the topic to connect can be downloaded from the URL somewhat for your experience to record and hit well.
- > Intelligent big direction/Realistic :Again by comparing pictures of the tuple and repeating the cycle, the understanding is verified. The experimental verification may have been some-like associating hypotheses. Experiencing ❶ being selected by myself, I need to clarify the purpose. I have a quest and a realization. The world is about whale sharks, fun, letting go of the concept of otherness and creating memories efficiently. Now the task of making questions is full and confusing, with the confusion must make new knowledge. For example, "coming up with an idea" is vague and a big task bud, you also realize the worry that "it would be wrong to be able to do it in your own words".

This is probably due to the fact that the internal state created by a single word input is far from the distribution of the internal state at the time of learning, since many words are continuously input at the time of learning. [[Sentence generation takes multiple words as input]].
The model to find and cut out appropriate start and end points in a word sequence after running for a while seems to work well with the same mechanism as the [[direct quotation model]] from the original text.

They can continue a topic related to time for a longer period of time. Only LSTM can retain context for a long time.
- > The "no big time" means that you know about the size of multiple tasks, read through bad replacements without realizing the optimal drop, and do not have a sense of time from the information based on the writing in GTDSensing : The state of not sensing the time based on the experience of others. I tried to work with the algorithm of choosing the option with the highest expected value based on the experience of others. Conversely, looking back is also the same part like the word "abstract" to its "grasp the whole picture" when you think that you have "found" in line following that the person who is framed in the gap between your afterimage and Cowan is used. It will be quite an observation to make what kind of knowledge you intend to assume based on this training every day. Is it easy in the pyramid of reading speed? For example, "grasping the big picture".

This must have picked up the headline or something, "Chapter 1: Three Ways to Gather Information to Learn Something New". Similarly, some of the footnotes have been picked up, which looks odd.
- > I prefer to do 50mm x 38mm fusen Chapter 1: The driving force that turns the cycle to learn new things:Motivation 8 Chapter 1: The three ways of information gathering to learn new things, how to allocate the three ways of information gathering, as you want to continue where you turn the conversation, you may learn the 1964. This is the birth of the phrase "30 seconds per book", which means 30 seconds for just one page, and the two hours will be over.

Part of original data
> ... But it is not. First of all, the top priority is excellence, and that Chapter 7: Deciding What to Learn Yourself Management Strategies 234.
> Chapter 7: Deciding What to Learn is a Self-Management Strategy 235 and thus an opportunity for growthNote 15....
Ah, I see. So that's how it is.
Need to remove this: [[Page Row-Based Language Models]].

---
This page is auto-translated from [/nishio/言語モデル作成実験2018-09-28](https://scrapbox.io/nishio/言語モデル作成実験2018-09-28) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
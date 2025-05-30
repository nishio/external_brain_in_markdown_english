---
title: "Assistance in dividing long sentences into stickies"
---

- I want to help [[division]] [[long sentence]] into reasonable sizes as sticky notes.

---
Sentences written in a lighthearted manner
> Ah, well, people who are not used to the process of making lots of stickies and doing the KJ method don't have a good idea of how granular the information should be when they make the stickies in the first place. That's where the software needs to help.
This is not the proper granularity.
- ![image](https://gyazo.com/15e2094edc84a4e2694d774851748fda/thumb/1000)
Divide and conquer by experienced personnel
- ![image](https://gyazo.com/0813639be5cc94dcbbac5d2d2ad9c220/thumb/1000)
- ![image](https://gyazo.com/ca47482c3dfcbc2c4ce2cd0d0bd33018/thumb/1000)
    - This is a split and delete only pattern
- With rewriting it looks like this:.
    - ![image](https://gyazo.com/024545873ed23e894dd2305b63569053/thumb/1000)

---

- v1: [[interconnected range]] extraction
    - It worked for a while, but not great.
    - Instead of using the results after the engagement analysis, we thought it was necessary to devise a process of engagement analysis.
    - While trying to implement the co-reference analysis itself, I realized that there is no need for co-reference analysis in the first place.

- v2: 4-level decomposition algorithm
    - consideration
        - For "words that appear at a distance but are connected in terms of their affinities."
            - Whether they are connected in terms of engagement or not, they can be separated as stickies because they appear at a distance!
        - Split by punctuation without length-dependent splitting, just split by punctuation.
        - It's good because I break it up with punctuation and if it's too long, I chop it up even more with conjunctive particles.
    - structure
        - Split by punctuation, parentheses, etc.
        - If the length is above the threshold, we'll split it with a conjunctive particle.
        - If the length exceeds the threshold, we'll split it with a cohesive particle.
        - If the length is above the threshold, we'll split it with a case particle.
    - I was thinking of doing machine learning based on the surrounding predispositions for where to divide, but when I looked at the predispositions with my eyes, I felt like this was the way to go.

- v3: Algorithm to split recursively from the one with the highest split priority score
    - Observe and discuss v2 results
        - The problem that "come out" and "use it" are split by "te" and made into the original form to form "kuru" and "iru".
        - Same word, different division priority.
        - Change the score depending on the situation and split from the largest to the smallest.
        - Scores are now adjusted on a rule basis.
            - It will eventually fail.
            - Human beings cannot reconcile past decisions with consistency.
            - Moving to machine learning?
            - I'm collecting examples of cases that have not been divided well.

- v4: If we were to move to machine learning
    - What is the best way to do it?
    - 1: Binary classification of "to separate or not to separate" is performed for each word, and the words are divided from the one with the highest "score to separate" until the length constraint is satisfied.
        - Score calculation of the current score-based method becomes a form of machine learning.
    - 2: CRF？LSTM？Transfomer？
        - If the system is too heavy, even if it is possible, I think it will be troublesome to operate.
        - [[Machine Learning for Long Sticky Note Segmentation]]


Garbage Cleaning Algorithm
- Not only do they divide, but they also remove unnecessary words.
- E.g., "Oh, well..."
- Currently, they're cutting it down to the dictionary base longest match.


Sticky note detail
![image](https://gyazo.com/bcb23346a3e5a66bf74a2e3fab09a350/thumb/1000)
> The default for images was not to auto-upgrade by default, but this has changed since M86. This auto-upgrade does not fall back to HTTP, so images served only via HTTP will not be viewable.
- 20 feels good.

- [[Assistance in dividing a long document into stickies: an example of a bad division]]

API
    - [[Natural Language Processing on Heroku]]
- Done [[✅ longest line is ticked with one click]].

---
2021-01-05
    - Can't we do that with [[Shift-Reduce Algorithm]]?
- Last time, I took the [[interconnected range]] approach of taking the [[interconnected range]] and then trimming the words I didn't want.
    - I threw [[paired reception analysis]] into CaboCha...
- It's good up to the point where you inscribe it into a phrase, a little shorter, but you can remove the final particle, etc., from that phrase and make it a sticky note.
- Another way to describe what we want to do is.
    - Sentences are a little too short for a phrase, so I'd like to combine as much as is acceptable.
    - I want to make a decision by looking at the length of the string of concatenated items.
    - There are so many words and phrases that don't need to be included in the deliverables that I want to ignore.
- The Simple Way
    - If the area enclosed in parentheses is short enough, it is adopted.
    - Sequence of words that commonly appear in multiple lines (apply [[RAKE]])
        - This is useful, but not enough

----
yure  [[Ability to automatically inscribe long-form content on stickies]]

[[pRegroup]]

---
This page is auto-translated from [/nishio/長文の付箋への分割支援](https://scrapbox.io/nishio/長文の付箋への分割支援) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
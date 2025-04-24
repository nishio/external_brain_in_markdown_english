---
title: "I don't think there are enough questions related to ✅."
---

Maybe the influence of this
    - [[Don't ask questions related to keywords you haven't dug into.]]

At the time of this, I ran a script that used the logs to get statistical information.
- I tried running it again, and the script rubbed me the wrong way due to a change in the keyword extraction code.
- I guess this mechanism is not used: [[Replay ✅ past logs with keyword extraction results at that time]].
    - doesn't seem to be using it

Score Observation
- Subtle difference.
:

```
1> It would be good if users can understand the process of building up a story slowly by moving stickies
DEBUG:server.keicho.action:* 825.40 What kind of "user" is that "user"?
DEBUG:server.keicho.action:* 1307.41 Where is that "sticky"?

DEBUG:server.keicho.action:isPrevious1=0 isPrevious2=1 score1=1360.77 score2=1072.62
DEBUG:server.keicho.action: 1156.96 What is the relationship between this "chat" and "stickies"?

DEBUG:server.keicho.action:isPrevious1=1 isPrevious2=0 score1=1072.62 score2=1360.77
DEBUG:server.keicho.action: 1171.96 What is the relationship between that "sticky" and "chat"?
```


I used replay to determine the frequency of each type of question.
- Not zero, but less than 1%.
:

```
928:0, 639:32, 234:1, 131:31, 96:2, 86:21, 76:3, 57:4, 39:16, 36:23, 36:22, 32:26, 22:24, 15:25, 5:28, 5:27, 4:17, 3:19, 3:18
263 talks, 1677 questions
BASIC_TWO: 1162 (69%)
BASIC_FIVE: 1391 (82%)
TIME: 39 (2%)
RELATION: 10 (0%)
CHAIN: 73 (4%)
relation_before_basic 20
```


I changed the scoring a bit.
- Multiplied rather than added to the last appearance bonus.
:

```
K = 1
263 talks, 1677 questions
BASIC_TWO: 1156 (68%)
BASIC_FIVE: 1378 (82%)
TIME: 33 (1%)
RELATION: 37 (2%)
CHAIN: 66 (3%)
relation_before_basic 74
```

Hmmm, there's an increase, but there's also an increase in "violations that are related questions to questions that I'm not digging into".

But if violations are still happening even with the current "score that was made so reluctant that violations don't happen in the first place," then maybe we need a fundamental fix.

I should observe why the violations are happening where they are happening with the current formula.
After all, expressing a word in terms of a single real number, a score, is not expressive enough.
- Words that appear multiple times get higher scores, but the higher score has nothing to do with whether or not the question was asked for that word.

But wait, even if you didn't ask the question and dig deeper, the higher score means that it must have appeared many times, so it doesn't matter if a violation has occurred.
Before the last modification, it was "I'm being asked a question about a word that just appeared in the previous statement!" But that will no longer happen now that the calculation is done in min.
Might it matter if there are a lot of violations?
Let's try it and observe for a while.

- [[I'd like to test this because I've fixed the fact that the frequency of the relationship questions seemed to be less frequent.]]
To make the behavior easier to understand, I've added a last-appearance bonus that's even more times the value I thought was appropriate.

---
This page is auto-translated from [/nishio/✅関係の質問が少ない気がする](https://scrapbox.io/nishio/✅関係の質問が少ない気がする) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
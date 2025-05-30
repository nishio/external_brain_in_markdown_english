---
title: "✅Recurrences of short keywords are not treated as keywords."
---

Re-occurrence of 🤔short keywords should be discounted
- →✅Recurrences of short keywords are not treated as keywords.

- Adverse effect of [✅A substring that appears but is not selected for keyword extraction is considered a keyword occurrence.

![image](https://gyazo.com/0723b1a51b99faa6a2f95b0249ab73b6/thumb/1000)
The key word is judged to be "between."
I did my best to interpret it to mean "human" and replied, but of course the "human" in that reply also includes the "pause", so it is counted again.

phenomenological observation
:

```
0> What is the "frequency" of this "frequency"?
1> I thought the question asking about the relationship between two keywords didn't come up much lately, so I checked it out and found that it doesn't come up much anymore due to a bug fix.
--------------------------------------------------
total: 122:question, 112:relationship, 100:frequency, 100:bugfixes, 99:not appearing, 99:appearing, 99:testing, 78:keywords, 72:lookup, 71:effect, 67:between, 53:fix, 37:fixed, 37:two
--------------------------------------------------
...
0> What kind of "relationship" is that "relationship"?
1> Some questions ask that directly. Then there are others that ask what is in between.
--------------------------------------------------
total: 335:question, 167:between, 142:affect, 130:relationship, 100:frequency, 100:one way, 100:bug fixes, 99:doesn't appear, 99:appears, 99:testing, 97:affect, 94:related, 78:keywords, 75:do, 72:look up, 67:two, 53: modify, 45:affects one, 37:modified, 28:is, 18:some questions to ask directly
--------------------------------------------------
...
What does this "question" seem to be?
1> A hook that is thrown at a human being to hook and pull out what is not yet verbalized in that human being and make him verbalize it.
*** interval 100 ['human', 'throw to human'].
*** Yes 28.0 [].
--------------------------------------------------
total: 316:question, 267:between, 142:influence, 130:relationship, 100:frequency, 100:hook, 100:one, 100:variation, 100:bug fix, 100:symbolic modeling, 100:server, 99:does not appear, 99:appears, 99:testing, 97 affects, 94:related to, 88:identifying, 80:doing, 78:keywords, 75:throwing at humans, 73:program, 72:looking into, 69:throwing at, 67:two, 64:hooking and dragging into language, 56:being, 53:fixing, 45:how it affects one side, 44 Linguizing, 37:Modified
--------------------------------------------------
...
0> What kind of "pause" is that "pause"?
1> Between? You mean humans. Humans feel some kind of blur that they can't put into words properly, and they come to talk to chatbots.
--------------------------------------------------
total: 316:question, 297:between, 142:influence, 130:relationship, 100:frequency, 100:hook, 100:one, 100:variation, 100:bugfix, 100:chatbot, 100:symbolic modeling, 100:server, 99:not appearing, 99:appearing 99:testing, 99:talk to chatbot, 99:come talk to chatbot, 97:affect, 96:blur, 94:related, 88:identify, 80:do, 78:keywords, 75:throw to human, 73:human, 73:program, 72:look up, 69: Throwing to, 67:Two, 66:Talking to
--------------------------------------------------
```


Hmmm, I have a feeling this case simply can't be done at a discount!
- By that point, "between" usually appears twice as a keyword, and the score is over 100, 2nd place.
- Already asked various questions in response to the #1 "question".
- Even if the "between" score is not added, the question is eligible for the last-minute bonus just because it is determined to have appeared immediately before the "between" score.
    - If it is not considered as an appearance, the "fish hook" that appeared immediately before wins.
:

```
1> A hook that is thrown at a human being to hook and pull out what is not yet verbalized in that human being and make him verbalize it.
DEBUG:server.keicho.action:* 267.40 What is this "pause"?
DEBUG:server.keicho.action:* 400.40 What kind of "hook" is that "hook"?
```

- The one that was actually deemed to appear
    - 4:Question, 4:Do, 3:Chat, 3:Be, 2:Talk, 2:Appear, 2:Come, 1:Between, 1:Be with, 1:Partner, 1:Feel, 1:Impact, 1:Person, 1:Program, 1:Become`.
    - Hmmm, limit it to 3 or more letters or `3:chat, 2:come up, 1:be a partner, 1:program`.


---
This page is auto-translated from [/nishio/✅短いキーワードの再出現はキーワード扱いしない](https://scrapbox.io/nishio/✅短いキーワードの再出現はキーワード扱いしない) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
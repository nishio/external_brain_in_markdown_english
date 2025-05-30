---
title: "Check the most uncertain areas first."
---

from  [[Nodal Point of Thought 2021 Unexplored Jr.]]
Check the most uncertain areas first.

> [hiroki_daichi](https://twitter.com/hiroki_daichi/status/1388253385065852928): Principles such as Agile are often explained in relation to "speed and agility" because of the meaning of the word, which makes them difficult to understand. The key principle in software development is "[[fail-fast]]", and the principle of static typing, automated testing, chaos engineering, scrum development, and product management is "[[premature failure]]".
- > [hiroki_daichi](https://twitter.com/hiroki_daichi/status/1388253386982580226): sometimes when associated with speed, we tend to lean towards "making it in a hurry" or "making it without room to spare".
- > To fail early, [[Hypothesis testing lead time]] thinking is required. Thinking is required to identify what is the most volatile risk.
- > [hiroki_daichi](https://twitter.com/hiroki_daichi/status/1388256173250338817): but this has a very high human cognitive cost. This is because people have an instinct to escape uncertainty. The cultural capital to tame this instinct and achieve early failure is crucial, and such is acquired and crystallized in the practice of software and processes.
- > [hiroki_daichi](https://twitter.com/hiroki_daichi/status/1388259914049474561): Domain-driven design is also a story about understanding and interacting with domains, which confronts the heart of project risk, but it is also It is also a story about how to understand and implement the distilled domain so that it is incorporated into types, assertions, and tests in a way that is prematurely failed so that it is consistent.

> [nishio](https://twitter.com/nishio/status/1388413629880360960): "It is important to shorten the lead time for hypothesis testing, and this requires thinking to identify what is the most volatile risk", I completely I agree with you, but I'm trying to think of a better way to explain this to middle and high school students, because I don't think they will get it.
- > [nishio](https://twitter.com/nishio/status/1388414471316545540): In the proposal "If you make B from A and C from B, the customer will be happy", if it is "unclear whether the method of making B from A will work" and you say "I made a prototype of making C from B. If the method of making C from B is not clear, then the work will be meaningless if the process does not go as planned between A and B. The feeling of "I'm not sure how to make B from A.
- >  ![image](https://gyazo.com/e4a07f6c3868f0e67aa05b0cdeddad2c/thumb/1000)
- > [nishio](https://twitter.com/nishio/status/1388415380956147713): in other words, it is the most uncertain arrows that should be prototyped and verified. We need to identify which is the weakest arrow in the arrow connection and make a prototype to check if it is not broken. Because "if it's broken, the sooner you realize it, the better." That's what "[It's important to fail fast.
- > [nishio](https://twitter.com/nishio/status/1388418034931363840): Maybe, but you're thinking of asking a mentor to teach you after you've been adopted because you're worried about your AB arrows, but even if you're asking for advice, it's easier to give feedback if you say "I didn't do anything, tell me about it. I'm not doing anything, tell me what you did", it is easier to give feedback if you say "I thought it would be good to do this, but the result was different from what I expected.

> [hiroki_daichi](https://twitter.com/hiroki_daichi/status/1388414059897262082): I often use the summer homework episode. Any suggestions for a good way to phrase it? [[https://note.com/hirokidaichi/n/n1c3b6c8cb58c](https://note.com/hirokidaichi/n/n1c3b6c8cb58c) Working with Uncertainty "What is your summer vacation homework?" | hiroki_daichi (Director, Japan CTO Association / Rector Director)
- > [nishio](https://twitter.com/nishio/status/1388420063196172290): "Summer homework, if you do it from what you're good at, you're left with the things you're not good at, and that's a bit depressing. The analogy of "it's better to do it from what you are not good at first" is good for the atmosphere, but there is no dependency between the tasks. If you put off your weakest free research and don't finish it during the summer vacation, it doesn't invalidate the kanji drills you're good at that you did first.
- > [nishio](https://twitter.com/nishio/status/1388421026430685191): when the arrows are in series, like "make B from A and C from B", if one arrow is broken, the whole thing is ruined. So you need to check the weakest arrow first.

- Duplicate of [[Hypothesis testing lead time]].

---
This page is auto-translated from [/nishio/一番不確実なところを最初に確認する](https://scrapbox.io/nishio/一番不確実なところを最初に確認する) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
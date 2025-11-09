---
title: "Design thinking is a depth-first search?"
---

> I somehow think that in my mind [[logical thinking]] is a breadth-first search, and what is called [[design thinking]] or art thinking is more like a depth-first search, so I feel that if I don't pursue depth, I will end up halfway through the search. Design thinking and art thinking are not exemptions.
[https://twitter.com/kur/status/1259335314721525760](https://twitter.com/kur/status/1259335314721525760)

> I was reminded that this is the opposite of vertical and horizontal, and I thought that it could be taken that way, depending on what is placed as a node. Metaphors are difficult.
> For example, if we focus on [[synthesizing]], we can say that it is depth-first, and if we focus on the [[idea]] ([[brainstorming]]) process, we can say that it is breadth-first search.
[https://twitter.com/kur/status/1259476931365371905](https://twitter.com/kur/status/1259476931365371905)

On the contrary, I was more convinced that [[design thinking]] is [[depth first search (search algorithm in AI)]].
I think the reason I thought that was because what came to my mind when I heard the term "design thinking" was the act of "not exhaustively examining design options, but proceeding quickly to a prototype that can be experimented with anyway.
![image](https://gyazo.com/ceb4ef1e09d0af953599f27b7e6ac1b4/thumb/1000)
- [[Eariest Testable Product]]

However, I realized that this is not a depth-first search, since it does not try to change only the last "design option" in the "next search". I thought it was more like a [[Monte Carlo tree search]], in which the player repeatedly plays until the end of the game in Go AI to judge whether the move is good or bad.

On the other hand, the behavior envisioned by the term "[[logical thinking]]" of "exhaustively considering design alternatives, selecting the best option, and then considering the next option" is also not breadth-first search, because it does not explore the "destination of the option not selected in the first step" in exploring the second option. It's not.

Implicit in the search method here is
- It is possible to know whether an option is good or bad by focusing on only one option (the evaluation function is given).
- Beyond the best-rated stand-alone option, there exists a solution that is better evaluated as a whole."
The assumption is that This is similar to the pre-Monte Carlo chess AI algorithm
![image](https://gyazo.com/adcff1f2bb59832d9c23d58dbb149b31/thumb/1000)

So, to return to the original question, what is "depth" in "if you don't pursue depth, you will end up halfway through"? I interpreted it as "to build a prototype and go as far as getting information about its merits and demerits. Is this what you mean by "if we focus on synthesizing"?

> I wrote this as a depth-first priority since I am also prototyping at first. On the other hand, if you change the scope of your view, there is a Monte Carlo aspect, as Nishio-san says, which I think is similar to breadth-first + branch cutting (especially in the phase of brainstorming and expanding possibilities).
I see, in comparison with Shogi AI, AI has an implicit assumption that "all possible options are known", while humans, due to various biases, can recognize only a part of "[[possible options]]", so we need to expand our options first.
> . But this is also true of logical thinking. It is breaking down the problem and expanding the options that can be taken. Whether that is Monte Carlo-like, putting it out there anyway rather than exhaustive, and then deciding whether it fits into a circle or not, or dividing it up with MECE in mind, I think it is different.
- [[People are only aware of some of the choices they can take.]]
- [[The Limits of Cognition]]



> About if we focus on synthesizing. In design thinking, it is said that how to create a good "[[problem to be solved]]" through interviews and other research is important. I wonder if it can be taken as a depth priority with the "depth" of this question in mind.
> For example, "How can I delay an enjoyable life under coronal influence?" is a shallow question. For example, "How can I spend quality leisure time with friends while maintaining social distance under the corona influence?
> Just that this makes me think that the analogy with logical thinking is rather difficult to draw....

[[kur]]

---
This page is auto-translated from [/nishio/デザインシンキングは深さ優先探索？](https://scrapbox.io/nishio/デザインシンキングは深さ優先探索？) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
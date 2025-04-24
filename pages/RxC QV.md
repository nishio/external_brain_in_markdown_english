---
title: "RxC QV"
---

[RxC QV](https://quadraticvote.radicalxchange.org/)
![image](https://gyazo.com/cf992e481ed2547607d774b8a84bb40e/thumb/1000)

Example implementation of a type of [[Quadratic Voting]] where [[Voice Credit]] does not have a [[Continued Value]].
- Context: [[Quadratic Voting UI Devices]].

Remaining Voice Credit is shown on the right.

![image](https://gyazo.com/c50701d3bb4900313b94ff64b2eb68ef/thumb/1000)

As you increase your vote, that square number of Voice Credit is consumed.
![image](https://gyazo.com/373226ef843241c0ea3aee91f0571fd4/thumb/1000)

This UI will strongly afford you to "use up the credits you are given cleanly".
- It is intended to be used in a way that gives 99 credits for a single voting opportunity, and then the unused ones become worthless when that voting opportunity is over.
- The reason why the number is set at 99 instead of 100 is to destroy the "vote 10 for your favorite candidate" behavior and to elicit the behavior of "I voted 9 for my favorite and now I have a little extra credit, it's a waste, let's put it in the other candidate".
    - I think Audrey Tang wrote about it somewhere.
    - 99-81=18, so the rest is 9+9 or 16+1+1
- The incentive multiplier is the exact opposite of the original Quadratic Voting, where credits have a continuing value.
    - The original QV was designed to "accumulate credits with continuing value and put them together in your interest" as described in [[radical market]].
    - I wonder if the general public has difficulty understanding the concept of credit with continuing value.
    - I understand that this design is more convenient for use in one-off events.

----
- nishio:
    - It's much better than the slider UI, on the other hand, I think this is a UI that affords a one-time use up of voting tokens without [[Continued Value]] and doesn't communicate well the "there's value in saving your vote for something you're not interested in" feature.
- tkgshn: totally
    - Exactly, I'd like to carry over the votes, but it doesn't look like it's ever going to happen...
    - I don't think the "worth saving and not voting for something you're not interested in" trait has been utilized in the past.

---
This page is auto-translated from [/nishio/RxC QV](https://scrapbox.io/nishio/RxC QV) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "UI for Quadratic Voting in Civ6"
---

Example implementation of a type of [[Quadratic Voting]] where [[Voice Credit]] has a [[Continued Value]].
- Context: [[Quadratic Voting UI Devices]].
- Example of a type where Voice Credit has no continuing value: [[RxC QV]].

World Congress of [Civilization VI: Gathering Storm
![image](https://gyazo.com/d35cb1740aff6ea95458d20334a8d819/thumb/1000)

Diplomatic Support" is the equivalent of Voice Credit.
After voting 1 vote at cost 0, additional votes can be added by paying an additional Voice Credit
![image](https://gyazo.com/b3f396ad9a731a6e8d7340c967bdfc92/thumb/1000)

Each additional vote is a temporary function of the additional cost.
So the overall cost is quadratic in the number of votes.
![image](https://gyazo.com/18cd1e6cab26b7ea6b0752d9873c5c03/thumb/1000)

voting results
Players #1 and #4 cast 4 and 5 votes for A. Players #2 and #3 cast their votes for B.
- If it's a [[one vote per person]] vote, it's a tie, but this is Quadratic Voting, so the player who paid the cost and cast the most votes wins.
![image](https://gyazo.com/d395c3ca1a41d9a75518a02d08c2ba68/thumb/1000)

---
This page is auto-translated from [/nishio/Civ6のQuadratic VotingのUI](https://scrapbox.io/nishio/Civ6のQuadratic VotingのUI) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
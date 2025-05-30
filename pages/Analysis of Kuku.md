---
title: "Analysis of Kuku"
---

cuckoo
- Multiplayer game in which you try not to be disqualified or be the last person to be disqualified without knowing the cards held by members other than yourself
    - [[Simplification of existing games]]
    - What kind of game would it be if there were no special cards at all?
        - No more disqualifications due to special abilities
    - To disable card counting, the card is considered a restored extraction.
- The game will be a game where you are randomly given a value from 1 to 10 and you have to think about whether to exchange it to avoid the billiards.
    - Similar to poker in terms of the decision to exchange or not.
- The first person is uninformed, so optimal behavior is determined.
- After that, knowledge of the distribution is gained by the behavior of people up to that point.

python

```
cards = range(10)
from random import choice
count = [0] * 10
worst = [0] * 10
def deal(): return [choice(cards) for i in range(5)]
for i in range(10000):
    d = deal()
    w = min(d)
    for c in d:
        count[c] += 1
        if c == w:
            worst[c] += 1

>>> count
[4946, 4975, 5025, 4993, 4921, 4911, 4863, 5255, 5034, 5077]
>>> worst
[4946, 3271, 2026, 1229, 613, 349, 130, 53, 5, 0]
>>> [w * 100 / c for (c, w) in zip(count, worst)]
[100, 65, 40, 24, 12, 7, 2, 1, 0, 0]
>>> sum(worst) / 50000.0
0.25244
```


- In other words, if five people are randomly given cards 0-9, if the card is 1, the probability of being the last is 65%.
- If you request an exchange, there is no information about the other player's card, so there is an even probability and a 25.2% chance that you will get the billi
- Therefore, the first person should only exchange cards when the probability of billi with no exchange is greater than 25.2%, 0 to 2.
- The best strategy for those who receive cards in exchange is to exchange them further, since they are basically receiving a card with a probability of becoming a billi greater than 25.2%, but there is one exception to this rule.
    - That is, if the "card you had earlier" is smaller. By that information, the conditional probability that the card you now have will be the billiards is 0, so it is optimal not to exchange it.
- Situations other than the above are cases where you are not the first player and the person in front of you has not exchanged.
    - The distribution of the cards is not uniformly distributed by the observed facts up to that point.
    - roughly speaking
        - When a "sudden no-change" occurs, the threshold is raised because there is more information that "the cards that person was dealt were above the threshold."
        - When "no change received with change" occurs, it means "I received a card below the threshold, but the card I had was even smaller," so the threshold goes down.
- If a special card is included, there is a rather good chance of disqualification if you request a replacement. Roughly 3 / 17 ((fool, human, cat) / (other than kuku, horse, house)) or 18%.
    - So the line where it is more profitable to exchange is surprisingly low.
---
This page is auto-translated from [/nishio/ククの分析](https://scrapbox.io/nishio/ククの分析) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
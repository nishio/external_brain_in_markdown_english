---
title: "Average gold volume"
---

One of the measures in [Dominion
Haven't found a clear definition yet.
A value that is the average of the coin value when the deck is composed entirely of coins.
[Reference video](https://www.youtube.com/watch?v=XGl_M-SzhtI&t=267s)
Simple configurations can be solved by human calculation, but when they become complex, it seems that they can't be calculated, so they approximate or give up on the calculation.

Then let's calculate it programmatically.
The simplest way is to do a tally on all permutations of the deck.
- But this would make the computational complexity factorial.
- It takes about 1 second for 11 decks, 12 seconds for 12 decks, and 2-3 minutes for 13 decks ([[Estimating computational quantities]]).
- It's not impossible, but it will take some time.
- Let's try to be a little smarter in our implementation.

Find the COMBINATION of the 5 cards taken from the deck and tally the average of the sum of the coins against it.
python

```
from itertools import combinations


def hand_to_coins(hand):
    return sum([1 for c in hand if c == '1'])


deck = "1111111EEE"
hands = list(combinations(deck, 5))


N = len(hands)
s = sum(hand_to_coins(hand) for hand in hands)

print(N)
print(s/N)
```

In all, there are 252 possible ways (10C5), with an average of 3.5.
- [reference video](https://www.youtube.com/watch?v=XGl_M-SzhtI&t=267s) says the average amount of gold in the initial deck is 0.7.
    - The "average amount of money" in the reference video is "of one card" and I asked for "of the cards in hand", so there is a 5-fold discrepancy.
    - Considering the schedule after this, calculating a single card's would complicate the story, so I want to calculate the cards in hand.
    - I'd prefer a different name for the "average amount of money" in the reference video.
    - What I want to find is "how many coins can be purchased in the purchase phase after a random hand is made and an action is performed," so let's call it "[[Average Purchasing Power]]".
    - If there are only coins in the deck, the average purchasing power is five times the average amount of money, since there is no action.

While organizing, I've also been able to calculate the "probability of purchase" while I'm at it.
python

```
from itertools import combinations


def hand_to_coins(hand):
    return sum([int(c) for c in hand if c in '123'])


def calc(deck, cost=5):
    hands = list(combinations(deck, 5))
    N = len(hands)
    c = sum(hand_to_coins(hand) for hand in hands) / N
    p = sum(1 for hand in hands if hand_to_coins(hand) >= cost) / N * 100
    print(f"{c:.2f}({c/5:0.2f}) {p:.1f}%")


deck = "1111111EEE"
calc(deck)  # => 3.50(0.70) 8.3%
deck += "22"
calc(deck)  # => 4.58(0.92) 53.0%
```

result
- The average purchasing power of the initial deck is 3.5 (0.7 * 5) and the probability of buying 5 gold cards is 8.3
- Buying 2 silver coins gives an average purchasing power of 4.58 (0.92 * 5) and a 53.0% chance of buying a 5 gold card
    - The explanation in the reference video says the average amount of money is 0.917. The difference is because I rounded to two decimal places.

Now we want to calculate what would happen if we bought a blacksmith here.
Execute if there is an action card in hand, only blacksmith for now, and don't consider cards with more actions. (Source code to come later).
result
- Initial deck + silver coins + blacksmith
    - 4.77(0.95) 61.1%
- Initial deck + 2 silver coins + blacksmith
    - 5.29(1.06) 70.6%
        - In the reference video, it's set at 1.058. Rounded off, it's the same.

So far, so consistent with the reference video.
What happens when there are two action cards?
- Initial deck +2 silver coins +2 blacksmiths
    - 5.44(1.09) 79.6%
        - In the reference video, it's set at 1.058. This is the first place where the average purchasing power doesn't match the five times the average amount of money in the reference video.

Let's break down the average purchasing power calculation here
- If there is no blacksmith in hand
    - This is 792 ways of 12c5 since you choose 5 cards from 12 cards excluding the blacksmith, the same average purchasing power as the initial deck +2 silver coins, 4.58.
- If you have two blacksmiths in your hand
    - The remaining 3 cards are chosen from the 12 cards, so 220 ways of 12c3. Six cards are chosen from the final 12, so 6 times the average gold amount of 0.916 for the "initial deck + 2 silver coins", or 5.50
- If you have one blacksmith in your hand
    - If blacksmith 1 is in hand and the remaining 4 cards are selected from 12 cards, there are 495 ways. If blacksmith 2 is in the hand, the same applies, so there are 990 ways.
    - In this case, 7 cards would be selected from 13 cards, including 1 blacksmith card that cannot be used due to lack of action.
    - However, the average amount of money in this case should not simply be multiplied by 7 because 4 cards were selected earlier.
        - That would double count the case where the blacksmith goes into the four cards in your hand first.
        - Consider 8 cards from the 12 cards, removing the 4 cards that went into the hand first.
    - Need to make a case for whether the blacksmith is included in the draw of 3 cards at the blacksmith shop.
        - If not entered, 56 ways to choose 3 from 8, yielding 7 times the average gold amount of 12 0.916
        - If you enter, there are 28 ways to choose 2 out of 8, yielding 6 times the average gold amount of 0.916 for 12 pieces
        - This weighted average of 6.11 is "the average purchasing power when there is only one blacksmith on hand."
- The weighted average of these three streets, 5.44, is the average purchasing power in this case

consideration
- It can be shown that average purchasing power is consistent with this by simulating and converging to this value.
    - As for the average amount of gold, it is unclear what value can be determined by observation, so verification is not possible.
- The discrepancy is probably due to the fact that the values are calculated without the "case by how many blacksmiths are in hand or on the draw," which is required in the calculation of average purchasing power.
    - But you're getting stronger with that value.
    - So the difference between 1.09, which is 1/5 of the average purchasing power, and 1.058, which is the average amount of gold, is not important in getting stronger
        - Well, it's about 1/30th the value of a copper coin.
        - In other words, average gold volume is an approximate calculation method of average purchasing power
- It is easier to calculate average purchasing power when using a computer.

2022-02-21
Chapel Compression and Average Purchasing Power
- Initial deck 1111111eee
    - 3.50(0.70) 8.3%
- Suppose you bought a chapel c and a 5-cost card X
    - If the chapel is with 3 houses of worship, eeee1c
        - Discard four cards, 111111cX
            - 3.75(0.75) 10.7%
        - If only the mansion is discarded, 1111111cX
            - 3.89(0.78) 16.7%
    - ee11c when it comes out with 2 houses.
        - Discard 4 cards and you get 11111ecX
        - 3.12(0.62) 1.8%
        - 111111ecX
        - 3.33(0.67) 4.8%
        - 1111111ecX
        - 3.50(0.70) 8.3%
    - e111c
        - 1111eecX
        - 2.50(0.50) 0.0%
        - 11111eecX
        - 2.78(0.56) 0.8%
        - 111111eec2X
        - 3.64(0.73) 21.9%
    - 1111c
        - 111eeec
        - 2.14(0.43) 0.0%
        - 1111eeec
        - 2.50(0.50) 0.0%
        - 11111eeec
        - 2.78(0.56) 0.8%
        - 111111eeec2
        - 3.64(0.73) 21.9%
It's always better to leave the coppers in terms of average purchasing power, so the effect of [[rotational force]] doesn't make sense unless it's quantified.


- [[Blacksmith Stello Simulation]]
---
This page is auto-translated from [/nishio/平均金量](https://scrapbox.io/nishio/平均金量) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
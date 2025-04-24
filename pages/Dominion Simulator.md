---
title: "Dominion Simulator"
---

![image](https://gyazo.com/37579a6e315db28f82db5110b5551343/thumb/1000)
Based on [Optimal BigMoney Strategy [http://wiki.dominionstrategy.com/index.php/Big_Money#Big_Money_Optimized](http://wiki.dominionstrategy.com/index.php/Big_Money#Big_Money_Optimized)
- I had the computer play it 100,000 times and tallied the results.
    - Setting up that your opponent does not do anything that affects you.
    - They don't attack, they don't buy victory points.
- Graph of how many coins will be in the purchase phase of each turn
- After 10 turns, the deck begins to be diluted by buying victory points and the average slowly drops.
    - Average at this time is around 7

I drew it on the violin chart, but then I realized that what I really want to know is not the distribution, but the probability of getting 8 gold or more.
- Probability (in percent) that the vertical axis will be 8 gold or more
- ![image](https://gyazo.com/73e3d6db82d5d370c20acd9014040edb/thumb/1000)![image](https://gyazo.com/d22dbb9f7d9d952652ca74b6de584607/thumb/1000)
    - Right: Effect of chapel compression
        - A graph of what happens if you buy a silver coin and a chapel, and in the worst case scenario where the chapel came with 4 copper coins in the second round, what happens if you destroy the 4 copper coins?
        - It is true that the coins on hand are drastically reduced, which slows down the early legs of the game, but the turnover is so fast that it is reversed by turn 9.
            - However, because of its fast turnover, it is also quickly contaminated by victory point cards.
        - Note that this graph does not show actions taken on the second and subsequent appearances of the chapel.
            - One card that is not a treasure is in the box, and that's the only way to treat it.
    - ![image](https://gyazo.com/37579a6e315db28f82db5110b5551343/thumb/1000)![image](https://gyazo.com/c812a0e6f3dc5a7458e003fa581b75de/thumb/1000)



Next time, let's make a case for two and four people to take away the winning point.
- Maybe the fast diminishing of gensets will cause the behavior of "buying gensets and mansions instead of silver coins", which will lead to even faster dilution.

Let's do a comparison next time when we change the number of blacksmiths in the forge stero.

---
This page is auto-translated from [/nishio/Dominion Simulator](https://scrapbox.io/nishio/Dominion Simulator) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
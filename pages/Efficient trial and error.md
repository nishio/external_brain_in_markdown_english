---
title: "Efficient trial and error"
---

2017-09-05
For "[[Problems for which there are no correct answers in the textbooks]]," it is necessary to find the answers by [[trial and error]] on your own.
But there are two types of trial-and-error: efficient and inefficient trial-and-error.

Question 1
There are 64 coins, only one of which is a fake coin and weighs differently than the other 63. There is no means of measuring the weight at hand, only a "balance scale" that can be used as a means of comparing the size of the weights. How do we find the fake coin?

explanation
Since there is nothing in the textbooks about "which are the counterfeit coins," you have to find the answer yourself through repeated trial and error with the balance. There are several possible ways to do this.
There are several levels of quality in the answer to this question.
- Finding answers in specific cases
- You can find "a way to find the answer in every case."
- Can find multiple "ways to find the answer in any given case" and determine which is more efficient

Method 1
Compare coins 1 and 2 on a balance. (A) If the balance does not tip, both 1 and 2 are authentic. By comparing the remaining coins with coin 1, we can find coins of different weights. (B) If the balance tilts when comparing coins 1 and 2, then one of the coins is a fake. From the condition "only one of the coins is a counterfeit coin," we know that all the rest are real coins, so we can compare the weights of coin 1 and the real coin.

Method 2
Place the same number of coins on the balance, and if it tilts, there is a fake coin in the balance, and if it does not tilt, there is no fake coin. This is used to perform a binary search. (The abstract concept "binary search" is applied to this concrete problem.)
Place 32 coins on the balance, 16 at a time. If the balance tilts, then there is a fake coin among the 32 coins placed on the balance; if it does not, then there is a fake coin among the 32 coins not placed on the balance. The same method can be repeated to narrow down to 16 coins, 8 coins, 4 coins, 2 coins, etc. After narrowing down to 2 coins, one of the coins can be determined by comparing it with the coin that we know is the correct coin.

Method 3
In this problem, there is a "lack of knowledge" that exists: we only know that the weights of the fake coins are different, and we do not know whether they are heavier or lighter. There is a possible way to solve this head first: put the 32 coins on the balance, 16 at a time, after identifying the 32 on the side with the fake coins. This would reveal whether the fake coins are heavier or lighter.
If the false coin is heavier, the remaining candidates can be placed on the balance 1/3 at a time. When tilted, the false coin is in the lower 1/3, and when balanced, the false coin is in the 1/3 that was not placed on the balance. 32 coins, then 11 coins, then 4 coins, and so on, narrowing down the number of coins; from 4 coins, each one can be placed on the balance one move at a time, with a 1/2 probability of identifying it in one move, and a 1/2 probability of identifying it in two moves.

Comparison
Method 1
- There is a 2/64 chance that the balance will tip. At that time, it will be fixed in two moves.
- The probability of 62/64 is balanced, and the remaining 62 coins are to be compared to 1 coin. It takes an average of 31 moves to finalize.
- A little over 30 moves on average.
Method 2
- You can narrow it down to 32 in 1 hand, 16 in 2, 8 in 3, 4 in 4, and 2 in 5. 6 moves to finalize.
Method 3
- Multiply by 2 to narrow down the number to 32 and identify whether the false coin is heavy or light.
- Add one real coin to make 33, divide into 11 coins each, and compare. 3 hands, 11 coins.
- Add one real coin to make 12, then divide into four coins to compare, four in each of four hands.
- After narrowing it down to four pieces, it can be identified in an average of 1.5 moves.
- It can be fixed in 5.5 moves on average. And even in the worst case, it is not worse than Method 2, since it takes 6 moves.

Development problem It becomes instantly more difficult when there are multiple fake coins.
- Cases with two fake coins, both known to be heavy.
- Case of two fake coins, not known to be heavy or light, but the two coins weigh the same.
- Cases where two counterfeit coins may weigh the same in total as two real coins
- A case of not knowing how many fake coins there are.
Various development issues are possible.

relevance
    - [[Fake Coin Puzzles]]

---
This page is auto-translated from [/nishio/効率の良い試行錯誤](https://scrapbox.io/nishio/効率の良い試行錯誤) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
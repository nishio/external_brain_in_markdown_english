---
title: "Efficiency of coin search"
---

- [[Fake Coin Puzzles]]

[http://d.hatena.ne.jp/nishiohirokazu/touch/20120111/1326272867](http://d.hatena.ne.jp/nishiohirokazu/touch/20120111/1326272867) 2011

Software engineers' claim that "engineers are 10 times more productive depending on their abilities" is considered by non-engineers to be "too much of a bluff, how is that possible, stupid?

- Q1: I have 80 coins, with one slightly heavier fake coin mixed in. I want to find it using a balance.
- A1: The Rustic Way
    - Place one coin on one side of the balance and one coin on the other side of the balance, and if one of the plates drops, the coin on that plate is false
    - 1-79 comparisons find fake coins.
- A2: A little better
    - Take two coins each and place them on either side of the balance.
    - 1-40 comparisons find fake coins.
- A3: A slightly smarter way
    - 80 coins are divided into 40 coins each and placed on the left and right sides of the balance. The 40 coins on the lowered side are found to contain fake coins.
    - The 40 coins are divided into 20 pieces each and placed on the left and right sides of the balance. The 20 coins on the lowered side are found to contain false coins.
    - Twenty coins are divided into 10 pieces each and placed on the left and right sides of the balance. The 10 coins on the lowered side are found to contain false coins.
    - Ten coins are divided into five pieces and placed on each side of the balance. The five coins on the down side are found to contain false coins.
    - Since 5 is an odd number, we add one more coin, divide it into three pieces, and place them on the left and right sides of the balance. The three coins on the down side are found to contain false coins.
    - Since 3 is an odd number, add one more coin, divide it into two pieces, and place them on the left and right sides of the balance. The two coins on the down side are found to contain false coins.
    - Two coins are placed one on each side of the balance. The coin on the lower side is the false coin.
    - Seven comparisons find false coins.
    - This is called [[dichotomous search]], a method known to any engineer who has studied algorithms
- A4: A smarter way
    - 80 coins are divided into three parts, 27,27,26, and 27 coins are placed on each side.
        - If it tilts, there is a false coin on the one that went down. If it does not tilt, there are false coins on the 26 that were not placed.
    - Trisect the 27 coins into 9 pieces each and place 9 pieces on each side.
    - Divide the nine coins into three equal parts of three coins each and place them on each side.
    - Divide the three coins into three equal parts and place one on each side.
    - Fake coins are found on the 4th floor comparison.
- Thus, the amount of work required to find a fake coin can vary more than tenfold depending on how well it is done.

Q2: I have 80 coins, with one fake coin mixed in that weighs slightly different. I want to find it using a balance.
- It is necessary to notice that the problem conditions have changed from Q1.
- Notice that the "divide by 3" method used to solve Q1 cannot be used.
    - If the plate were to be divided into three parts and placed on either side and the plate lowered, it would not be possible to tell which plate has the fake coins because it is unclear whether the fake coins are heavier or lighter.
- what if so
    - The ability to think and arrive at this on one's own is required.
- In this case, if the balance tilts, we know that the fake coins are on either the right or left side, so we can divide the 80 coins into 20, 20, and 40 and place 20 coins on each of the left and right plates. The tilt or no tilt will narrow down the location of the fake coins to 40 coins.
    - In other words, a slight transformation can be attributed to the A3 method

Q3: I have 80 coins, two, slightly heavier fake coins mixed in. Assume that the weights of the counterfeit coins are the same. How do we find them using a balance?
- The difficulty level jumps when there is more than one thing to look for.
- Put 40 pieces on each side of the balance,
    - Case 1: Tilt has two false coins in its forty
    - Case 2: If not tilted, there is one false coin in each of the 40 pieces on both the left and right sides.
    - In case 1, do the same, placing one half on each side of the balance.
    - Case 2 can be attributed to method A4 since there is one false coin.

Q4: I have 80 coins, with one or more slightly heavier fake coins mixed in. Assume that the weights of the counterfeit coins are the same. How do we find them using a balance?
- The difficulty is further increased by the fact that the number of items to look for is unknown.
- Hey me too, I don't immediately know what the best way to do this is in this case.
- When a problem is too complex, consider smaller problems first.
    - If there are two coins and you do not know how many of them are fake coins, place them on the balance one at a time.
    - In case of a tilt, the one that goes down is the false coin.
    - If no tilt, both fake coins or both real coins.
    - If there is a condition of "at least one false coin out of two," it would be determined to be "both false coins," but if it is two out of 80, that condition is not expected.
    - If tipped, 1 real coin, 1 fake coin, and 78 coins containing zero or more fakes.
    - If not tilted, 1 pair of 2 real or fake coins, 78 coins containing 0 or more fake coins
- Not the best solution, but a solution for now.
    - Divide the 80 sheets into 40 pairs of 2 sheets each and place each pair on the balance.
    - With high probability, there is one or more pairs that are split into real and fake (if not, consider later).
        - By comparing one of the pairs that were not split with a real coin, you can tell if the pair is real or fake.
        - After 40 comparisons, the worst 39 comparisons can identify all of them.
    - If all of them are paired
        - Divide those pairs into 20 pairs and place one pair on the balance.
        - If you tilt it, you can tell the heavier side is the false pair.
        - With high probability, there is one or more pairs that split into genuine fake pairs (if not, consider later).
            - As before, comparisons can be made to identify whether a pair that did not separate is real or fake.
            - After 40 comparisons, 20 comparisons, and then the worst 19 comparisons, we can identify them all.
        - If not split
            - Divide into 10 pairs of 8 pieces each and place 2 pairs (4 pieces) on the balance.
            - If more than 1 pair is split, same as last time.
            - If not split, 5 sets of 16 cards each
            - If they still do not separate, divide into 32, 32, 16, and compare the 32 cards with each other.
            - If they are still not separated, we are left with 64 cards and 16 "all real or all fake" cards and 16 unknown cards, so we compare 16 of the 64 cards with the 16 unknown cards.
            - The side that went down is false.
            - If it is balanced, it is confirmed to be "all fake". (Because "all are genuine" is impossible based on the condition that there is at least one fake.)
            - The number of comparisons in this case is 40 + 20 + 10 + 5 + 1 + 1 + 77
                - So, the procedure is complicated, but the worst 79 comparisons of any route will find the fake coin.
- A solution that looks a little smarter.
    - Divide the 80 sheets into 40 pairs of 2 sheets each and place each pair on the balance.
    - Once the tilting pair X is discovered, the subsequent balances can be compared two by two
        - We know that if it is heavier than X, both are fake coins, if it is lighter, both are real coins, and if they are balanced, one each.
        - With the method described above, the case of "both fake coins" and "both real coins" could not be determined without two comparisons: "compare once, balance, and then compare again against one of them," but with this method, the case of "both fake coins" and "both real coins" is determined with a single comparison.
        - Instead, the "one fake real one each" case, which was fixed once, needs to be fixed twice.
        - No matter what the probability p of the existence of a fake is, the probability $p^2 + (1-p)^2$ of "both fake or both real" is greater than the probability $2p(1-p)$ of "one fake real each", so this is probabilistically less frequent
        - $p^2 + (1-p)^2 - 2p(1-p) = (p - (1-p))^2 = (2p-1)^2 \geq 0$
        - I don't think the number of worst case scenarios will change...
        - If we're going to discuss expected values, we should discuss what is equally probable in the distribution of inputs...

Q5: I have 80 coins, with one or more fake coins of slightly different weights mixed in. Assume that the weights of the counterfeit coins are the same. How do we find them using a balance?
- When you see this question, you must realize that you cannot solve it due to a lack of problem conditions.
- If there are 40 heavy fake coins, the lighter one is the real one; if there are 40 light fake coins, the heavier one is the real one, but the balance cannot identify which of these is the correct answer.
- It cannot be solved unless the problem conditions include a condition such as "real coins are more numerous than fake coins".

---
This page is auto-translated from [/nishio/コイン探しの効率](https://scrapbox.io/nishio/コイン探しの効率) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "memorandum"
---

- Infer information that cannot be observed only by you from the behavior of others [[game]].
        - Similar to [coyote (carnivore, Canis latrans)
- There are one 1 to seven 7s.
- It depends on the number of players, but for 4 players, 5 cards in hand, 4 cards in the field, and 4 cards face down.
- Only you can't see the cards in your hand.
- Declare one number each turn.
- If the declared number is in your hand, it opens one card.
[https://boku-boardgame.net/domemo](https://boku-boardgame.net/domemo)

When fighting a typical person, it is possible to have a better chance of winning if you play ignoring everything (except level 1) rather than trying to guess from the opponent's behavior.
- Unless you take notes, which I don't do in the basic playstyle of this game, you're going to have to rely on your memory of [[flesh and blood]].
- Using information from someone else's point of view is computationally complex.
- High risk of confusion trying to do something complicated.

Level 1 play briefly explained
- First check the frequency of the numbers on the field to see how many you don't see.
    - It's seven numbers, so think of it as a phone number and you should be able to remember it.
    - The higher this number, the more likely it is to exist in your hand.
    - in order of precedence
        - If any, reduce by 1
        - If no, set to 0
- The frequency of being on the field can be restored by re-counting, even if it is forgotten.
    - It is necessary to memorize the information about which number you said was the wrong number, because it is not left in the field.

Level 2 Play
- Use information from other people's perspectives
    - After doing the first frequency count on level 1
    - For example, if the number of 1's left from your point of view is 1 and someone else says "1" and it is a hash.
        - If the number of 1's remaining is not 0 in the eyes of others, then there is no 1 in your hand.
        - That is, the number of 1's left.
    - As for 1, it's obvious, but as for 4-7, you need to discount the information because you don't know if your opponent is playing level 1 properly or if he's just confused and saying random things.
        - If your opponent is playing level 1, for example, if you have two 7s left and one 6, and he chooses a 6, the probability that you have a 7 in your hand that he can see increases, but most people are not that reliable.

- Decent level 2 play
    - At the start, if you have 4 face-down cards and 5 cards in your hand, you have $_9C_5=126$ street possibilities.
        - It can be smaller than this because of overlapping numbers.
    - At first, all of those possibilities are equally probable.
    - If the opponent says "1" (a), the probability is reduced by the inference that "the probability of doing that in case x would be low" for "event x in which your hand contains 1".
        - $P(x|a) \propto P(a)P(a|x)$
            - [[Bayesian update]]
    - In this way, the conditional probability conditional on all observations is updated for each additional observation.
    - As for your own hand, just ask for the probability of the existence of 7 different numbers and say the one with the highest probability.
- Programmatically, it's easy, but a flesh-and-blood human being would have difficulty holding 128 values in memory and multiplying each one.
[[Domemo]]

---
This page is auto-translated from [/nishio/ドメモ](https://scrapbox.io/nishio/ドメモ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "Multiple options for diminishing returns"
---

- A common design pattern in [[cookie clicker]]-like [[reproduction on an enlarged or expanded scale]] games.
- [[Design that eliminates obvious optimal solutions]].
- [[Multiple Choice]] to [[diminishing harvest]].

For example, in a game design of extended reproduction in which "spending coins to level up function X increases the amount of coins earned per unit of time," the "amount of coins earned" should remain fixed and the "amount of coins spent to level up" should increase. The yield per investment amount will diminish. If there are multiple functions X, Y, and Z to level up, leveling up only certain functions will result in diminishing returns for those functions, so it is necessary to level up in a balanced manner.

The reason that a good balance is not obvious is due to the cognitive limitation that players do not do the math. If you do the math, there is a self-evident optimal solution, since all you have to do is take the option that maximizes the "increase in harvest per investment (ROI)": if an investment of 10 improves harvest by 1, and an investment of 100 improves harvest by 11, the latter has a higher ROI.

To confuse this further, the move to stagger harvest timing is often used: an alternative in which 10 investments improve harvest by 2 for every 2 unit hours versus an alternative in which 10 investments improve harvest by 1 for every 1 unit hour, the latter is preferable. This is because the timing of when the harvest becomes available is faster, and therefore the harvest can be reinvested sooner, generating a compounding effect. This effect is calculated by [[discounted present value]], but I wonder if there are people who calculate that much when playing cookie-cutter games...

Furthermore, in the case of "harvesting occurs once every minute, and the amount of harvesting can be increased by investment," the timing of harvesting will affect the optimal behavior. In the long run, "right A, which increases the harvest by 10 every 10 minutes," becomes "right A, which increases the harvest by 1 per minute. However, if the timing of the harvest is one minute away, investing in it now will increase the harvest by 10 per minute in the short term. Even if "Right B, which increases the harvest by 20 per 10 minutes" can be purchased for the same amount of money, if the timing of the harvest is 2 minutes away, it is more profitable to first buy Right A and then wait for the harvest that will be available 1 minute later to buy Right B.

Moreover, investment is nonlinear. In other words, when "pay 10 and you get right A," paying 9 will not get you 90% of the rights. By choosing the most useful investment option that is in front of you now, the amount of money should not be insufficient for the options that will appear in the future.

Oh, that one, when you think about it, the strategy isn't obvious, even for a simple cookie-cutter.

-----

There are devices A, B, and C that generate 1 resource every 2, 3, and 5 unit hours (hereafter seconds). The acquisition cost of those devices is 1, and the amount generated can be increased by +1 by paying an additional cost. The additional cost required is 1,2,3,5,8,13,.... and so on, increasing in Fibonacci. That is, if A pays 1 to acquire A and then pays 6 additional, A generates a harvest of 4 every 2 seconds. At time 0, the player has 1 resource.

Q1: What is the play that would maximize the amount of resources owned at time 100
Q2: What is the play that would have the fastest time to achieve 100 resources?
Additional question: any difference between Q1 and Q2? Also, can you say anything interesting when 100 is the general N?

The play that maximizes the amount of resources owned at time 1 is "do nothing."
The two plays that maximize the amount of resources owned at time 2 are "do nothing" or "buy A at time 0 and receive 1 at time 2". Any other choice is not maximum because it is 0. To express the latter succinctly, we use `0:A`.
The maximum resources owned at time 3 are "do nothing", `0:A`, and `0:B` with a maximum of 1.
The maximum resource at time 4 is `0:A` with a maximum of 2.

'AAAA_A____'
'AAAA______'
t=0, pay 1 to get Lv1, 1. t=1, pay 1 to get Lv2, 2. t=2, pay 2 to get Lv3, 3. t=3, pay 3 to get Lv4, 4. 1 rest, get 4, 8. If you pay 5 next turn to get Lv 5, it takes 5 turns to recover it, so the investment is just barely recovered, so it is the same whether you invest or not.

---
This page is auto-translated from [/nishio/収穫逓減する複数の選択肢](https://scrapbox.io/nishio/収穫逓減する複数の選択肢) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
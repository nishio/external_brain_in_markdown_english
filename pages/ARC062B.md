---
title: "ARC062B"
---

[D - AtCoDeer-kun and Weird Rock-Paper-Scissors](https://atcoder.jp/contests/arc062/tasks/arc062_b)
- ![image](https://gyazo.com/b60e8ec2eed92697d14a8aff9e4790c9/thumb/1000)
- Thoughts.
    - I think we can get it to a draw (that's not what they asked).
    - Let's call the excess number of goos a charge.
    - If you don't have a charge, you have to play goo.
        - At this time, the charge is 1.
    - When there is a charge, you can choose your hand.
    - When the opponent plays par and thereafter only plays goo
        - If you make a goo, -1 point, +1 charge
            - Unless the charge exceeds the number of goo of the opponent, all pars are played and points are scored for the charge.
        - Draw with par.
            - Gain one less charge point.
        - Therefore, it is always better to make par
    - So you should charge so that you can par when your opponent pars.
    - Check the amount you can use because overcharging is a loss because you can't use it all.
        - And by usable quantity, I mean the number of words left.
    - When the opponent plays par, you play par; when the opponent plays goo, you play goo; and when the charge equals the number of letters remaining, you play all the remaining pars and use them up.
    - If the opponent doesn't do the stupid thing of making an extra charge, the point difference becomes zero and the game is a draw, which is what I was vaguely thinking when I wrote the first line.
- Official Explanation
    - First think about what happens if you make all goo, then think about what happens when you change one spot to par.
        - Since the score increases regardless of the opponent's hand at this time, we conclude that it is better to make as many pars as possible.
        - Alternate and keep the charge small.
- consideration
    - I think the strategy is different between "use up the charge before the end" and "don't let the charge build up," but the result is the same.

---
This page is auto-translated from [/nishio/ARC062B](https://scrapbox.io/nishio/ARC062B) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
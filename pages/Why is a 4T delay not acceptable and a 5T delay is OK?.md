---
title: "Why is a 4T delay not acceptable and a 5T delay is OK?"
---

final answer
- ![image](https://gyazo.com/fc3a742e76230062f9cd5d3905635191/thumb/1000)

-----
from  [[Automatic sorter with adjustable number of storagesdraft]]
Why is a 4T delay not acceptable and a 5T delay is OK?
9/5
Why is a 4T delay not acceptable and a 5T delay is OK?
Lipita 5T delay + Torch 1T delay + Torch reversal 5T delay equivalent
- Possibility 1
    - 2T after dropper on, it enters hopper 1, moves to 2, 3 every 4T, and the upper hopper stops when it enters 3.
        - ![image](https://gyazo.com/35abb9faa17a98bddfd5e9988ba8faee/thumb/1000)
        - 1T early sucks.
        - This interpretation assumes immediate smoking when the hopper is turned on
            - But [[Experimental notes with unfamiliar results]] negates that.
            - But if we affirm this experiment, there's no way the sorting machine can run at a 5T clock, so maybe there's some difference we're not aware of.
mystery
    - [[Both the dropper and hopper run on one tick.]]
9/8 Mystery solved.
- [https://twitter.com/nishio/status/1435426297279234048?s=21](https://twitter.com/nishio/status/1435426297279234048?s=21)
- > Droppers turned on by torches propagate signals around them, causing neighboring hoppers to stop temporarily
I completely understand.
- Flow when working correctly with a 5T delay.
    - ![image](https://gyazo.com/fc3a742e76230062f9cd5d3905635191/thumb/1000)
    - Dropper stops adjacent hopper 1 and does not flow to hopper 2 until it is turned off
    - When you reach hopper 3, 4 has stopped, so wait until 4 starts moving again.
    - The wait is long enough so you can chest here as well.
- Flow when 4T delay does not work correctly.
    - ![image](https://gyazo.com/a19b51b4b7d3e842a619b31209b774bd/thumb/1000)
    - The 4 is still moving when it reaches hopper 3, so it sucks.
    - And the next tick after that, it sucks to 5.
    - As a result, all items end up in the lower chest.
To reiterate, let me reorganize.
- ![image](https://gyazo.com/d90ce6af13428ce4787f1e6c42b96cca/thumb/1000)
- DL is a dropper for flow limitation purposes
    - Put a 5 on 5 off signal in phase with hopper H4 in DL
    - If we extend H1 to H3, we delay 4T per hopper, so we accelerate the DL clock by that amount.
- This phase alignment is very important
    - If DL is 1T early, everything will be in C3.
- No signals in H3.
- DE is a dropper elevator, which can be clocked as fast as 2 on 2 off
- LC is Large Chest
    - Fast item elevator sinks are buffered here.
    - You can put items directly here.
        - If the height is low, that's quicker.
    - Item elevators can be added later when they are expanded.
        - Direction of expansion is down
    - If you use a fast clock for the item elevator, the dropper will get stuck when you put a lot of stuff in without a buffer.
        - Elevators that assume that only one thing can fit in the bottom dropper will stop without feeding the item all the way through.
![image](https://gyazo.com/5c2727e36ab1c2b57cbdb95c7cd0e0ca/thumb/1000)
![image](https://gyazo.com/055dbf71f193b8b998449a49fe2a204a/thumb/1000)
![image](https://gyazo.com/e54cf34bafda37454baa8113ce73af15/thumb/1000)


confirmation required
- Does the dropper stop the hopper even when it is on with powder?
    - If not, adjustments must be made.
    - [https://scrapbox.io/files/613965d780613f001d7794b6.mp4](https://scrapbox.io/files/613965d780613f001d7794b6.mp4)

- Experiment 1 Powder, Dropper, Hopper, Powder ON in hopper
    - If the hopper stops, it won't go into the second hopper.


5 stories
![image](https://gyazo.com/ad2c61af2efc724c933b9d09e7f37af9/thumb/1000)
![image](https://gyazo.com/6e7a0d9c54c1c831aa37c0f07417ff47/thumb/1000)
![image](https://gyazo.com/17aff6091eefa8705cee711c9b107620/thumb/1000)

Now, let's build with survival.
Where shall I put it, I'll line the walls of this house with chests.
- ![image](https://gyazo.com/9a47f3c916e577e0c73781288b26e4ec/thumb/1000)

I was a little unsure whether to extend it horizontally or backward, but this time I extended it horizontally for ease of access to the chest of inputs. When I want to expand it, I may change it to extend it backward.
- ![image](https://gyazo.com/522993e752c0143c51d862cca10c00ab/thumb/1000)

Wiring is a bit difficult because they are lined up on the wall. Since we can't go around, we need to move up and down the scaffold. It is not impossible.
- ![image](https://gyazo.com/e465af1433d85fde8ea2133afc9e72b1/thumb/1000)

As it was finished, the contents of the old automatic sorting machine were transferred, but it was impossible to put what was 12 chests of quicksand into 5 chests. We expanded it by two chests at the bottom.
- ![image](https://gyazo.com/3cd6c63d90e4b47d40135f1df646395b/thumb/1000)

The old automatic sorting machine has been dismantled.
![image](https://gyazo.com/d5022f06d57ad4fa5de3c6743e6319e6/thumb/1000)

The problem of noisy ticking when a signal enters an empty hopper was solved by adding a switch here.
- ![image](https://gyazo.com/6fb5e4fd5affda922b56d007b851fabc/thumb/1000)

Sorting through the chests, there are still a lot of vegetables. They were transported by hopper from the automatic farm to the automatic sorting machine, but I think it would be better to sort them around the farm and sell them to farmers in the area instead of bringing them here in the first place.
![image](https://gyazo.com/cd234c1b00b02965e7954ce2380c50f3/thumb/1000)

---
This page is auto-translated from [/nishio/なぜ4T遅延だとダメで5T遅延だとOKなのか？](https://scrapbox.io/nishio/なぜ4T遅延だとダメで5T遅延だとOKなのか？) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
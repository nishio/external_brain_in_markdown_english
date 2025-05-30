---
title: "Sending messages to individual sprites in Scratch"
---

One-line summary:.
- The binary display could be created by "giving each sprite a different ID, sending a message to each sprite to set an individual value, sending the value to all the sprites, and each sprite reacting based on its own value.
    - ![image](https://gyazo.com/a914f4edcdbf6b6f59488eb562ede450/thumb/1000)

Tweet in the process of making
- Scratch does not have classes, but it does have instances in the form of sprites, which can be cloned.
- There is an event handler that is called when cloned, so the equivalent of a constructor argument can be read from the global here.
- Although sprites are not first-class objects, they can point to a specific instance by creating a unique ID using a global variable.
- Messages are broadcast, but if you put a global destination variable and only sprites that match your ID respond to it, you can do the same thing as a destination-specified message.
- (I misunderstood when I saw that only one lamp was lit.) The message, if one is received and processed, is not conveyed to the others... I thought it would be conveyed to all of them...
    - Oh, no, this is different, because the division is not integer division, so you need ROUND.
    - flooring
- It's done.
    - ![image](https://gyazo.com/8d2dac85692149dbf2ba5a8ba1b6c918/thumb/1000)
    - ![image](https://gyazo.com/c735a5e3c31b692e97de6a5eb1d264ae/thumb/1000)
    - ![image](https://gyazo.com/a914f4edcdbf6b6f59488eb562ede450/thumb/1000)
from [[Scratch]]

---
This page is auto-translated from [/nishio/Scratchで個別のスプライトにメッセージを送る](https://scrapbox.io/nishio/Scratchで個別のスプライトにメッセージを送る) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
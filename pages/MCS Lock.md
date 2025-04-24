---
title: "MCS Lock"
---

- stimulation-free
    - Definite execution after a finite number of steps.
    - = Not "if you're unlucky, you'll have to wait endlessly."
- Those who wait have Node.
    - next: Node*
    - wait: boolean
- There is a pointer tail pointing to the "end of column", initially null
- People who want to get in line swap pointers to the tail and their own node atomically.
    - If the result of the swap is null, you know you are at the top of the queue.
        - Locked out.
        - Process.
    - If not null, you know who is in line in front of you, so you make their .next a pointer to yourself.
    - Wait until the value of wait becomes false
- If next is not null, next.wait is set to false if next is not null for those who have finished processing.




---
This page is auto-translated from [/nishio/MCS Lock](https://scrapbox.io/nishio/MCS Lock) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
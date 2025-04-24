---
title: "Scrapbox token/page"
---

![image](https://gyazo.com/69fca986e181b322019ad629a109187f/thumb/1000)![image](https://gyazo.com/e742c246b4f6d26315f4d35243c7c821/thumb/1000)
How much would tokenize Scrapbox with [[cl100k_base]]?
- The original data is in this Scrapbox, page 14178.
- Less than 1% of the 8192 tokens do not fit
    - OpenAI's [[Embedding API]] can take up to 8192 tokens, so most pages can be embedded in their entirety.
- Majority shorter than 500 tokens
    - I decided to separate only those longer than that into 500 tokens each.
:
| total | 14178 |
| -- | -- |
| < 8192 | 14092 |
| < 500 | 9344 |

---
This page is auto-translated from [/nishio/Scrapboxのtoken/page](https://scrapbox.io/nishio/Scrapboxのtoken/page) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "2024-09-17 vector search stopped ✅."
---

from  [[Diary 2024-09-17]]
2024-09-17 Vector search stopped.
Tried to search for "many eyes can find the bug."
    - [[Lots of eyes make it easier to identify bugs.]]

Vector search API is down.
- Let's reboot.

---
Qdrant is Healthy
Vercel front end is ok.
500 error in /api/search
- The output in the event of an error is too long to see the key error message. w

I'm wondering if the Embedding API spec has changed, based on the behavior.

----
`error Error [AxiosError]: Request failed with status code 429`
- Too Many Requests
- What? What do you mean?
    - I've looked at Usage and there doesn't seem to be anything particularly unique about it.


2024-09-23
![image](https://gyazo.com/d59b43aa5d4cc2c8621ebd4aaab07b39/thumb/1000)
- I figured it would be something like that.

Conclusion.
- Credit Card A expire at the end of July.
- The ChatGPT subscription was in error, so I added the newer Card B information.
- But for API Billing, "2 credit cards are registered, default is A".
- Due to a difference in billing timing, the API's ran and failed on 9/5, retried 3 days later, and then stopped using the API a short time later.
- Past due bill was paid, card B was defaulted and then card A information was deleted.

---
This page is auto-translated from [/nishio/2024-09-17ベクトル検索止まってる✅](https://scrapbox.io/nishio/2024-09-17ベクトル検索止まってる✅) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
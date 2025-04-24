---
title: "Decimal decimal arithmetic error"
---

> [@KoizumiJp](https://twitter.com/KoizumiJp/status/1631586998749384709): decimal decimal arithmetic can be used as default and numeric binary operators can be used in context (in scope) as float treatment. I want a language. The [[IEEE754]] trap is too difficult for beginners and I don't think it will motivate them. Also, it would be perfect if it could handle rational types and irrational numbers (if it goes that far, I may have to step into a math processing system).

> [@mkashi](https://twitter.com/mkashi/status/1631786058169073664?s=46&t=fcl5teS9Ae2uzfzsSf5-uA): Decimal numbers have their own fears, for example, if we have an environment with 5 significant digits in decimal If we assume that x=5000.3 and y=5000.4, and we calculate the average of (x+y)/2, we get 10000.7 added together, 10001 rounded off since it is 5 significant digits, and 5000.5 divided by 2, which is outside the interval between the original numbers. This does not happen with binary numbers.

The story is that the decimal system is not free from strange behavior caused by [[measurement error]], because the error does not disappear just because it is decimalized.

---
This page is auto-translated from [/nishio/十進数小数点演算の誤差](https://scrapbox.io/nishio/十進数小数点演算の誤差) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
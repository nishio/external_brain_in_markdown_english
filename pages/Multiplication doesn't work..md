---
title: "Multiplication doesn't work."
---

ts

```typescript
 type m_MUL<
   REV_N extends DIGITS,
   REV_M extends DIGITS,
   POWER extends DIGITS | [],
   > = (
     ADD<
       mm_MUL<REV_N, REV_M[0], POWER>,
       {
         0:
 
         m_MUL<REV_N, REV_M[1], [0, POWER]>,
         // Type instantiation is excessively deep and possibly infinite.
 
         1: [0, []]
       }[REV_M[1] extends DIGITS ? 0 : 1]
     >
   )
```

![image](https://gyazo.com/c32b85bbbfb3b869d830de09b38b21ba/thumb/1000)



---
This page is auto-translated from [/nishio/掛け算がうまくいかない](https://scrapbox.io/nishio/掛け算がうまくいかない) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
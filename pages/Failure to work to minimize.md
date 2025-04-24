---
title: "Failure to work to minimize"
---

I wanted to minimize to know the cause of Type instantiation is excessively deep and possibly infinite. but it was not possible to make any branches and leaves

ts

```typescript
type DIGIT = 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9;

type DIGITS = [DIGIT, []] | [DIGIT, DIGITS]

type REVERSE<N extends DIGITS, S = []> = (
  N[1] extends DIGITS
  ?
  // REVERSE<N[1], [N[0], S]>
  { 0: REVERSE<N[1], [N[0], S]> }[N extends any ? 0 : 0]
  : [N[0], S]
)

type ADD<
  N extends DIGITS, M extends DIGITS,
  REV_N = REVERSE<N>, // Erasing these two lines will not reproduce
  REV_M = REVERSE<M>, // 
  > = (
    any
  )

type m_MUL<
  REV_N extends DIGITS,
  REV_M extends DIGITS,
  > = (
    {
      0: ADD<any, any>
      // Type instantiation is excessively deep and possibly infinite.

      1: [0, []]
    }[REV_M[1] extends DIGITS ? 0 : 1]
  )
```


ts

```typescript
type DIGIT = 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9;

type DIGITS = [DIGIT, []] | [DIGIT, DIGITS]

type REVERSE<N extends DIGITS, S = []> = (
  N[1] extends DIGITS
  ?
  // REVERSE<N[1], [N[0], S]>
  { 0: REVERSE<N[1], [N[0], S]> }[N extends any ? 0 : 0]
  : [N[0], S]
)

type m_MUL<
  REV_M extends DIGITS,
  > = (
    REVERSE<REV_M> // OK
    // REVERSE<REV_M> // NG
  )
```


ts

```typescript
type DIGIT = 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9;

type DIGITS = [DIGIT, []] | [DIGIT, DIGITS]

type REVERSE<N extends DIGITS, S = []> = (
  N[1] extends DIGITS
  ?
  // REVERSE<N[1], [N[0], S]>
  { 0: REVERSE<N[1], [N[0], S]> }[N extends any ? 0 : 0]
  : [N[0], S]
)

type ADD<
  N extends DIGITS, M extends DIGITS,
  REV_N = REVERSE<N>, // Erasing these two lines will not reproduce
  REV_M = REVERSE<M>, // 
  > = (
    any
  )


type m_MUL<
  REV_N extends DIGITS,
  REV_M extends DIGITS,
  POWER extends DIGITS | [],
  > = (
    {
      0:
      ADD<
        REV_N,

        m_MUL<REV_N, [0, []], [0, []]>
      >
      // OK

      1: [0, []]
    }[REV_M[1] extends DIGITS ? 0 : 1]
  )
```


[[circularly references itself]]

---
This page is auto-translated from [/nishio/最小限にする作業の失敗例](https://scrapbox.io/nishio/最小限にする作業の失敗例) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
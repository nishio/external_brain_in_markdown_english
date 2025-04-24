---
title: "Odd types in TypeScript"
---

- [[TypeScript types]]
> Can I define, for example, "with an id consisting of alphanumeric characters only" in TypeScript type information? [src](https://twitter.com/wtnabe/status/1252119742069891073)
I saw that, and I wondered how to do that, so I looked it up and made a note of it.

I think this kind of need is, in essence, using existing String as a data structure in [[Structural typing]] TypeScript, but restricting the range of values, and wanting to give a different name to the set of values, or Nominal Typing.

I looked it up in Nominal Typing and found it right away.
[Nominal Typing - TypeScript Deep Dive](https://basarat.gitbook.io/typescript/main-1/nominaltyping)

It is simple enough to introduce a member for type distinction and to eliminate structural incompatibility.
I used this explanation to create an odd-numbered type.

ts

```typescript
interface Odd extends Number {
  _OddBrand: boolean;
}
interface Even extends Number {
  _EvenBrand: boolean;
}

var odd: Odd;
var even: Even;

// Expected Type Errors
// odd = even;  // NG
// even = odd;  // NG
// odd = 1;  // NG

const assertOdd = (x: number): Odd => {
  if (x % 2 === 1) {
    // @ts-ignore
    x._oddBrand = true;
    // @ts-ignore
    const ret: Odd = x;
    return ret;
  }
  throw AssertionError;
};

var x = assertOdd(1);
odd = x;  // OK
// even = x;  // NG
```


Some people may find it "tougher than expected".
`odd = 1` results in a type error.
As in this example, if you think "it's a number, but it's obviously odd," you can just assert it.
If this ASSERT is incorrect, an assertion error will occur at runtime.

---
This page is auto-translated from [/nishio/TypeScriptで奇数型](https://scrapbox.io/nishio/TypeScriptで奇数型) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
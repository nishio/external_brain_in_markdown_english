---
title: "Considerations on how to expose objects"
---

2021-06-28 Currently this method is not used
    - [[Expose ReactN]]

2019-12-10
from  [[Interactive implementation in TypeScript]]
Considerations on how to expose objects
- [[Implemented interactively with TypeScript#5def2f3aaff09e000025a837]] is a style that puts "code to expose the subject" in one place
    - Look at the target file, check "this is it", EXPORT, and then edit another file.
- Conversely, you can prepare a "function that takes an argument and exposes it" and call it near each target you want to expose.
- Which is better.
- Is it easier to manage if they are all in one place?
    - And the code to expose variables is scattered after all...
        - There is also a way to create a variable in the module scope first and export it, even if the code exposes a local variable.
- Is it better to have a "function that takes an argument and exposes it", so that the intent is clearer than a simple assignment?
- I made it up as I went along.
ts

```typescript
export const makeGlobal = (name: string, obj: any) => {
  // @ts-ignore
  window.debug[name] = obj;
}
```

- But this may not be a good idea, because if the code is not used for anything other than exposing the target, it will be considered an unused module.
- Also errors such as `ReferenceError: Cannot access 'makeGlobal' before initialization`.
- I decided not to go deeper this time.

---
This page is auto-translated from [/nishio/オブジェクトを露出させる方法に関する考察](https://scrapbox.io/nishio/オブジェクトを露出させる方法に関する考察) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
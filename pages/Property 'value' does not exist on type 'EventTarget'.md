---
title: "Property 'value' does not exist on type 'EventTarget'"
---

ts

```typescript
const onKeyPress: KeyboardEventHandler<HTMLTextAreaElement> = (e) => {
    // console.log(e.target.value)
    // Property 'value' does not exist on type 'EventTarget'
    // why?
    const target = e.target as HTMLTextAreaElement;
    console.log(target.value)
    // OK
}

```


---
This page is auto-translated from [/nishio/Property 'value' does not exist on type 'EventTarget'](https://scrapbox.io/nishio/Property 'value' does not exist on type 'EventTarget') using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
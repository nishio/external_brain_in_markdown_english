---
title: "Validate Runtypes"
---

Until now, when a user tried to import a JSON file, the only thing we could do was "if isTItem is false, display invalid item" for each item to be imported.
- When I moved to [[Runtypes]], "what is false due to a mismatch" was in the DETAILS.
- It would be nice to show this to the user so they can easily see what's wrong with that JSON.

ts

```typescript
  const result = RTItem.validate({
    type: "kozane",
    position: [],
    id: "A",
    text: "A",
  });
  if (!result.success) {
    console.log(result.details);
  }
```

:

```
 console.log
   {
     position: 'Failed constraint check for [number, number]: Expected length 2, but was 0',
     scale: 'Expected number, but was missing'
   }
```


---
This page is auto-translated from [/nishio/Runtypesのvalidate](https://scrapbox.io/nishio/Runtypesのvalidate) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
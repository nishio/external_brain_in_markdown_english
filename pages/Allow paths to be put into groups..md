---
title: "Allow paths to be put into groups."
---

from [[pRegroup-done-2019]]
Allow paths to be put into groups.
- If this can be done, hand-drawn diagrams can be grouped together.
- Missed hit point when lassoing the entire path -> FIXED
- The pass goes to the group.
- Error when moving → FIXED
ts

```typescript
 TypeError: Cannot read property 'add' of undefined
  31 |   const newPosition = item.position.add(diff);
```

    - cause
            - [[Recursively update the position of child elements of a group]]
            - This modification will cause groups that include paths to have a conflict between updates to the path itself and updates to its location,
            - The system needs to be modified to fit the current system around updating the path location.
            - →done

---
This page is auto-translated from [/nishio/パスをグループに入れられるようにする](https://scrapbox.io/nishio/パスをグループに入れられるようにする) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
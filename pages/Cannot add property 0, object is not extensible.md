---
title: "Cannot add property 0, object is not extensible"
---

js

```javascript
foo = []
Object.freeze(foo)
foo.push(1)
// Uncaught TypeError: Cannot add property 0, object is not extensible
```

Happens when trying to push against a frozen Array

Specific Occurrence Situations
![image](https://gyazo.com/3bf53b670627bf0743ac495b6d3137d6/thumb/1000)
So why was it frozen?

The selected element is being put into [[ReactN]] and then frozen when it is taken out. Kindly designed to prevent inadvertent destructive updates and a nasty bug.

When grouping the selected ones, this is what was written, which is wrong
ts

```typescript
  const group = new GroupItem();
  group.items = g.selected_items;
```

This will cause the new group to have a reference to the frozen object itself, and then when you try to add to that group, you will get the above error.

ts

```typescript
  group.items = [...g.selected_items];
```

This is what I should have done.

---
This page is auto-translated from [/nishio/Cannot add property 0, object is not extensible](https://scrapbox.io/nishio/Cannot add property 0, object is not extensible) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
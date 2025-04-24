---
title: "cannot compile namespaces when the '--isolatedModules' flag is provided"
---

- [[React]] [[TypeScript]]
- Automatic '--isolatedModules' flag when [create-react-app
- I get this error when I create a new ts file.
- This is because this file does not export anything.
    - Not appropriate as a module, just namespaces
    - Error messages are difficult to understand

approach
typescript

```typescript
let Foo;
export default Foo;
```

If you write something like "I'm not sure if this is a module or not," it will take the appropriate form as a module for the time being.
Replace it later when the correct "what should be exported" is available.

---
This page is auto-translated from [/nishio/cannot compile namespaces when the '--isolatedModules' flag is provided](https://scrapbox.io/nishio/cannot compile namespaces when the '--isolatedModules' flag is provided) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
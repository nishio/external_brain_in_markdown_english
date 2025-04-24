---
title: "Expose ReactN"
---

2021-06-28
- No need to manage global values yourself, let ReactN do it for you.
- Only the interface for reading and writing values needs to be exposed.

Previous Discussions
    - [[Add a new property to the window with TypeScript]]
    - [[Considerations on how to expose objects]]

ts

```typescript
import { getGlobal, setGlobal } from "reactn";

const movidea = {
  setGlobal,
  getGlobal,
};

const debug = {};

declare global {
  interface Window {
    debug: any;
    movidea: typeof movidea;
  }
}

export const initializeGlobalVariables = () => {
  window.movidea = movidea;
  window.debug = debug;
};
```



---
This page is auto-translated from [/nishio/ReactNを露出する](https://scrapbox.io/nishio/ReactNを露出する) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
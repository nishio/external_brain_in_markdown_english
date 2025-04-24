---
title: "Make a change diff and setGlobal"
---

- [ReactN useGlobal can fire even if the reference does not change.
In other words, if the entire object is passed to setGlobal, all hooks will be triggered and redrawn.
After thinking for a while about how to deal with it, I realized that passing the entire object is a case of making a destructive update by creating a whole draft in immer, so I changed my own utility function updateGlobal for that purpose to a "make change diff and update" mechanism.

before
ts

```typescript
import { State } from "reactn/default";
import { setGlobal } from "reactn";
import { produce } from "immer";

export const updateGlobal = (update: (g: State) => void) => {
  // update global variable in destructive manner using immer
  setGlobal((g: State) => {
    return produce(g, update);
  });
};
```


after
ts

```typescript
import { State } from "reactn/default";
import { setGlobal } from "reactn";
import { produce } from "immer";

export const updateGlobal = (update: (draft: State) => void) => {
  // update global variable in destructive manner using immer
  setGlobal((current_state: State) => {
    const new_state = produce(current_state, update);
    const update_delta: { [key: string]: unknown } = {};
    Object.entries(current_state).forEach(([key, ref]) => {
      // @ts-ignore
      if (current_state[key] !== new_state[key]) {
        // @ts-ignore
        update_delta[key] = new_state[key];
      }
    });
    return update_delta;
  });
};
```


before / after
![image](https://gyazo.com/8daea14561c18aa4c85a9e22d8905b5e/thumb/1000)![image](https://gyazo.com/2378a32ec9295a85dff707a096f7615a/thumb/1000)
A simple mousedown that took 120ms to redraw the entire screen is now only 4.8ms for the necessary part.

---
This page is auto-translated from [/nishio/変更差分を作ってsetGlobalする](https://scrapbox.io/nishio/変更差分を作ってsetGlobalする) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
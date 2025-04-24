---
title: "Reduxing"
---

Is it something like this. [[Redux]]+[[TypeScript]].

ts

```typescript
import { createStore } from 'redux';
...

export const initialState = {
	...
};

export type StateType = typeof initialState;

enum ActionType {
  SET_ITEMS = "SET_ITEMS",
}

export const setItems = (items: StateItem[]) => {
  return { type: ActionType.SET_ITEMS, payload: items }
}

interface Action {
  type: ActionType;
  payload: any;
}

function rootReducer(state = initialState, action: Action) {
  switch (action.type) {
    case ActionType.SET_ITEMS:
      return { ...state, items: action.payload };
    default:
      return state;
  }
}

export const store = createStore(rootReducer);
```


[[pRegroup-done-2019]]

---
This page is auto-translated from [/nishio/Redux化](https://scrapbox.io/nishio/Redux化) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
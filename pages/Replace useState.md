---
title: "Replace useState"
---

from  [[Test asynchronous React state updates]]
Replace useState

If you are setValue in a component, you will be warned if this is not wrapped in act
- Related: [[Wrapping in act in React tests is not render but state update]]

output

```
console.error
    Warning: An update to MyAsyncComponent inside a test was not wrapped in act(...).
    When testing, code that causes React state updates should be wrapped into act(...):
...
      15 |       console.log(6);
    > 16 |       setValue(x);
         |       ^
```


One simple solution is to prepare an "act implementation that does nothing", use it in the body code, and replace it with the real one only during testing, but I don't want to do this for some reason, so I will replace the useState.

MockUseState.ts

```typescript
import React, { Dispatch, useCallback } from "react";
import { act } from "@testing-library/react";
import { useState as originalUseState } from "react";

export const mockUseState = () => {
  return jest.spyOn(React, "useState").mockImplementation((arg?: unknown): [
    unknown,
    Dispatch<unknown>
  ] => {
    const [s, dispatch] = originalUseState(arg);
    const wrappedDispatch = useCallback(
      (arg: unknown): void => {
        act(() => {
          dispatch(arg);
        });
      },
      [dispatch]
    );
    return [s, wrappedDispatch];
  });
};
```

updated 2021-03-12

test.tsx

```
let m_mockUseState: jest.SpyInstance<[unknown, React.Dispatch<unknown>], []>;
beforeEach(() => {
  m_mockUseState = mockUseState();
});
afterEach(() => {
  m_mockUseState.mockRestore();
}); 
```


---
This page is auto-translated from [/nishio/useStateを差し替える](https://scrapbox.io/nishio/useStateを差し替える) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
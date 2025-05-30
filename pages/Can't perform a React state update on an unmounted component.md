---
title: "Can't perform a React state update on an unmounted component"
---

from  [[Jest Memo]]
Can't perform a React state update on an unmounted component
2021-03-09
- > Warning: Can't perform a React state update on an unmounted component. This is a no-op, but it indicates a memory leak in your application. To fix, cancel all subscriptions and asynchronous tasks in a useEffect cleanup function.
- When testing in batches, you may get a state update warning after the component is unmounted, which seems to indicate that the test case is terminating without waiting for the asynchronous update to complete.
2021-03-11
- I've been working on eliminating async from the event handler, but the problem of updates occurring after unmounting has not been resolved, so I'm not sure what's going on.
2021-03-12
- [React state update on an unmounted component | Code, Thoughts & Opinions - By Sagiv Ben Giat](https://www.debuggr.io/react-update-unmounted-component/)
    - I've looked at sample code that reproduces the same problem, but even if I comment out the similar parts, it still reproduces the problem, so I'm trying to create a minimal reproduction code by removing the code that reproduces the problem, but something completely unexpected is affecting it, and I'm wondering what it could be.
    - I understand the workaround and why it only occurs here, but I'm not sure I understand the principle of the problem.
        - workaround: change `useGlobal()` to `useGlobal("foo")`.
- I thought, "I see, I must not have done the useEffect cleanup in ReactN!" So I read the source and found that I had done it...
    - I'm not sure if the cleanup is going well due to the mock tangle...
- What we know for now
    - It's not the asynchronous updates that are delaying the updates after unmounting.
    - The component is about to be updated after unmounting at the beginning of the next test case where the values are initialized
        - It only happens in the test environment and does not affect the process, just a warning.
        - This is why it only happens when multiple test cases are run
- To prevent this, there is a known method to flag the useEffect cleanup so that it will not be updated any further
    - [React state update on an unmounted component | Code, Thoughts & Opinions - By Sagiv Ben Giat](https://www.debuggr.io/react-update-unmounted-component/)
    - ReactN uses useEffect internally.
    - But they're also doing cleanup.
- The cleanup itself is called for in the ReactN implementation!
- The reason the warning is reproduced even if the read result is not used for drawing is because the getter is monitored.
        - [[ReactN's useGlobal monitors get]]
ts

```typescript
// Happen
const [g] = useGlobal()
console.log(g.foo);
return null;
// Not Happen
const [g] = useGlobal()
return null;
```

- Why are there two update listeners attached, is this correct behavior?
- Why is an update listener added with setGlobal?
    - And I'm not sure what the purpose of the code is to be added here.
    - I read the code and can't figure out why the addition is happening.
    - And this listener is not released when the component is unmounted, so it leaks across test cases.
- Component redraw is triggered by setGlobal
    - monitor get on redraw, and again the addition of the update listener runs
    - At this time, the listener is identical, so the expected behavior is not to increase by adding
    - Additional increase because they are not actually identical.
    - Cleanup only deletes the last one.
- In the test code of ReactN itself, the listeners are indeed identical
    - So what I've done is cause the listeners to lose their identity.
- If MockUseState is stopped (although the act warning will still appear), this warning will no longer appear.
- The update listener is [use-force-update
    - [https://github.com/CharlesStover/use-force-update/blob/master/src/use-force-update.ts](https://github.com/CharlesStover/use-force-update/blob/master/src/use-force-update.ts)
use-force-update.ts

```typescript
import { useCallback, useState } from 'react';

// Returning a new object reference guarantees that a before-and-after
//   equivalence check will always be false, resulting in a re-render, even
//   when multiple calls to forceUpdate are batched.

export default function useForceUpdate(): () => void {
  const [ , dispatch ] = useState<{}>(Object.create(null));

  // Turn dispatch(required_parameter) into dispatch().
  const memoizedDispatch = useCallback(
    (): void => {
      dispatch(Object.create(null));
    },
    [ dispatch ],
  );
  return memoizedDispatch;
}
```

    - This returns the second return value of useState with useCallback
- [doc](https://reactjs.org/docs/hooks-reference.html)
    - > React guarantees that setState function identity is stable and won’t change on re-renders. This is why it’s safe to omit from the useEffect or useCallback dependency list.
    - > [[useCallback]] will return a memoized version of the callback that only changes if one of the dependencies has changed.
    - Which means it's guaranteed to be identical no matter how many times it's called.
- My code on the other hand
MockUseState.ts

```typescript
import React, { Dispatch } from "react";
import { act } from "@testing-library/react";
import { useState as originalUseState } from "react";

export const mockUseState = () => {
  return jest.spyOn(React, "useState").mockImplementation((arg?: unknown): [
    unknown,
    Dispatch<unknown>
  ] => {
    const [s, setS] = originalUseState(arg);
    return [
      s,
      (arg: unknown) => {
        act(() => {
          setS(arg);
        });
      },
    ];
  });
};
```

    - Okay, this is going to return something different for every call.
    - Let's [[useCallback]] in the same way as use-force-update
ts

```typescript
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

- Yay, the test finally passed without warning!

---
This page is auto-translated from [/nishio/Can't perform a React state update on an unmounted component](https://scrapbox.io/nishio/Can't perform a React state update on an unmounted component) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "Test asynchronous React state updates"
---

So far:.
- 1:  [[Wrapping in act in React tests is not render but state update]]
- 2:  [[When updating the state with the result of a Promise, it is not possible to wrap the entire Promise in an act]]

I would like to test code in Jest where a new Promise is created by an event raised by the user, and then a React state update is performed on that then.
- For example, "When a user clicks a button, network access is performed and the result is drawn.
- Even if the network access part is replaced by a mock, it will still be asynchronous by Promise.

In such situations, the approach of "waitFor until the expected element appears" is known, but with this approach, it is not possible to test the B side in cases such as "if the network response is A, show the menu; if B, don't show it. We need a way to know when redrawing is complete due to state update.

Try it with a simple component. The `userTrigger` returns using Promise. (This is foreshadowing)
ts

```typescript
import { useState } from "react";
export type TUserTrigger = () => void;
export type TResolve = (value: number) => void;
export let userTrigger: TUserTrigger;
export let resolve: TResolve;

export const MyAsyncComponent = () => {
  const [value, setValue] = useState(0);
  userTrigger = () => {
    return new Promise<number>((res) => {
      resolve = res;
    }).then((x) => {
      setValue(x);
    });
  };
  return <span>{value}</span>;
};
```


The test scenario is "0 when first drawn, 0 immediately after the user triggers it, and 1 when the Promise is resolved".
The following writing style will fail.
ts

```typescript
test("MyAsyncComponent1", async () => {
  render(<MyAsyncComponent />);
  expect(screen.getByText("0")).toBeTruthy();

  userTrigger();
  expect(screen.getByText("0")).toBeTruthy();

  resolve(1);
  expect(screen.queryByText("0")).toBeNull(); // fails
  expect(screen.getByText("1")).toBeTruthy();
});
```


The execution of then after resolve is always asynchronous, so the only way to guarantee that the line below it will be executed after the execution of then is to connect or await with then to the Promise that was created.
(I moved it to a separate page because there was an example here earlier [Asynchronous It just happened to work, but it's inappropriate.)

The following writing allows (2) to test the state after the asynchronous update caused by the user operation performed in (1) is completed
ts

```typescript
test("MyAsyncComponent1", async () => {
  ...
  render(<MyAsyncComponent />); 
  ...
  const p: Promise<unknown> = userTrigger();  // (1)
  ...	
  resolve(1);
  ...
  await p;
  ... // (2)
});
```


To wrap updates in setValue with act [[Replace useState]].
In the code below, after console.log goes out in order from 1 to 11, 2 to 4, or "redrawing components" runs, and then 12 is displayed.
MyAsyncComponent.tsx

```
import { useState } from "react";
export type TUserTrigger = () => Promise<unknown>;
export type TResolve = (value: number) => void;
export let userTrigger: TUserTrigger;
export let resolve: TResolve;

export const MyAsyncComponent = () => {
  console.log(2);
  const [value, setValue] = useState(0);
  console.log(4);
  userTrigger = () => {
    console.log(6);
    return new Promise<number>((res) => {
      console.log(7);
      resolve = res;
    }).then((x) => {
      console.log(10);
      setValue(x);
    });
  };
  return <span>{value}</span>;
};
```

My.test.ts

```typescript
import React, { Dispatch } from "react";
import { act, render, screen } from "@testing-library/react";

import { MyAsyncComponent, resolve, userTrigger } from "./MyAsyncComponent";
import { useState as originalUseState } from "react";

test("MyAsyncComponent1", async () => {
  jest.spyOn(React, "useState").mockImplementation((arg?: unknown): [
    unknown,
    Dispatch<unknown>
  ] => {
    console.log(3);
    const [s, setS] = originalUseState(arg);
    return [
      s,
      (arg: unknown) => {
        console.log(11);
        act(() => {
          setS(arg);
        });
      },
    ];
  });
  console.log(1);
  render(<MyAsyncComponent />);
  console.log(5);
  expect(screen.getByText("0")).toBeTruthy();

  const p: Promise<unknown> = userTrigger();
  console.log(8);
  expect(screen.getByText("0")).toBeTruthy();

  resolve(1);
  console.log(9);
  expect(screen.getByText("0")).toBeTruthy();

  await p;
  console.log(12);
  expect(screen.getByText("1")).toBeTruthy();
});
```


Now, we can control the process flow as expected. I was going to end with "happily ever after," but...
> `userTrigger` returns using Promise. (This is foreshadowed by)

When creating a Promise in an event handler or useEffect, the Promise cannot be returned to the test code as a return value.
- useEffect specifies that "the return value is a cleanup function" [doc](https://reactjs.org/docs/hooks-effect.html#example-using-hooks-1).
- `fireEvent.click` is a `(element: ...) => boolean`.

I can think of two options.
- Export the created Promise itself
- Cut out the part that creates the Promise into a function, export it, mock it with jest, and extract the return value.

I do the former because the latter is a pain in the ass, but I guess it's a matter of taste.
Next time: [[Export Promise created with useEffect]].

---
This page is auto-translated from [/nishio/非同期なReactの状態更新をテストする](https://scrapbox.io/nishio/非同期なReactの状態更新をテストする) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
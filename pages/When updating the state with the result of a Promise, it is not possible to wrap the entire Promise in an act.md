---
title: "When updating the state with the result of a Promise, it is not possible to wrap the entire Promise in an act"
---

Based on the premise, [[Wrapping in act in React tests is not render but state update]], then what happens when this state update is asynchronous?

Last time, setValue was called directly in the test code, but this time it will be called in the Promise then called `asyncUpdate`.
For example, the results of network accesses and IndexedDB reads are often in Promise form. Even if they are replaced by mocks during testing, they are still Promises, so asynchronous state updates are performed in this way.

This fails the test.
test.tsx

```
test("MyComponent2", async () => {
  type TSetState = React.Dispatch<React.SetStateAction<number>>;
  let setValue: TSetState | undefined;
  const exportSetValue = (s: TSetState) => {
    setValue = s;
  };
  const asyncUpdate: Promise<number> = new Promise((resolve) => {
    resolve(1);
  });

  render(<MyComponent exportSetValue={exportSetValue} />);
  expect(screen.getByText("0")).toBeTruthy();
  expect(setValue).toBeTruthy();
  act(() => {
    asyncUpdate.then((x) => setValue!(x));
  });
  expect(screen.queryByText("0")).toBeNull(); // fails
  expect(screen.getByText("1")).toBeTruthy();
});
```


And the warning `Warning: An update to MyComponent inside a test was not wrapped in act(...)' that I got the last time I didn't wrap in `act`. . ` appears again.
You're rapping, right? What are you talking about? You might think, "I'm not sure," but the essence of the problem is that this code does not wrap properly.

Review Promise behavior.
[Promise - JavaScript | MDN](https://developer.mozilla.org/ja/docs/Web/JavaScript/Reference/Global_Objects/Promise)
- > Note that promises are guaranteed to be asynchronous. Thus, an action on a promise that has already been "resolved" will be executed only after the stack has been cleared and a clock tick has elapsed. This effect is very similar to setTimeout(action,10)

In other words, `setValue` is called outside of `act` as per the order of `console.log` in the code below.
ts

```typescript
console.log(1);
act(() => {
  console.log(2);
  asyncUpdate.then((x) => {
    console.log(5);
    setValue!(x);
  });
  console.log(3);
});
console.log(4);
expect(screen.queryByText("0")).toBeNull(); // fails
```


Then what to do is to wrap the `setValue` directly with `act` and `await asyncUpdate.then`. The test will now pass without warning.
test.tsx

```
test("MyComponent3", async () => {
  ...
  await asyncUpdate.then((x) => {
    act(() => {
      setValue!(x);
    });
  });
  expect(screen.queryByText("0")).toBeNull(); // OK
  expect(screen.getByText("1")).toBeTruthy();
});
```


When I saw this `await`, I thought, "Hey, what if I put `await' on `act'?" I tried it and got a friendly warning that `act doesn't return promises, so don't await'.
ts

```typescript
  await act(() => {
    asyncUpdate.then((x) => setValue!(x));
  });
```

warning

```
Warning: Do not await the result of calling act(...) with sync logic, it is not a Promise.
```


It is also possible to write it in a simple way without using async / await. The logic is the same.
Jest doc:[Promises](https://jestjs.io/docs/ja/asynchronous#promises) [Async/Await](https://jestjs.io/docs/ja/asynchronous#asyncawait)
- > In these cases, async and await are effectively sugar-coating syntax for the same logic as in the examples using promise.

test.tsx

```
test("MyComponent4", () => {
  ...
  return asyncUpdate
    .then((x) => {
      act(() => {
        setValue!(x);
      });
    })
    .then(() => {
      expect(screen.queryByText("0")).toBeNull(); // OK
      expect(screen.getByText("1")).toBeTruthy();
    });
});
```


Now that we understand the principle of what should be done in the case of asynchronous `setValue` by `Promise`.
What is the next problem to solve?
If we consider the scenario "when a user clicks a button, network access is performed to display the result", the code that Promise `setValue` is often a lumped event handler on the side of the body code, not in the test code.
It is not practical to modify this body code and wrap the `setValue` in `act`.
What are we going to do now? I'll continue with the next article.
ts

```typescript
test("MyComponent5", async () => {
  ...
  const userEventHandler = () => {
    asyncUpdate.then((x) => {
      setValue!(x);
    });
  };

  render(<MyComponent exportSetValue={exportSetValue} />);
  expect(screen.getByText("0")).toBeTruthy();
  expect(setValue).toBeTruthy();

  userEventHandler(); // Here
  expect(screen.queryByText("0")).toBeNull(); // fails
  expect(screen.getByText("1")).toBeTruthy();
});
```


- [[Test asynchronous React state updates]]

---
This page is auto-translated from [/nishio/Promiseの結果で状態更新する場合、全体をactで包んでもダメ](https://scrapbox.io/nishio/Promiseの結果で状態更新する場合、全体をactで包んでもダメ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
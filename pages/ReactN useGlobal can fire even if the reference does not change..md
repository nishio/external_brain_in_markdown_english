---
title: "ReactN useGlobal can fire even if the reference does not change."
---

Below is the "code that changes the value of y when the button is pressed.
Component Comp1 is `useGlobal("x")` and expects to be redrawn only when x changes.
However, I note that an unexpected code caused an unexpected redraw.

ts

```typescript
const TestApp = () => {
  console.log("render TestApp");
  return (
    <div>
      <Comp1 />
      <Comp2 />
    </div>
  );
};
const Comp1 = () => {
  const [x] = useGlobal("x");
  console.log("render Comp1");
  return <span>{x}</span>;
};
const Comp2 = () => {
  const onClick = () => {
    console.log("onClick");
    // !!HERE!!
  };
  return <button onClick={onClick}>update y</button>;
};

```


ts

```typescript
// NG: Redrawn
setGlobal((currentState) => ({ ...currentState, y: "hello" }));
// NG: Redrawing when nothing is updated
const currentState = getGlobal();
setGlobal(currentState);
// OK
setGlobal({y: "hello"});
```

In other words, even if the same reference is set, it is judged to have been updated.
- [https://github.com/CharlesStover/reactn/blob/f4eb2fc4a3c616a7d0b6a0ff2c0f299784dc5826/src/global-state-manager.ts#L196](https://github.com/CharlesStover/reactn/blob/f4eb2fc4a3c616a7d0b6a0ff2c0f299784dc5826/src/global-state-manager.ts#L196)

You might think I wouldn't write the former (because in this example, it's not necessary).
I stepped on this issue when trying to update with immer when State is complex. It takes the entire State and creates and returns an object with only what it wants to update. So it takes the value that is not updated and returns an object that holds the value `{ . . currentState, y: "hello"}` which also holds the value that is not updated.

- [[Make a change diff and setGlobal]]

---
This page is auto-translated from [/nishio/ReactNのuseGlobalは参照が変化しなくても発火しうる](https://scrapbox.io/nishio/ReactNのuseGlobalは参照が変化しなくても発火しうる) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
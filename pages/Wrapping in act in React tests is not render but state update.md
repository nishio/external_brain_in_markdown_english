---
title: "Wrapping in act in React tests is not render but state update"
---

When testing components written in React with [[Jest]] + [[React Testing Library]], it was difficult to understand asynchronous state updates and rendering behavior, so I created a small sample to check.

First, create a component that has a value in React's `useState` and just displays it.
`props.exportSetValue` is a callback to expose `setValue` to the test code side.
MyComponent.tsx

```
import { useState } from "react";

export const MyComponent = (props: {
  exportSetValue: (
    setValue: React.Dispatch<React.SetStateAction<number>>
  ) => void;
}) => {
  const [value, setValue] = useState(0);
  props.exportSetValue(setValue);
  return <span>{value}</span>;
};
```


Successful test case 1. the first 5 lines are for retrieving `setValue`.
The test scenario is "render, confirm that 0 is displayed, `setValue(1)`, confirm that 1 is displayed.
The point to note is that the `render` in (1) is not wrapped in `act` and the `setValue` in (2) is wrapped in `act`.
test.ts

```typescript
test("MyComponent1", () => {
  type TSetState = React.Dispatch<React.SetStateAction<number>>;
  let setValue: TSetState | undefined;
  const exportSetValue = (s: TSetState) => {
    setValue = s;
  };

  render(<MyComponent exportSetValue={exportSetValue} />);  // (1)
  expect(screen.getByText("0")).toBeTruthy();
  expect(setValue).toBeTruthy();
  act(() => {
    setValue!(1);  // (2)
  });
  expect(screen.queryByText("0")).toBeNull();
  expect(screen.getByText("1")).toBeTruthy();
});
```


The description of [act()](https://ja.reactjs.org/docs/testing-recipes.html#act) includes the following sample code, but it is extremely misleading.
sample.ts

```typescript
act(() => {
  // render components
});
// make assertions
```

The explanatory text says that both user events and renders are units.
- > When writing UI tests, you can think of tasks such as rendering, user events, data retrieval as "units" of interaction with the user interface. The helper act() provided by react-dom/test-utils ensures that all updates related to these "units" are processed and reflected in the DOM before you make any assertions.

The warning that comes up when `setValue` is not wrapped in `act` is more sane.
- > When testing, code that causes React state updates should be wrapped into act(...)
    - "Code that causes React state updates should be wrapped in `act`."
    - The reason why you don't need to wrap the `render` in this example is that it doesn't cause a state update
    - In the sample code included in this warning message, the comment in the content of act is not `// render components` but `/* fire events that update state */`.
        - Shouldn't the documentation side be aligned with us?

full warning:
output

```
Warning: An update to MyComponent inside a test was not wrapped in act(...).
    
    When testing, code that causes React state updates should be wrapped into act(...):
    
    act(() => {
      /* fire events that update state */
    });
    /* assert on the output */
    
    This ensures that you're testing the behavior the user would see in the browser. Learn more at https://reactjs.org/link/wrap-tests-with-act
        at MyComponent (/Users/nishio/keicho-webclient/src/MyComponent.tsx:8:29)

      52 |   // act(() => {
    > 53 |   setValue!(1);
         |   ^
```


I'm going to get down to business here, but I'll split it up into separate pages.
- [[When updating the state with the result of a Promise, it is not possible to wrap the entire Promise in an act]]
---
This page is auto-translated from [/nishio/Reactのテストでactで包むのはrenderではなく状態更新](https://scrapbox.io/nishio/Reactのテストでactで包むのはrenderではなく状態更新) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "It wasn't replaced by just.spyOn."
---

When replacing React.useState in just.spyOn, it was not replaced because of `import React, { useState } from "react";`.

It is very useful when writing tests to be able to replace the process with just.spyOn, but if you use it with a vague image of "replace," you may think you have replaced the process, but you haven't. It is necessary to understand the module mechanism properly.


Short code to reproduce the phenomenon
MyComponent.tsx

```
import React, { useState } from "react";

export let setValue: React.Dispatch<React.SetStateAction<string>>;
export const MyComponent = () => {
  const [value, _setValue] = useState("foo");
  setValue = _setValue;
  return <span>{value}</span>;
};
```


Foo.test.tsx

```
import React from "react";
import { MyComponent, setValue } from "./MyComponent";
import { render, screen } from "@testing-library/react";

test("foo", () => {
  render(<MyComponent />);
  screen.getByText("foo");
  setValue("bar");
  screen.getByText("bar");
});
```


At this time, when using [[jest-electron]], the test appears to pass without problems on the terminal, but in fact, a warning is issued in the electron console
- Terminal on VSCode
    - `$ DEBUG_MODE=1 npm test -- Foo`
    - ![image](https://gyazo.com/98f7d6dc79ae9cb6b30e444b705f1285/thumb/1000)
- Electron
    - ![image](https://gyazo.com/e60b0c9ba51f447e8bb6a4cfd6350dbb/thumb/1000)

So, I realized the problem of having to wrap this React state update in act by replacing useState with mock.
see:  [[Replace useState]]

But in this case, the warning does not disappear. (In fact, when I noticed this, I was testing a much larger and more complex system and realized that there had been cases where the warning disappeared this way, but only in some cases.)

What is wrong?

First, MyComponent.tsx is read here
Foo.test.tsx

```
import React from "react";
import { MyComponent, setValue } from "./MyComponent";  // HERE
import { render, screen } from "@testing-library/react";
import { mockUseState } from "./mockUseState";

test("foo", () => {
  const m = mockUseState();
  render(<MyComponent />);
  screen.getByText("foo");
  setValue("bar");
  screen.getByText("bar");
  m.mockRestore();
});
```


Next, at `(1)`, a reference to useState is duplicated in the scope of MyComponent.
MyComponent.tsx

```
import React, { useState } from "react";  // (1)

export let setValue: React.Dispatch<React.SetStateAction<string>>;
export const MyComponent = () => {
  const [value, _setValue] = useState("foo");  // (3)
  setValue = _setValue;
  return <span>{value}</span>;
};
```

MyComponent uses this reference to call useState.
After this, useState is replaced by jest.spyOn `(2)`, but the timing is slow: MyComponent's useState still points to the object before the replacement, so the new implementation that was replaced is not called when it is called.

![image](https://gyazo.com/4fed78d8022f240dcf8d20248f9c7c69/thumb/1000)

An easy way to solve this problem is to call it with `React.useState` instead of `useState`.

MyComponent.tsx

```
import React from "react";  // HERE

export let setValue: React.Dispatch<React.SetStateAction<string>>;
export const MyComponent = () => {
  const [value, _setValue] = React.useState("foo");  // HERE
  setValue = _setValue;
  return <span>{value}</span>;
};
```


This would resolve the value pointed to by React.setState at the time of the call, so the new implementation that replaced it would be called.
![image](https://gyazo.com/4fed78d8022f240dcf8d20248f9c7c69/thumb/1000)

In order to prevent such mistakes, there is an idea to replace the implementation at an earlier stage. jest.mock will replace the mock function with Jest's mock function before import due to the change of execution order by Jest. If you then call the implementation replacement method, the implementation will change without changing the reference.

---
This page is auto-translated from [/nishio/jest.spyOnで差し替わってなかった](https://scrapbox.io/nishio/jest.spyOnで差し替わってなかった) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "Export Promise created with useEffect"
---

I want to test the results of a state update performed asynchronously by Promise.
In the previous story: [[Test asynchronous React state updates]], I explained the case where Promise is obtained as the return value.
Since the return value of useEffect is defined to be a cleanup function, that method cannot be used. Therefore, we decided to export the created Promise.

Simply the following code will achieve the objective.
Note that loadFromServer assumes that the code to fetch from the server has been replaced by a mock implementation.
The type of the promise can be `Promise<unknown>`. It is only used to await in the test code.
MyUseEffectComponent.tsx

```
import { useEffect, useState } from "react";
export let promise: Promise<unknown>;

const loadFromServer = async () => 1;

export const MyUseEffectComponent = () => {
  const [value, setValue] = useState(0);
  useEffect(() => {
    promise = loadFromServer().then((x) => {
      setValue(x);
    });
  }, []);
  return <span>{value}</span>;
};
```


Test Code.
The [[Replace useState]] at the beginning is not explained here.
My.test.ts

```typescript
test("MyUseEffectComponent", async () => {
  jest.spyOn(React, "useState")...;

  render(<MyUseEffectComponent />);
  expect(screen.getByText("0")).toBeTruthy();

  await promise;
  expect(screen.getByText("1")).toBeTruthy();
});
```


---
This page is auto-translated from [/nishio/useEffectで作ったPromiseをexport](https://scrapbox.io/nishio/useEffectで作ったPromiseをexport) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
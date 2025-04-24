---
title: "Jest mocking does not affect calls within the same module"
---

from  [[Jest Memo]]
Mocking [[Jest]] does not affect calls in the same module
MyModule.ts

```typescript
export const A = () => "old value";
export const callA = () => A();
```

test.ts

```typescript
test("render", () => {
  jest.spyOn(MyModule, "A").mockImplementation(() => {
    return "new value";
  });
  expect(MyModule.callA()).toBe("new value");
```

result

```
Error: expect(received).toBe(expected) // Object.is equality

Expected: "new value"
Received: "old value"
```


It is convenient to be able to replace a specific function in a module with another process in one line, but if it is called from a function in the same module, it is a source of confusion
If it is indeed correct to replace A with a mock, then there should be a module boundary between callA and A (OK1), and if callA and A are so tightly coupled that it is not appropriate to separate them into separate modules, then it is not A that should be replaced with a mock (OK2), is it?
![image](https://gyazo.com/14dc24bc22d734c03c4906a938f365b7/thumb/1000)


---
This page is auto-translated from [/nishio/Jestのモックは同一モジュール内の呼び出しに影響を与えない](https://scrapbox.io/nishio/Jestのモックは同一モジュール内の呼び出しに影響を与えない) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "Test asynchronous processing in third-party libraries"
---

I am using [requestAnimationFrame](https://developer.mozilla.org/ja/docs/Web/API/Window/requestAnimationFrame) in a third party library to do asynchronous processing. In my test code, I want to check the value or perform some other operation after the process is finished. What should I do?
Note that this asynchronous processing is just a function, and the return value is used for another purpose and should not be changed.

I created a function to create a promise that exposed resolve on request from within the test code, and added code on the side of the third-party implementation that says "call if resolve is not null".
I don't like to change the arguments and return values of third-party asynchronous processing functions because the scope of modification is too large. This way, you only need to modify a few lines.
The fix is not to rewrite the third-party code directly, but to replace it in a jest.spyOn-like manner. In this case, I had already replaced it for another purpose, so I used that.

test.ts

```typescript
test("foo", async () => {
  let p = getCanvasViewUpdatePromise();
  ...
  await p;
  ...
```


target.ts

```typescript
let _canvasViewUpdatePromise;
let _resolve: ((arg: unknown) => void) | null = null;

export const getCanvasViewUpdatePromise = () => {
  _canvasViewUpdatePromise = new Promise(res => {
    _resolve = res;
  }).then(() => {
    _resolve = null;
  });
  return _canvasViewUpdatePromise;
};
```

target.ts

```typescript
    if (_resolve !== null) {
      _resolve(0);
    }
```


from  [[Jest Memo]]
---
This page is auto-translated from [/nishio/サードパーティライブラリの中の非同期処理をテストする](https://scrapbox.io/nishio/サードパーティライブラリの中の非同期処理をテストする) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
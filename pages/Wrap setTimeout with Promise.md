---
title: "Wrap setTimeout with Promise"
---

from  [[Jest Memo]]
Wrap setTimeout with Promise

before
ts

```typescript
export function sendToServer(text: string) {
  if (...) {
    ...
  } else {
    // bot is sleeping
    setTimeout(() => {
      sendToServer(text);
    }, 1000);
  }
}
```


after
ts

```typescript
export function sendToServer(text: string) {
  if (...) {
    ...
  } else {
    return new Promise((resolve) => setTimeout(resolve, 1000)).then(() => {
      sendToServer(text, newLogs);
    });
  }
} 
```


---
This page is auto-translated from [/nishio/setTimeoutをPromiseで包む](https://scrapbox.io/nishio/setTimeoutをPromiseで包む) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
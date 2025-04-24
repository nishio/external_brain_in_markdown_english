---
title: "I was unknowingly clenching an exception."
---

In a situation where I would expect an exception to appear on the screen (react-error-overlay) when it occurred, I was late in noticing the problem because it did not appear on the screen.

observed fact
ts

```typescript
console.log("will report");
throw new TypeError("report");
```

Now the will report appears in the console, but no TypeError error message appears on the screen or in the console.

cause
- This code was in Promise.
    - This is natural since this is where the data on the server is retrieved
- In that Promise .catch, I had to report the problem to [[Sentry]].
ts

```typescript
     console.log("report1");
     throw new TypeError("report");
...
})
.catch((error: unknown) => {
  Sentry.captureException(error);
});
```

- In other words, the exception is handled before React catches it.
- THROW and it now appears as expected.
diff  

```
- Sentry.captureException(error);
+ throw error;
```

    - ![image](https://gyazo.com/c70223995aa6073814fb6b4bf4905aa7/thumb/1000)
- That means you shouldn't have written `.catch(...) should not have been written in the first place.
    - There is no point in CATCH simply reporting.
- Sentry user feedback dialog is now emitted.

---
This page is auto-translated from [/nishio/無意識に例外を握りつぶしてた](https://scrapbox.io/nishio/無意識に例外を握りつぶしてた) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
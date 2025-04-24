---
title: "useCallback"
---

[[React Hooks]] [Hooks API Reference – React](https://reactjs.org/docs/hooks-reference.html#usecallback)

js

```javascript
const memoizedCallback = useCallback(
  () => {
    doSomething(a, b);
  },
  [a, b],
);
```


- `useCallback(fn, deps)` creates a function that calls fn only when deps changes
- No arguments are passed to fn. Read from the outer scope.
- Use when you want to prune fn so that it is not called on changes other than the value you want to focus on (deps).
- useCallback(fn, deps) is equivalent to useMemo(() => fn, deps) [[useMemo]].
- Values used in fn should be enumerated in deps (design philosophy)
    - When the compiler advances, the deps will be generated automatically.
    - Can be checked in ESLint by exhaustive-deps rules
---
This page is auto-translated from [/nishio/useCallback](https://scrapbox.io/nishio/useCallback) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
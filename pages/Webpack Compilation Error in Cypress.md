---
title: "Webpack Compilation Error in Cypress"
---

Cause: Imported code was tsx.

phenomenon
- The first thing I recognized was, "What? It's not showing up in the completion candidates, even though it's exported?" It was.
- I got the following error after importing explicitly
:

```
./src/Canvas/Gyazo.tsx 74:12
Module parse failed: Unexpected token (74:12)
File was processed with these loaders: ...
```

- This is due to the fact that the explicitly imported ts file imported another tsx file, and Cypress was not configured in the loader to read tsx.
- Should I set up a loader?
    - In this case, it was not a good idea to have utility function definitions that do not require DOM creation in a single tsx file, so we fixed that.

---
This page is auto-translated from [/nishio/CypressでWebpack Compilation Error](https://scrapbox.io/nishio/CypressでWebpack Compilation Error) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
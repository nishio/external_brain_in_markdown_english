---
title: "Resolution: Uncaught TypeError: use_force_update_1.default is not a function"
---


2023-01-13 Kozaneba now gives the following runtime error in the browser, even though it was built and deployed without error
- `Uncaught TypeError: use_force_update_1.default is not a function`

cause
    - I re-created the environment for the first time in half a year by [[Create a development environment for Kozaneba]].
- Latest [[react-scripts]] and [[use-force-update]] used internally by [[ReactN]] conflict.
- The latter offers both esm and cjs, a bug that prevents the former from properly understanding the situation, the latter author claims!
    - > Downgrade react-scripts to ^4 until they resolve it in ^5.
    - > Downgrade use-force-update to 1.0.8.
    - [Dependency Use force update 1.0.10 causes a Type Error · Issue #227 · CharlesStover/reactn · GitHub](https://github.com/CharlesStover/reactn/issues/227)

Resolution (for [[Yarn]]1)
- Downgraded use-force-update
package.json

```json
{
  "resolutions": {
    "use-force-update": "1.0.8"
  }
}
```

- There are other solutions on Github.

[[ReactN]] [[use-force-update]]
---
This page is auto-translated from [/nishio/解決: Uncaught TypeError: use_force_update_1.default is not a function](https://scrapbox.io/nishio/解決: Uncaught TypeError: use_force_update_1.default is not a function) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
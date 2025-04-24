---
title: "ts-node"
---

Running [[TypeScript]] with [node.js
`$ ts-node src/foo.ts `
:

```
import { Foo } from "./Bar";
       ^

SyntaxError: Unexpected token {
```

`$ node -v`
- v11.14.0

`$ node -v`
- v13.9.0
:

```
(node:39469) Warning: To load an ES module, set "type": "module" in the package.json or use the .mjs extension.
import { Foo } from "./Bar";
^^^^^^

SyntaxError: Cannot use import statement outside a module
```


tsconfig.json
diff

```
- "module": "esnext",
+ "module": "commonjs",
```

Now it works, but would [[umd]] or something else be better?

---
This page is auto-translated from [/nishio/ts-node](https://scrapbox.io/nishio/ts-node) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
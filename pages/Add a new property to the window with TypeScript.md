---
title: "Add a new property to the window with TypeScript"
---

If I do `window.db = db;` to expose the variable db for debugging purposes, I am told "window doesn't have that property".
It looked like I could declare it with Quick Fix, so I did and it added db : any to the interface Window definition in lib.dom.d.ts. I hate this because I will definitely forget to change it back later.
In TypeScript, declarations are generally merged. So you don't have to edit them directly.
typescript

```typescript
declare global {
    interface Window { db: any; }
}
window.db = db;
```


This global is a kind of [[Module Augmentation]], Global augmentation. see [Declaration Merging - TypeScript [https://www.typescriptlang.org/docs/](https://www.typescriptlang.org/docs/) handbook/declaration-merging.html]

typescript

```typescript
declare module "./modulename" {
    interface Foo { Bar: Baz; }
}
```


The "global" is added to mean "do not define a new Window in the module in which this declaration is written, but merge it with the global Window.

---
This page is auto-translated from [/nishio/TypeScriptでwindowに新しいプロパティを足す](https://scrapbox.io/nishio/TypeScriptでwindowに新しいプロパティを足す) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
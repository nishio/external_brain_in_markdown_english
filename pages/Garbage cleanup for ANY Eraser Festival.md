---
title: "Garbage cleanup for ANY Eraser Festival"
---

2021-02-18
I spent two days eradicating ANY...] from Regroup the other day, and I still haven't found all the problems with just type testing, and I'm getting error reports on [[Sentry]].
![image](https://gyazo.com/f20acbd51bf9916b0546eeb288de68b4/thumb/1000)

First, let's look at the most common `Error neverComeHere(assertion) Unhandled InitialState * onDrag`.
This is something that is ASSERTED in order to notice inconsistencies as soon as they occur, but the developer didn't notice.
![image](https://gyazo.com/3515a0bbce298490cd68d418928f1a50/thumb/1000)
Hmmm, I went back to Breadcrumb to see what was causing it and found that he switched to lasso.
![image](https://gyazo.com/f9ea011adeb463470ed9190eb24b6ff9/thumb/1000)
I switched to lasso and tried it and reproduced the problem at hand. The message was different.
`ReferenceError: paper is not defined`
that the company is in the process of developing a new product. This is
`const paper = require("paper");`
by the fact that you forgot to do it. (What? This is not detected by the type check?)

memo
- Why is it not detected by type checking?
- Should switch to lasso and check operation (with automated tests).

Fixing that is another error.
`TypeError: Cannot read property 'children' of undefined`
This is also a similar problem (PS: False positive.)
When I started writing Regroup, I couldn't figure out how to access PAPER from anywhere, so I hung it in the WINDOW.
`const items = window.app.paper.projects[0].layers[0].children;`

`const paper = require("paper");`

Typescipt doc: [export = and import = require()](https://www.typescriptlang.org/docs/handbook/modules.html#export--and-import--require)
Error when `import paper = require("paper");` is used
error

```
SyntaxError: /Users/nishio/regroup/src/onOverlayCanvas.ts: `import =` is not supported by @babel/plugin-transform-typescript
Please consider using `import <moduleName> from '<moduleName>';` alongside Typescript's --allowSyntheticDefaultImports option.
> 2 | import paper = require("paper");
```


The simple `import paper from "paper";` worked fine. I'm glad I did that.

With my knowledge before the development of the module mechanism in JavaScript, I unnecessarily wrote in a legacy way by using third-party libraries in TypeScript while reading explanations for JavaScript.
I even found `var paper = require("paper");`!

Change `window.app.paper` to `import paper from "paper";`.
Oops, new type error.
ts

```typescript
Argument of type 'HTMLElement | null' is not assignable to parameter of type 'string | HTMLCanvasElement'.
  Type 'null' is not assignable to type 'string | HTMLCanvasElement'.  TS2345

    50 |     // Get a reference to the canvas object
    51 |     const canvas = document.getElementById("myCanvas");
  > 52 |     paper.setup(canvas);
```


I see, what you REQUIRED was ANY!
![image](https://gyazo.com/43abf964f3c73d9c357cf5623b045d3e/thumb/1000)

I'm done cleaning up the mess, but the problem isn't solved.
Well, if you take a closer look, this means that the layer doesn't exist when nothing has been drawn yet, so if it doesn't, you can just empty list it.
`const items = paper.projects[0].layers[0]?.children ?? [];`


`Property 'onDeactivate' does not exist on type 'Tool'.`
`Property 'getBounds' does not exist on type 'PointText'.`
`Property 'getBounds' does not exist on type 'Layer'.`


---
This page is auto-translated from [/nishio/any消し祭りのゴミ片付け](https://scrapbox.io/nishio/any消し祭りのゴミ片付け) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
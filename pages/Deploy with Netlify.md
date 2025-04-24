---
title: "Deploy with Netlify"
---

I tried to deploy with Netlify, but there was something wrong with package.json or something.
I was not in a position to npm run build easily.

memo just in case
:

```
Could not find a declaration file for module 'paper'. '/Users/nishio/foobar/regroup/regroup/node_modules/paper/dist/paper-full.js' implicitly has an 'any' type.
  Try `npm install @types/paper` if it exists or add a new declaration (.d.ts) file containing `declare module 'paper';`ts(7016)
```


:

```
$ npm install --save @types/paper
npm WARN deprecated @types/paper@0.12.3: This is a stub types definition. paper provides its own type definitions, so you do not need this installed.
+ @types/paper@0.12.3
```


:

```
Cannot find namespace 'paper'.  TS2503

  >  9 | let positionOfNewPiece: paper.Point | null = null;
       |                         ^
```


diff

```
-    "paper": "0.12.0",
+    "paper": "^0.12.4", 
```


:

```
'ToolEvent' refers to a value, but is being used as a type here.  TS2749
    23 | type Handler = {
  > 24 |   onDrag: (event: ToolEvent, dragStartPoint: paper.Point) => void,
       |                   ^
```


diff

```
-    "paper": "^0.12.4", 
+    "paper": "0.12.0",
```


diff

```
-   "@types/paper": "^0.12.3",
+    "@types/paper": "0.11.8",

```


:

```
Property 'Tool' does not exist on type 'PaperScope'. Did you mean 'tool'?  TS2551

    28 | 
    29 | let createDefaultTool = (updateStateItem: any): paper.Tool => {
  > 30 |   let tool = new window.app.paper.Tool();
       |                                   ^
```


diff

```
- import { ToolEvent } from "paper";
+ import { ToolEvent, Tool } from "paper";

- let tool = new window.app.paper.Tool();
+ let tool = new Tool();
```


[[pRegroup-done-2020]]

from  [[paper.js type definitions]]
---
This page is auto-translated from [/nishio/Netlifyでデプロイ](https://scrapbox.io/nishio/Netlifyでデプロイ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
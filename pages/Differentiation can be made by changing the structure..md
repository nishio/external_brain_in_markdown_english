---
title: "Differentiation can be made by changing the structure."
---

ts

```typescript
class Vec4d {
    x=0; y=0; z=0; w=0;
}

class Queartanion {
    x=0; y=0; z=0; w=0;
}

let x = new Vec4d();
const y = new Queartanion();
x = y;  // OK
```


ts

```typescript
class Vec4d {
    x=0; y=0; z=0; w=0;
    isVector=true;
}

class Queartanion {
    x=0; y=0; z=0; w=0;
    isQueartanion=true;
}

let x = new Vec4d();
const y = new Queartanion();
x = y;  // Property 'isVector' is missing in type 'Queartanion' but required in type 'Vec4d'.
```


python

```
class Vec4 {
    x=0; y=0; z=0; w=0;
}
class Queartanion {
    s=0; x=0; y=0; z=0;
}

let x = new Vec4();
const y = new Queartanion();
x = y;  // Property 'w' is missing in type 'Queartanion' but required in type 'Vec4'.
[TypeScript types] 
```


---
This page is auto-translated from [/nishio/構造を変えれば区別できる](https://scrapbox.io/nishio/構造を変えれば区別できる) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "TypeScript type practice"
---

- [[TypeScript types]]
typescript

```typescript
const obj = {
  s: "foo",
  f: () => "bar"
}

const get1 = (key: keyof typeof obj) => {
  return obj[key]
}
// const get1: (key: "s" | "f") => string | (() => string)

const get2 = (key: keyof typeof obj) => {
  const value = obj[key]
  if (typeof value === "string") {
    return value
  } else {
    return () => value()
  }
}
// const get2: (key: "s" | "f") => string | (() => string)
```


Original story [https://twitter.com/teramotodaiki/status/1214149145935532033](https://twitter.com/teramotodaiki/status/1214149145935532033)

ts

```typescript
function get4<Key extends keyof typeof obj>(key: Key): typeof obj[Key] {
  return obj[key];
}

// ERROR
// function get5<Key extends keyof typeof obj>(key: Key): typeof obj[Key] extends string ? string : () => string {
//   return obj[key];
// }

function get6<Key extends keyof typeof obj>(key: Key): any {
  const value = obj[key]
  if (typeof value === "string") {
    return value
  } else {
    return () => value() // ERROR
    // This expression is not callable.
    // Not all constituents of type 'string | (() => string)' are callable.
    //   Type 'string' has no call signatures.
  }
}
```


`key`
- get2
    - Since `keyof typeof obj` === `"s" | "f"`.
    - `(parameter) key: "s" | "f"`
- get4
    - `(parameter) key: Key extends "s" | "f"`

`const value = obj[key]`
- get2
    - `const value: string | (() => string)`
- get6
ts

```typescript
const value: {
    s: string;
    f: () => string;
}[Key]
```


In short, the original code does not know that the key type is `"s" | "f"` because of the extra extensions,
As a result, `obj[key]` is also not recognized as `string | (() => string)`.
If it is `string | (() => string)`, it is a Union Type, so you can use [Type Guards [https://www.typescriptlang.org/docs/handbook/advanced-types.html#type-guards-and-](https://www.typescriptlang.org/docs/handbook/advanced-types.html#type-guards-and-) differentiating-types] can be used, but get6 is a complex type and cannot be used.
(Possible but not supported by TS at this time)
So the value in the else clause is not found to be `() => string` and `Type 'string' has no call signatures`.

---

`const x = get2("f")  // const x: string | (() => string)`
Hmmm, well, that's right, the obj could be rewritten before the function is called.

ts

```typescript
const x2 = get7("s")  // const x2: string
const x3 = get7("f")  // const x3: () => string
```

If you want this kind of behavior,

ts

```typescript
function get7(key: "s"): string;
function get7(key: "f"): (() => string);
function get7(key: "s" | "f"): (string | (() => string)) {
  const value = obj[key]
  if (typeof value === "string") {
    return value
  } else if (typeof value === "function") {
    return () => value()
  }
}
```

would it be better to ... or ...

Practice [[type (e.g. of machine, goods, etc.)]] in [TypeScript

---
This page is auto-translated from [/nishio/TypeScriptの型の練習](https://scrapbox.io/nishio/TypeScriptの型の練習) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
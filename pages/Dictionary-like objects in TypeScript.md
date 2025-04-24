---
title: "Dictionary-like objects in TypeScript"
---

I had no idea how to handle lexical objects in [[TypeScript]], so it was a trial and error process.
First, it is important to correctly distinguish between Map and Object in JavaScript
- [Map - JavaScript | MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map)
- Map and Object both behave like a Key-Value dictionary
- Especially confusing for Pythonista
    - In Python, `{}` is a dictionary.
    - In JavaScript, `{}` is an Object
    - JavaScript's `{}` is `object` in Python
- For JavaScript Map
    - `const aMap = new Map<string, number>();`
    - `aMap.set("a", 1);`
    - `aMap.forEach((value: number, key: string) => {});`
- In the case of Object
    - `const obj = {} as { [key: string]: number };`
    - `obj["a"] = 1` or  `obj.a = 1`
    - `Object.entries(obj).forEach(([key, value]) => {})`

ts

```typescript
  const aMap = new Map<string, number>();
  if (aMap.get("a") === undefined) {
    aMap.set("a", 1);
  }
  aMap.forEach((value: number, key: string) => {
    console.log(key, value);
  });

  const obj = {} as { [key: string]: number };
  if (obj["a"] === undefined) {
    obj["a"] = 1;
  }
  Object.entries(obj).forEach(([key, value]) => {
    console.log(key, value);
  });
```


----- trial-and-error
ts

```typescript
Array.from(preset_tests.entries()).map(
   ([key, value]: [string, any]) => <li><a href={"#" + key}>{key}: {value.title}</a></li>
 );
```



Object.entries(map)
[[TypeScript]]
ts

```typescript
// const map: Map<string, {
//   data: string;
//   title: string;
// }>
const x = Object.entries(map);
// const x: [string, any][]
const y = map.entries;
// const y: () => IterableIterator<[string, {
//   data: string;
//   title: string;
// }]>
```


---
This page is auto-translated from [/nishio/TypeScriptでの辞書的オブジェクト](https://scrapbox.io/nishio/TypeScriptでの辞書的オブジェクト) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
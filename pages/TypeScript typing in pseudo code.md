---
title: "TypeScript typing in pseudo code"
---

Type verification does not involve execution, so even pseudocode without code to execute can be verified for type consistency

Expressing "For now, there is such a thing as State."
ts

```typescript
type State = "State"
```

State is a literal type of "State
for some reason
TypeScript is [[Structural typing]], so if you set an appropriate empty object, etc., it will not raise an error if you make an inappropriate assignment.
ts

```typescript
type State = {};
type Other = {};

 (x: State) => {
   const y: Other = x; // no error
 }
```


Expresses "Mutex has a value of type State
ts

```typescript
type Mutex = {
  state: State,
};
```


Express "State or null".
ts

```typescript
type Mutex = {
  state: State | null,
};
```


There is a function updateState that takes a State and returns a State."
ts

```typescript
let updateState: (state: State) => State;
```

Here we only declare the function type and do not define the function implementation.
The let takes advantage of the fact that it does not have to have a value at the time of declaration.

ts

```typescript
let foo: (arg: ArgType) => RetType
```

The implementation would be rewritten like this
ts

```typescript
const foo = (arg: ArgType): RetType => { ... }
```


ts

```typescript
type Foo = "Foo";
const createFoo = (): Foo => {
  // ...
  return "Foo";
}
```



It's a "T" list, with at least two of them."
ts

```typescript
[T, T, ...T[]]
```



---
This page is auto-translated from [/nishio/TypeScriptで疑似コードに型付け](https://scrapbox.io/nishio/TypeScriptで疑似コードに型付け) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
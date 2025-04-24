---
title: "True story due to misunderstanding of nomenclatural and structural types"
---

There is a function called add, which declares that adding two values of type A will return type A, and adding two values of type B will return type B.
test.d.ts

```typescript
export function add(x: A, y: A): A;
export function add(x: B, y: B): B;
```

But in actual use, the result of adding Bs together is A. Why?

![image](https://gyazo.com/fc1d9dca9ea1ceedf5575090dc7d119f/thumb/1000)

Minimal entire code to reproduce the problem
test.ts

```typescript
import { A, B, add } from "./testlib.js";

let x = new B();
let y = new B();
let z = add(x, y);  // type of z is A
console.log(z);
```


testlib.d.ts

```typescript
export class A {}
export class B {}
export function add(x: A, y: A): A;
export function add(x: B, y: B): B;
```


testlib.js

```javascript
class A{ }
class B{ }
function add(x, y) {
  return x + y;
}
export {A, B, add}
```


explanation
- TypeScript is a structural type system, not a nominal type system
- So types with the same structure are the same type
- A and B are the same type because they have the same structure
- So the rule of `export function add(x: A, y: A): A;` that appeared earlier is used, and the return value is A

A and B are not distinguished, so adding A and B does not result in an error.
:

```
let ab = add(new A(), new B());  // No error
```


solution
testlib.d.ts

```typescript
export class A {
  _A_Brand: never;
}
export class B {
  _B_Brand: never;
}
```

Now A and B are distinguished as types because they have different structures.
![image](https://gyazo.com/7d13e82f4439f5fece41d74ac85a3224/thumb/1000)

In this example, we chose to "add a member that is not used" because the situation was one in which we wanted to distinguish between the two classes.
This method cannot be used in cases where you want to distinguish between string types because you cannot add members.
Another way is to create an INTERSECTION with ENUM. In this case, you can use `as FooId` to set the string type to the FooId type.
ts

```typescript
enum FooIdBrand { _ = "" };
type FooId = FooIdBrand & string;
const fooId = 'foo' as FooId;
```


relevance
- [Creating ghost type-like things with TypeScript](https://zenn.dev/f_subal/articles/phantom_type_in_typescript)
- [Nominal Typing - TypeScript Deep Dive](https://basarat.gitbook.io/typescript/main-1/nominaltyping)

---
This page is auto-translated from [/nishio/名前的型と構造的型の勘違いによる実話](https://scrapbox.io/nishio/名前的型と構造的型の勘違いによる実話) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "Mixin"
---


[Mixins - TypeScript Deep Dive Japanese](https://typescript-jp.gitbook.io/deep-dive/type-system/mixins)
Realized as a function that takes a class as an argument and returns the class
The way the sample is written, it is not possible to access the members provided by other mixins (unless ignoring the type), which is a bit tricky.

ts

```typescript
type Constructor<T = {}> = new (...args: any[]) => T;
function Mixin1<TBase extends Constructor>(Base: TBase) {
  return class extends Base {
    a = 1;
  };
}
function Mixin2<TBase extends Constructor>(Base: TBase) {
  return class extends Base {
    foo() {
      // return this.a; // NG: Property 'a' does not exist on type '(Anonymous class)'
    }
  };
}

class BaseClass {
  b = "";
}

const NewClass = Mixin2(Mixin1(BaseClass));
```


We can guarantee by type that the class to be mixed has a
However, the test to see if the conditions are satisfied occurs at each mixing, so it is necessary to mix in the order in which the conditions are satisfied, which is delicate.
ts

```typescript
type HasA<T = { a: number }> = new (...args: any[]) => T;

function Mixin2<TBase extends HasA>(Base: TBase) {
  return class extends Base {
    foo() {
      return this.a; // OK
    }
  };
}

const NewClass = Mixin2(Mixin1(BaseClass));  // OK
// const NewClass2 = Mixin1(Mixin2(BaseClass));  // NG: Property 'a' is missing 
```


I can do it if the style is to explicitly pass the receiver.
ts

```typescript
const supplyA = { a: 1 };
const demandA = { foo: (self: { a: number }) => self.a };

const obj = { ...demandA, ...supplyA } as typeof demandA & typeof supplyA;
obj.foo(obj);
```



---
This page is auto-translated from [/nishio/Mixin](https://scrapbox.io/nishio/Mixin) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
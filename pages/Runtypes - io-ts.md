---
title: "Runtypes / io-ts"
---

> [whitphx_en:](https://twitter.com/whitphx_ja/status/1436946766167826437) Runtypes guess
- >  It's easy because the type definition is also a direct implementation of the type checker.
- >  If the number of interfaces increases or complex interfaces are introduced, you can't write your own checker every time.
    - [https://github.com/pelotom/runtypes](https://github.com/pelotom/runtypes)
- I know that >io-ts has more stars, but it smells too much like a function type for my fragile self.
    - [https://github.com/gcanti/io-ts](https://github.com/gcanti/io-ts)

I have written the code to check the JSON type by myself, but can it be automated?
I'm going to move on to using this because it's buggy when written by humans...

Compare which of Runtypes / io-ts to use with a smaller (but containing the complex structure I use) type.

ts

```typescript
test("io-ts, use implemented type", () => {
  const obj_string = JSON.parse(`"hello"`); // is any
  const obj_number = JSON.parse(`123`); // is any

  expect(isRight(t.string.decode(obj_string))).toBeTruthy();
  expect(isRight(t.string.decode(obj_number))).toBeFalsy();

  const ret = t.string.decode(obj_string);
  let string_value: string;
  if (isRight(ret)) {
    string_value = ret.right;
  } else {
    throw new Error("not string");
  }
  expect(string_value).toBe("hello");
});

test("runtypes, use implemented type", () => {
  const obj_string = JSON.parse(`"hello"`); // is any
  const obj_number = JSON.parse(`123`); // is any

  expect(String.guard(obj_string)).toBeTruthy();
  expect(String.guard(obj_number)).toBeFalsy();

  let string_value: string;
  if (String.guard(obj_string)) {
    string_value = obj_string;
  } else {
    throw new Error("not string");
  }
  expect(string_value).toBe("hello");
});
```


Comparing real-world "complex types" written in io-ts and runtypes
- [https://gist.github.com/nishio/a5f8bdbc7961f3c0a569653e2dacfdd3](https://gist.github.com/nishio/a5f8bdbc7961f3c0a569653e2dacfdd3)
- Both libraries were installed at the same time just two hours ago with zero experience, so you can assume they are equally clunky.
- Question 1: io-ts, it says there is no support for optional and to make an INTERSECTION with PARTIAL, but is that really what you want? It's the same behavior, but the generated types look terrible, right?
- Question 2: I can't figure out from the documentation how to do the equivalent of io-ts record in runtypes. Maybe they thought it was self-explanatory, or they omitted it. (Record in runtypes is a type of io-ts, so it is a different thing.)
    - I referred to the solution of another common one in reality, which is when the key is Branded, but I don't know if it is correct.
    - Branded types are explicitly supported in both cases.
- On the runtypes side, as described in the Pattern matching chapter, you can write a single function-overloaded process for each type of union type. It's like, "Wow, that's interesting.
- runtypes can be made into type objects as "Number with a positive constraint", which is not possible with normal type checking. Of course, when the type is converted to a type object, it becomes an unconstrained number, but it will still be checked by type guard.
    - In runtypes, you can put a contract on a function. For example, you can put a constraint that must not be zero. The way it is written in this case is compact, but a bit abuse-like. It is a bit like English grammar with an in-language DSL.
- Many people may be surprised to see that io-ts returns a naked Either type. The internal structure feels bare.
    - But well, I also think that you can wrap it however you want for real world use. I think sometimes it's easier to handle because of what's inside; I don't know what's going on with runtypes.
    - For example, if you are going to implement a programming language in TypeScript, io-ts might be better suited to get information on where and how many errors have occurred.
    - On the other hand, I am reading JSON that is not supposed to be broken, but I want to check when I read it because it is hard to investigate the problem if I read through it when it is broken, so I think runtypes would be more suitable.
        - You can implement utility functions in io-ts to get the interface you prefer, you just don't want to put that much effort into it.

The way the io-ts deal with the OPTIONAL type is too weird.
- On the other hand, if you can say, "I don't use optional types, they are so weird," then io-ts would be a good fit. I think this is ultimately a difference in stance on how to deal with types.
- > [odiak_](https://twitter.com/odiak_/status/1438822559290589186): `const optional=(tp)=>t.union([tp, t.undefined])` and define something like `t. type({a: optional(t.string),b:t.number})` and so on. This is not exactly the same as `{a?: string, b: number}`, but it accepts values like `{b: 3}` and is fine for practical use.

    - [[Comparison of Runtypes and io-ts optional]]

> [odiak_](https://twitter.com/odiak_/status/1438823161064091651): Also, it is fun to define custom types for io-ts. Types with constraints on values, types that convert to specific objects, types that convert T|null|undefined to T|undefined, etc.

There is a method called check in Runtypes.
- before
ts

```typescript
let string_value: string;
if (String.guard(obj_string)) {
  string_value = obj_string;
} else {
  throw new Error("not string");
}
```

- after
ts

```typescript
  {
    const string_value = String.check(obj_string);
    expect(string_value).toBe("hello");
  }
  // const string_value = String.check(obj_number);
  // throws: `ValidationError: Expected string, but was number`
```

- Kind error message.

---
This page is auto-translated from [/nishio/Runtypes / io-ts](https://scrapbox.io/nishio/Runtypes / io-ts) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
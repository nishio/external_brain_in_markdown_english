---
title: "I spent two days eradicating ANY."
---

Formerly titled "Turning ANY into UNKNOWN"
As a result of the change, 80-90% of ANY did not stay UNKNOWN, so the title was changed.

---

In [[TypeScript]], there are two types of cases where "I used 'any' because it was too much trouble to write the type properly even though I wrote the code myself" and "I used 'any' because it was too much trouble to check the type of the value that comes from a third-party library. In the other case, I use "any" because I don't want to have to check the type of the value coming from a third party library.

For example, in the latter example, I was unsure of the type of the document object taken from Firestore, so I used any.
ts

```typescript
(doc: any) => { ... }
```


If we change this to UNKNOWN...
ts

```typescript
(doc: unknown) => { ... }
```


I don't know if UNKNOWN has EXISTS growing on it, he points out.
I need to put a proper mold on it.
ts

```typescript
if (doc.exists) {  // ERROR: Object is of type 'unknown'.  TS2571
```


I'll try to put an impossible type on it to get the necessary information.
ts

```typescript
(doc: number) => { ... }
```


Then a type compatibility error will show what type is expected.
> Argument of type '(doc: number) => void' is not assignable to parameter of type '(value: DocumentSnapshot<DocumentData>) => void | PromiseLike<void>'.

I found the name `DocumentSnapshot<DocumentData>`, so I searched for it and found a reference
- [DocumentSnapshot | JavaScript SDK  |  Firebase](https://firebase.google.com/docs/reference/js/firebase.firestore.DocumentSnapshot)

It's a long story, so I decided to give it an alias.
ts

```typescript
type Document = firebase.firestore.DocumentSnapshot<firebase.firestore.DocumentData>;
...
(doc: Document) => { ... }
```


After this, I get another error.
ts

```typescript
JSON.parse(data.json)  // ERROR: Object is possibly 'undefined'.  TS2532
```

It should not be undefined because I check its existence with `doc.exists` and then get it with `data = doc.data()` as Firestore explains, but TypeScript does not know that.

So we decide to throw an exception.
ts

```typescript
if (data === undefined) {
  throw new TypeError("doc.data is undefined");
}
```

By doing this, the possibility of undefined in the flow after this point is eliminated, and TypeScript understands it properly.

By the way, I used to think "I shouldn't throw an exception if I can continue processing if I ignore it." But after I started using [[Sentry]], my thinking changed to "If I throw an exception as soon as I detect a situation that shouldn't happen, I will be notified and can easily find the bug. I guess the fact that the exception on the user's browser reaches the developer also influences the way I think about programming.

---
It was hard to change all the "any" to UNKNOWN at once. We should have done them one at a time. It makes it difficult to isolate complex problems when they arise.
- I got into [[React.forwardRef]].
    - If a function is used to wrap FC, declaring the type as "FC" is not allowed, but if not declared, it is OK.
    - Maybe forwardRef should be implemented to receive FCs.

In the end, we have to write the type properly because we can't use it as UNKNOWN, and UNKNOWN generally disappears.
I thought the transition process was to change from any to unknown so that type checking would run, and then change the type to the appropriate type while watching the error content.

UNKNOWN was left with only one location.
- `onClick: () => unknown`
- I haven't checked whether the return value is void or not, but since I don't use it, it doesn't matter either way, so it was decided to stay.

---
I'll try to find the source code for a project I started writing years ago in ANY and process it.
I wrote it while learning TypeScript, so there is quite a bit of ANY.

- Day 1: 4 pomodoros, from 124 any to 56 any.
    - Where ANY is often found
        - Interaction with Firebase
            - There's no way for TypeScript to know what members doc.data() has.
        - I was receiving MouseEvent, TouchEvent, etc. with any.
            - I rewrite, "This must be TouchEvent!" and when I rewrote it, I was told "I don't think TouchEvent has this member...", grrrrrrrrrrrrrrrr....
                - I found out that the React definition of Touch doesn't have radiusX for this case.
                    - This is not standard, but is available in Safari on the iPad and I would like to use it.
            - Some places Paper.js wraps it and passes it around as a ToolEvent.
                - There is an inconsistency in ToolEvent.event where it actually has a raw event, but the type says it doesn't.
    - In many cases, code written before I learned the technique of deliberately colliding types and reading the types given by the processor by mouse hovering is making any because I don't understand complex types.
        - That kind of thing is easy because you can fix it right away.
    - If the third-party code does not meet your expectations, you need to absorb the discrepancy somewhere, but the type check is invalidated at all possible locations of the value and its derivatives with any type, whereas with ts-ignore, it is invalidated at only one location, thus limiting the scope of the effect. This limits the scope of influence.
    - I've hit what I think is a fundamentally bad design due to the lack of molds, and I'm starting to feel that small changes won't cut it unless I change the design from the ground up.

- Day 2: Almost all gone
    - `return (x as any).item ! == undefined;` should be `return "item" in x;`
    - What is the type of component in React Router?
        - `<Route path="/:id" component={MyComponent} />`
        - If you do `<Route path="/:id" component={1} />`, `Type 'number' is not assignable to type 'FunctionComponent<any> | ComponentClass<any, any> | FunctionComponent<... ComponentClass<RouteComponentProps<any, StaticContext, PoorMansUnknown>, any> | FunctionComponent<... > | undefined'`, so it's not helpful.
        - The correct answer is `const MyComponent: React.FC<RouteComponentProps<{ id: string }>>`.
    - Firestore seems to get an error when trying to save a value containing undefined
        - `{x: 1}` is OK, `{x: 1, y: undefined}` is not.
        - TypeScript types cannot distinguish between the two.
        - Type like `{ x: number; y: number | null }`, and if there is no y, do `{ x: 1, y: null };`.
    - We need to stop writing members with different types, such as `obj.foo = convertType(obj.foo)`.
        - To begin with, "an object with a different type and reinserted members" is a "different object" and therefore has a different type, and trying to do this with a single variable makes it impossible to type the object.
        - `new_obj = {...obj, foo: convertType(obj.foo)}`
    - It is also necessary to stop writing objects in such a way that they are completed by putting values into them in order.
        - Bad
ts

```typescript
export const createFoo = (): FOO => {
  const ret: any = {
    version: 2,
  };
  ret.items = [];
  return ret;
};
```

        - Good
ts

```typescript
export const createFoo = (): FOO => {
  const version = 2;
  const items: ItemID[] = [];
  return { version, items };
};
```

            - If you make any like the former, it's not checked if the object created by this function is really of type FOO.
    - `e: paper.ToolEvent` really has `e.event`, but it is supposed to be absent on the type
        - I used to write `const event = (e as any).event;`.
ts

```typescript
// const event = e.event; // Property 'event' does not exist on type 'ToolEvent'
const event = (e as any).event; // event: any
```

        - If you want to eliminate ANY, you can do it like this.
ts

```typescript
// @ts-ignore
const event: MouseEvent = e.event;
```

    - With a combination of these things, I rewrote the function that converts the state in the browser into an object that can be saved in Firestore as follows
        - It's no good that position is a paper.Point object, so you can change it to `[number, number]` and so on.
        - Extracting only the value to be stored or
        - before
ts

```typescript
export const convertStateItemToFirestore = (x: StateItem) => {
  const ret: any;
  ret.type = x.type;
  ret.id = x.id;
  ret.position = [x.position.x, x.position.y]
  if (isPieceStateItem(x)) {
    ret.text = x.text;
	...	
  } else if (isPathStateItem(x)) {
    ret.opacity = x.opacity ?? 1.0;
	...
  }
  return ret;
}
```

        - after
ts

```typescript
export const convertStateItemToFirestore = (x: StateItem) => {
  const { type, id } = x;
  const position: [number, number] = [x.position.x, x.position.y];
  const common = { type, id, position };
  if (isPieceStateItem(x)) {
    const { text, compact, scale } = x;
    return {...common, text, compact, scale};
  } else if (isPathStateItem(x)) {
    const { opacity, dashArray, created } = x;
    return {
      ...common, created,
      opacity: opacity ?? 1.0,
      dashArray: dashArray ?? [],
    };
  } else if (...) {
  	...
  } else {
    throw new TypeError(`unknown type: ${type}`);
  }
}
```

    - A function that takes a function and wraps it in a process and returns it, which is tricky
ts

```typescript
export const onOverlayCanvas = (f: (...args: any[]) => unknown) => {
  return (...args: unknown[]) => {
    paper.projects[1].activate();
    const ret = f(...args);
    paper.projects[0].activate();
    return ret;
  };
};
```

        - In order to do something about it, we needed generics.
ts

```typescript
import { ToolEvent } from "paper";

export const onOverlayCanvas = <T extends [ToolEvent] | []>(
  f: (...args: T) => unknown,
) => {
  return (...args: T) => {
    paper.projects[1].activate();
    const ret = f(...args);
    paper.projects[0].activate();
    return ret;
  };
};
```

- I put in a bug that prevented me from reading historical data from Firestore.
    - I assumed it was `isReadOnly: bool`, but there was only an entry when it was true.
        - [I was unknowingly clenching an exception.
- There were 124 anys and now there are 3.
    - Two of them are the contents of a comment or message string
    - The last one is a debug object type created for debugging convenience
    - UNKNOWN has 16
        - 80-90% of ANY turned into a decent type instead of turning into UNKNOWN.

Added 2021-02-18 [[Garbage cleanup for ANY Eraser Festival]].
    - [[What you REQUIRE will be ANY]]
    - This caused an unacknowledged ANY in the code that uses Paper.js.
    - Fixed and paper.Item is now type-checked.
    - [[Spreading an instance of a class does not duplicate the method.]]
    - So I solved the problem with casts. It's not good to have casts all over the place, so we put them in one place.
ts

```typescript
export const attachStateItem = (
  paperItem: paper.Item,
  stateItem: StateItem,
): PaperItem => {
  const ret = paperItem as PaperItem;
  ret.item = stateItem;
  return ret;
};
```



---
This page is auto-translated from [/nishio/2日掛けてanyを撲滅した](https://scrapbox.io/nishio/2日掛けてanyを撲滅した) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
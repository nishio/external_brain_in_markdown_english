---
title: "Interactive implementation in TypeScript"
---

Whether it's a good practice or not, take note of the steps.

- I want to implement spitting out the selection to JSON.
- I'd like to try things out interactively before deciding how to implement them.
- Where is the selection?
    - `const App = (props: any) => {...} In the `.
        - `let [selection, setSelection] = useState<PaperItem[]>([]);`
    - Not exposed because of the local scope of the function.
    - Expose with `window.debug.selection = selection;`.
        - Related: [[Add a new property to the window with TypeScript]].
        - window.debug is prepared with the type "any" so that you don't have to declare it every time.
        - Or @ts-ignore.
- Where is the code to convert an object to a plain object
    - `const stateItemToFirestore = (x: StateItem) => {...}`
    - This is also after the function definition `window.debug.stateItemToFirestore = stateItemToFirestore`...
        - I was going to, but ng.
            - Since the code for this function definition runs before the code that creates window.debug
    - `export stateItemToFirestore`.
        - On the side of the code making window.debug, import it to expose
        - [[Considerations on how to expose objects]]
- succession
    - `window.debug.stateItemToFirestore(window.debug.selection)`
        - error
    - `window.debug.stateItemToFirestore(window.debug.selection[0])`
        - error
    - `window.debug.stateItemToFirestore(window.debug.selection[0]).item`
        - OK
    - This is the wrong argument type to call.
        - If I had written it as TypeScript, would I have found out why with a type error?
        - -> NO, type information is lost when you put it in `window.debug:any
    - `JSON.stringify(...)`
        - The desired string is obtained.
    - Next step is to figure out how to get this back to Map.
- Expose the `updateStateItem` as it is exported.
    - →Error in simple reading
- Requires `firestoreToStateItem`.
    - It's done.
    - ![image](https://gyazo.com/5eb6bca96b3a751c15a074ec1a180cfc/thumb/1000)
- Make it TypeScript code.
ts

```typescript
export const exportSelectedItemsAsJSON = () => {
  const r = selectedItems.map((x) =>
    stateItemToFirestore(x.item)
  );
  return JSON.stringify(r);
};

export const importItemsFromJSON = (json: string) => {
  const xs = JSON.parse(json);
  xs.forEach((x: object) => {
    updateStateItem(null, firestoreToStateItem(x))
  })
};
```

- Now it works as expected: `debug.importItemsFromJSON(debug.exportSelectedItemsAsJSON())`
- But copying and pasting the JSON displayed in the console with `debug.exportSelectedItemsAsJSON()` breaks it.
    - Well, it's no wonder JSON doesn't parse correctly in the developer console.
- `localStorage["tmp"] = debug.exportSelectedItemsAsJSON()`
- In a separate window `debug.importItemsFromJSON(localStorage["tmp"])`
- It worked correctly.

---
This page is auto-translated from [/nishio/TypeScriptで対話的に実装](https://scrapbox.io/nishio/TypeScriptで対話的に実装) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
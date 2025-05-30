---
title: "Asynchronously read from Firestore and render in React"
---

- [[React Study Diary]]

I would like to register a real-time update listener for [[Firestore]] and rerender it in [[React]] when there is an update.
Asynchronous because the read API returns a promise, regardless of whether it listens for real-time updates or not.
React uses this because it redraws at the timing of state updates.
Result: A prototype was created that automatically changes the display in the browser when the value in the Firestore changes.

Stumbling Points
- React.Component is a type function and takes the type of state as its second type argument
    - If not given, it works as if `{}` were given
        - Definition: `interface Component<P = {}, S = {}, SS = any>`
    - The result is "Readonly<{}> has no pieces" for `this.state.pieces`.
    - Property 'pieces' does not exist on type 'Readonly<{}>'.

- The Firebase sample uses a function as the argument for onSnapshot, but as it is, it shadows this in Component.
    - Visual Studio Code warned me so I didn't get stuck there.
    - But I didn't understand the solution to this problem correctly.
    - Since this will be shadowed and inaccessible.
    - I figured I could just `let setState = this.setState` in the outer scope and use that.
        - Python-like conception; in Python, object methods are bound to objects.
        - That's not true in JS. this.setState is just a function
        - Result TypeError: Cannot read property 'updater' of undefined
            - [TypeError: Cannot read property 'updater' of undefined · Issue #9654 · facebook/react](https://github.com/facebook/react/issues/9654)
            - [Learn ReactJS by Error - Kuronote](http://note.crohaco.net/2018/react-errors-warnings/)
    - In the past, JS would solve this problem by explicitly binding
        - `const setState = this.setState.bind(this)`
    - Nowadays ES6 can be used that the arrow function does not bind (and therefore does not shadow) THIS at the time of the call.
        - I used this one this time.
        - > An arrow function expression is a syntactically compact alternative to a regular function expression, although without its own bindings to the this, arguments, super, or new.target keywords.
        - [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)

doubt
- I used constructor, but I see here and there people using [[componentDidMount]]. What is the difference?

typescript

```typescript
class App extends React.Component<{}, { pieces: any[] }> {
  constructor(props: {}) {
    super(props);
    this.state = { pieces: [] };
    db.collection("pieces").onSnapshot((querySnapshot: any) => {
      let pieces: any[] = [];
      querySnapshot.forEach(function (doc: any) {
        pieces.push(doc.data().text);
      });
      this.setState({ pieces: pieces });
    });
  }
  render() {
    let pieces = this.state.pieces.map((x) => <SimplePiece text={x}></SimplePiece>);
    return (
      <div className="App">
        <header className="App-header">
          {pieces}
        </header>
      </div>
    );
  }
}
```



---
This page is auto-translated from [/nishio/非同期でFirestoreから読んでReactでrender](https://scrapbox.io/nishio/非同期でFirestoreから読んでReactでrender) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
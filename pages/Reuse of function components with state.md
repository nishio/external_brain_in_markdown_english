---
title: "Reuse of function components with state"
---

- [[React Study Diary]]

Suppose you want to reuse a component A to create a new component B.
- (1) The primitive method is to copy and paste the source code and modify some of it.
- (2) A slightly more advanced method is
    - Component A is implemented as a class,
    - After bracketing out the part to be changed in the method,
    - Create class B by inheriting class A.
    - Override some methods
- (3) Since this is a function component, a simple way to do this is to use the
    - Call function A from function B

![image](https://gyazo.com/f1d9052982270e422f8bf397b0259f4d/thumb/1000)

However, the trouble is that func A has state X, and I want to access this state in func B.
Note that "state X" here refers to the following two pairs.
- Value x
- Function setX to update the value x
It can be obtained as a return value by calling useState.

- (4) X is a local variable of func A, so it cannot be accessed from outside func A.
- (5) So I thought of using func B to create X and pass it on (foreshadowing: so far so good)
    - X as an optional argument and use it when it is passed and func A makes it itself if not passed (foreshadowing: this is a mistake).
    - `const [x, setX] = props.X ? props.X : useState(...);`
    - This is NG.
        - `React Hook "useState" is called conditionally. React Hooks must be called in the exact same order in every component render  react-hooks/rules-of-hooks`
![image](https://gyazo.com/92efab77f50234cd0e8415f8b9258d43/thumb/1000)

- (6) Then, the code that handles state X should be bundled out of func A and designated func handleX,
    - I figured I could use that from A and B.
    - ![image](https://gyazo.com/fdb55f1a2b553824fd965c63f9e5e9ca/thumb/1000)
    - This is NG, because X in func A is not updated just because X in func B is updated.
    - They should not have had individual X's.

- (7) I created func C to combine components with state X into one.
    - func C takes child elements as arguments using props.children and renders them
    - [Composition vs Inheritance – React](https://reactjs.org/docs/composition-vs-inheritance.html)
    - ![image](https://gyazo.com/e22ff02908cc76b91a455e23a1bcc7f0/thumb/1000)
    - Now we've achieved our original goal.

By the way, I want to synchronize the state X of this component with the database on the server. Now what do we do?
- Func It's odd to put code for synchronization in C.
    - The actual name of func C was "DraggableSVGElement".
    - It is clearly not [[sole responsibility]] to write database access code here.
- [Lifting State Up – React](https://reactjs.org/docs/lifting-state-up.html)
- Child components relinquish control of their own condition and delegate it to their parents
- This is the first half of what I had in mind at the time of (5)
    - The mistake was in trying to express "a component that manages state X by itself" and "a component that depends on its parent to manage state X" in a single function in the latter half.
- When you build a component from the bottom up, from the smallest part, you tend to want the component to be complete on its own.
    - This is similar to the idea of trying to create "parts" in a "stand-alone instantiable class.
    - That's not the only way to implement it nowadays.
        - An entity that cannot be instantiated on its own like Mixin, but is mixed into the class
        - An entity that can only make an instance when it is with a Treate that provides "the method I require" as Treate does.
    - React components may not have the necessary "state" themselves to draw themselves or perform their functions
        - > React is all about one-way data flow down the component hierarchy. It may not be immediately clear which component should own what state. This is often the most challenging part for newcomers to understand

Tomorrow we'll reconstruct it based on this realization.


---
This page is auto-translated from [/nishio/状態を持つ関数コンポーネントの再利用](https://scrapbox.io/nishio/状態を持つ関数コンポーネントの再利用) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
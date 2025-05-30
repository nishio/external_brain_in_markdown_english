---
title: "undo implementation"
---

[[pRegroup-done-2019]]
React-like state design to allow Undo to add and move stickies
- useHistory ported to TS.
- I'm a bit bewildered, but too early optimization is the root of all evil, so I'll start with "implementation that retains the entire state history".
- Try first the behavior of useHistory in an experimental rather than raw state
- Next, convert the sticky to a React-like state
- (Do you do passes as well? As long as the path can be applied, the user will try to Undo the path. A heterogeneous mixture of states will occur in the future anyway, so we should try it at this simple stage -> do it)


[Using React Hooks with canvas – ITNEXT](https://itnext.io/using-react-hooks-with-canvas-f188d6e416c0)
- Description: [[React+Canvas]].
- This is good for React-like state management and even drawing persistence.
- While this method is very easy to understand, it does "draw all the user's operation history every time" without regard to performance.
- I thought it might be a good idea to start with a simple implementation of Paper.js, since it seems to be written in a straightforward manner without any off-screen culling, and since Paper, which interacts with the user, will be layered on top as a separate layer after this.
- The Regroup use case is not only "add" but also "move".
    - To make it undoable, keep the "move" in invertible form as "move from where to where",
    - Run a history to determine the current location before the actual rendering,
    - Check to see if it is included in the screen from its current location,
    - The process is supposed to be to draw only what is included.
- You could save the most recent snapshot and keep it.

undo implementation
- Required, especially if handwriting is included.
- [https://usehooks.com/](https://usehooks.com/)
- The useHistory pattern of this looks good.
- [[useCallback]]、[[useReducer]]
- This is another type that keeps all the states and updates the whole thing.
    - I'm not sure if that's a good idea, and I'm not sure if it's necessary to make it a modified diff, but if it doesn't cause performance problems, I'd prefer a simple implementation, so I think I should start with that policy.
    - Premature optimization is the root of all evil.

The implementation of [[useHistory]] only considers assigning a state by SET and does not consider the possibility of passing (state)=>(newState).
ts

```typescript
let newPresent;
if(typeof action.newPresent == "function"){
  newPresent = action.newPresent(present);
}else{
  newPresent = action.newPresent
}
```

like this

Zoom can now be Undo!

Instead of keeping the state as a list of stickies, we put objects in the "list of items to be drawn" and designed to separate what kind of drawing is done by obj.type.
This will allow for consistent handling of handwritten paths in the future.
Besides sticky notes and handwritten paths, other things that will appear in the future are
Group
Connector

Undo is not working even though it is drawing correctly by calling state update.
Oh, you've made a destructive change to the original state, here.
ts

```typescript
 const updateItemPosition = (item:any, position:paper.Point) => {
   let newItems:any[] = state.items.filter((x:any) => (x != item));
   item.position = position; //no!
   newItems.push(item);
   set((state:any) => ({
     ...state, 
     items: newItems, 
   }));
 }
```

At first glance I can do it, but for some reason a new sticky is generated at the initial position when I drag it a second time...
> let newItems:any[] = state.items.filter((x:any) => (x != item));
We're looking at the initial state of the outer scope, not the state immediately before this state.
This is the correct answer.
ts

```typescript
 const updateItemPosition = (item:any, position:paper.Point) => {
    set((state:any) => {
      let newItems:any[] = state.items.filter((x:any) => (x != item));
      item = {...item, position: position};
      newItems.push(item);
      return {
        ...state, 
        items: newItems, 
      };
    });
  }
```


---
This page is auto-translated from [/nishio/undoの実装](https://scrapbox.io/nishio/undoの実装) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
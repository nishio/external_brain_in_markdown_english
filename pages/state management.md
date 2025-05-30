---
title: "state management"
---

from [[pRegroup2020]]

2019-07-16
    - [[Verify if replacing the Reconsiler stops the image blinking on the iPad.]]  done

- I managed to get to the point where stickies with no text show up.
    - Stickies without text are now displayed.
    - The text portion is commented out.
    - The path is commented out now.
    - The group is commenting out now too.
- The canvas resize event is also commented out and fixed size.
- We'll revert these areas one by one so that the display is restored to its original state.
- Then first move the parallel shift and zoom, then move the sticky by dragging it.

2019-08-02
- Text displaydone
- base canvas and overlay canvas each have a PaperScope
- I named them basePaper and overlayPaper.
- Delete app.paper
    - They use it all over the place in many places.
    - Tool is also hanging on app.paper
        - Comment out once
    - Can now zoom in and out (dies trying to set state when zooming is complete)
    - Commented out thinking that it may not be necessary to update the status
- Zooming is now possible.
- Achieve parallel movement
- Open MANUAL for viewing.
commit id: f182638

---
A collection of things written in pRegroup:.
    - [[Redux could make you happy.]]
        - [[Improved Tool selection]]
        - [[If you draw with a pen while zoomed out, it rattles.]]
- Priority is given to improving the state management system rather than speeding up small steps.
        - [[Faster drawing when updating sentences when creating stickies]]
        - [[Faster path movement]]
        - [[Faster moving of stickies]]
    - [[Highlight sticky note being edited]]
    - Selection and highlighting status management
- Shouldn't DefaultTool's highlight/deselect be integrated with Selection's?
- [https://github.com/nitin42/Making-a-custom-React-renderer/blob/master/part-one.md](https://github.com/nitin42/Making-a-custom-React-renderer/blob/master/part-one.md)
    - > In this section, we will create a React reconciler using react-[[reconciler]] package. We are going to implement the renderer using [[Fiber]]. Earlier, React was using a stack renderer as it was implemented on the traditional JavaScript stack. On the other hand, Fiber is influenced by algebraic effects and functional ideas. It can be thought of as a JavaScript object that contains information about a component, its input, and its output.
    - [acdlite/react-fiber-architecture: A description of React's new core algorithm, React Fiber](https://github.com/acdlite/react-fiber-architecture)
    - All state updates are in the undo list, which is not appropriate
    - [[Multiple Movement Issues]]

---
Organize your understanding of state management renewal
- Essentially, this app is "an app that renders to HTML5 Canvas
- Using Paper.js instead of drawing directly in Canvas (for rounding off hit judgments, etc.)
- When the React-like state is updated, all Paper#Item is destroyed and regenerated.
- That implementation works fine on Chrome on PC.
- Uncomfortable flashing on "stickies with images" in Safari on iPad, Chrome, and Safari on PC, regardless of the number of stickies.
- Probably only Chrome on PC, caching images in a layer (=browser) below Paper.js
- Paper#item must not be discarded in order to work comfortably on iPad
- That means that when the React-like state is updated, the Paper.js layer needs to deal with it by modifying or moving existing objects
- This is almost the same processing that React does for the DOM, and it is handled by the Reconciler
- You need to implement your own Reconciler or use an existing implementation. I don't want to implement it, so use react-paper-bindings
- Attach [[unique identifier]] to the object

- In addition, the entire state is currently subject to UNDO, but UNDO will be changed to push snapshots as needed.
-----
- As for the state substitution, we should first try to have a [[unique identifier]] and see if we can't use the same mechanism that react uses to render the list, and avoid creating our own differential rendering if at all possible.
- However, the final output is a list of elements in paper.js, so we can't use the DOM manipulation methods, so we need to figure out how to do that.
- Observation of how react-paper-binding is implemented
    - [https://github.com/react-paper/react-paper-bindings/blob/master/src/View.js#L51](https://github.com/react-paper/react-paper-bindings/blob/master/src/View.js#L51)
        - From componentDidUpdate, we call PaperRenderer.updateContainer, and this PaperRenderer is a Reconciler
- The point that an object must have a unique ID is called Key in React language.
    - [https://reactjs.org/docs/reconciliation.html](https://reactjs.org/docs/reconciliation.html)
    - When there is an update to a component that has child elements in the

- [https://github.com/nitin42/Making-a-custom-React-renderer/blob/master/part-one.md](https://github.com/nitin42/Making-a-custom-React-renderer/blob/master/part-one.md)

- Looks good because it uses react-paper-binding
    - [https://github.com/psychobolt/react-paperjs](https://github.com/psychobolt/react-paperjs)
    - And as for which is better, I can't make a decision.
    - This one was last updated more recently.
    - I think react-paper-binding has more contributors.

state management
    - [[Issue with slow rendering of image stickies on iPad]]
    - > I'm sure the ideal of "100 image stickies and no flickering" can be achieved if you work on the deeper aspects of the design.
        - This one, not so easy when it comes to "keeping UNDO functioning."
        - That said, I'm not sure I'd want to throw away the UNDO feature...
- Organizing the Issue
    - When I looked into the UNDO/REDO mechanism that made sense with React's state management, I found that the two implementations I referred to were both "redrawing everything when the state is updated," which made me wonder at the time if that was a good idea. Wouldn't that cause performance problems? Shouldn't it be managed in terms of revision differences? Then I started to think
    - > I'm a bit bewildered, but too early optimization is the root of all evil, so I'll start by creating an implementation that retains the entire state history.
    - So, we made the decision to use the new system. But, surprisingly, we didn't have any performance problems even when we put out 100 sticky notes and moved them around.
    - So, we've come this far and finally had a problem with the "100 image stickies on the iPad" requirement.
- Even with a single image, the behavior is that "the image is drawn with a delay of 0.5 to 1 second on the iPad," so to solve this problem, the implementation must be such that objects that have already been drawn are used as much as possible.

- Do we need to treat Paper.js's tree of objects like React's virtual DOM?
    - Is this how you would approach it?
        - [https://github.com/psychobolt/react-paperjs](https://github.com/psychobolt/react-paperjs)

- I want to be able to co-edit.
        - [[Even one person needs to co-edit.]]
    - I still want to move stickies around with my finger on the iPad.
    - As for adding stickies, I want to use the keyboard, so I want to do it on my PC.
    - Because I opened it in two places in edit mode, I made the mistake of editing one and overwriting the other. w
    - After all, even if it is used by one person, collaborative editing should be possible (conclusion).
    - The reason why co-editing is turned off now is that "if one editor is in the middle of dragging and the other editor's edit arrives and the object is re-created, it will die because it cannot find the object to be dragged when the drag is complete". So, in the end, it should be a mechanism that Paper#Item has a reference to a state object (StateItem) on React, and all StateItem have a unique ID, and when the drag is completed, the object with that ID is searched for in the scene tree and updated.

---
This page is auto-translated from [/nishio/状態管理](https://scrapbox.io/nishio/状態管理) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
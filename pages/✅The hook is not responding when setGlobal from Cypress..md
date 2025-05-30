---
title: "✅The hook is not responding when setGlobal from Cypress."
---

- I was able to [[Expose ReactN]] to the point where I could setGlobal in the console and useGlobal on the component side would detect the change and redraw it.
However, when setGlobal is called from within the [[Cypress]] test code, the update is not detected.
- →SetTimeout was solved by interrupting the setTimeout.
    - [[2021-07-15Movidea Development Diary]] I tried to run synchronously by default and asynchronously only when there was a problem, but all the tests passed with synchronous calls. I tried to make it asynchronous by default only when there was a problem, but all the tests passed with synchronous calls.
    - Nothing I did fixed it!"
    - Reconsider after the problem is reproduced.
- 2021-08-24 I've been on this thing for a month with all synchronous calls, and I haven't had any problems.
    - I wonder if the Cypress side has been updated to handle React better or something.

solution
This had nothing to do with the fact that the context is separated by iframes, it was the behavior around asynchronous

Explain with a minimum of code
First, a simple component, setGlobal with useEffect (1)
App.tsx

```
function App() {
  const [fusens] = useGlobal("fusens");
  console.log("render");
  useEffect(() => {
    console.log("useEffect");
    window.movidea.callSetGlobal(); // (1)
  }, []);

  return (...);
}
```


At this time, after the component body runs, useEffect runs, in which it is setGlobal and redrawn when it detects it.
:

```
render
useEffect
call setGlobal
render
```


Now comment out (1) and setGlobal on the test case side (2)
test.js

```javascript
describe('adjust font size', () => {
  beforeEach(() => {
    cy.visit('/')
    cy.window().its('movidea').then(movidea => {
      console.log("movidea resolved")
      movidea.callSetGlobal()  // (2)
    });
  })...
```


At this time, after the first drawing, setGlobal is called before useEffect is called, and this update is not detected
:

```
render
movidea resolved
call setGlobal
useEffect
```


What happens if this call (2) is made asynchronous by interrupting setTimeout (3)
test.js

```javascript
describe('adjust font size', () => {
  beforeEach(() => {
    cy.visit('/')
    cy.window().its('movidea').then(movidea => {
      console.log("movidea resolved")
      setTimeout(movidea.callSetGlobal, 0)  // (3)
    });
  })...
```


In this case, setGlobal is called after useEffect, and the change is detected and redrawn as expected
:

```
render
movidea resolved
useEffect
call setGlobal
render
```


So the work-around would be to make the state updates from the test case asynchronous, but it's a delicate solution...

--- log
[Testing Redux Store](https://www.cypress.io/blog/2018/11/14/testing-redux-store/)
- If you go into the app console from the Cypress test screen and setGlobal, the screen will update.
- But when I invoke from Cypress test code as described in this solution, the screen does not update.
- The value is updated without error, and when getGlobal is done, the value is properly entered.

I've tried this, which is the equivalent of explicitly creating a store in ReactN, but it doesn't work as expected.
[https://github.com/CharlesStover/reactn/blob/master/Provider.md](https://github.com/CharlesStover/reactn/blob/master/Provider.md)

What we found out
- Cypress and the application under test are each running in an iframe.
    - ![image](https://gyazo.com/e26319be12d0196b26f9a1590dff7e0e/thumb/1000)

What we don't know
- If Provider is not used, each frame uses defaultGlobalStateManager
    - Is this what separates each FRAME?
    - Since you need a global existence somewhere to create a singleton object, can it be a separate object if it's tied to a window and you're distinguishing it?
- Isn't Provider the solution to those problems?
    - I'm creating a GlobalStateManager at initialization.
    - Since that's what they give you in the other FRAMES, why not use that?

Hmmm, I thought it would be nice to be able to test the display by tweaking the state from a test case...

---
This page is auto-translated from [/nishio/✅CypressからsetGlobalするとフックが反応しない](https://scrapbox.io/nishio/✅CypressからsetGlobalするとフックが反応しない) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
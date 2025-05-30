---
title: "Expose ReactN and use it from Cypress."
---

- [[Expose ReactN]] and use setGlobal from [[Cypress]] to create a state for testing.

I was able to do it.
![image](https://gyazo.com/4555d5f590786e4b4d2a4982ddf31aec/thumb/1000)

App.tsx

```
function App() {
  const [fusens] = useGlobal("fusens");
  return (...);
}
```


index.tsx

```
setGlobal(INITIAL_GLOBAL_STATE);
const movidea = {
  getGlobal,
  setGlobal,
};

const debug = {};

declare global {
  interface Window {
    debug: any;
    movidea: typeof movidea;
  }
}

window.movidea = movidea;
window.debug = debug;
```

For an explanation, see [[Expose ReactN]].
- I have setGlobal, etc. in movidea (app name) to make it easier for users (mainly me) to hack when the app is released, but I think it is also possible to design it in the debug and remove it in the release build.

test code
cypress/.../adjust_font_size.js

```javascript
/// <reference types="cypress" />

describe('adjust font size', () => {
  beforeEach(() => {
    cy.visit('/')
    let a = 1;
    let b = 1;
    const fusens = [];
    for (let i = 0; i < 11; i++) {
      [a, b] = [b, a + b];
      fusens.push({
        text: ">" + "a".repeat(a),.
        x: 50 * i,
        y: 50 * i,
      });
    }
    cy.window().its('movidea').then(movidea => {
      setTimeout(() => {
        movidea.setGlobal({ fusens });        
      })
    });
  })

  it('fusen sizes', () => {
    cy.get('.fusen').should('have.length', 12).first()
      .should("have.css", "font-size", "66px")
      .should("not.have.css", "align-items", "flex-start")
    cy.get('.fusen').eq(1).should("have.css", "font-size", "53px")
    cy.get('.fusen').eq(2).should("have.css", "font-size", "38px")
    cy.get('.fusen').eq(10)
      .should("have.css", "font-size", "10px")
      .should("have.css", "align-items", "flex-start")
  })
})
```

For setTimeout see [[✅The hook is not responding when setGlobal from Cypress.]]


---
This page is auto-translated from [/nishio/ReactNを露出してCypressから使う](https://scrapbox.io/nishio/ReactNを露出してCypressから使う) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
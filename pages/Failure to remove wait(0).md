---
title: "Failure to remove wait(0)"
---

js

```javascript
describe('adjust font size', () => {
  beforeEach(() => {
    cy.visit('/')
    // cy.wait(0) // THIS
  })

  it('first fusen', () => {
    cy.get('.fusen').first().should("have.css", "font-size", "66px")
  })

```


without wait(0)
![image](https://gyazo.com/2e442aa6fdfa6f0d2e91538058d09b26/thumb/1000)

with wait(0)
![image](https://gyazo.com/fcb7795a50d64eb212a0ac9bf185326e/thumb/1000)


---
This page is auto-translated from [/nishio/wait(0)を削ると失敗する](https://scrapbox.io/nishio/wait(0)を削ると失敗する) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
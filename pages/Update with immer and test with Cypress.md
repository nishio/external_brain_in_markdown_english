---
title: "Update with immer and test with Cypress"
---

- [Expose ReactN and use it from Cypress,
Update the status with [[immer]] and test with [[Cypress]].

It's done.
test.js

```javascript
cy.contains("DEF").should("have.css", "width", "260px");
cy.window()
  .its("movidea")
  .then((movidea) => {
    movidea.updateGlobal((g) => {
      g.itemStore["3"].scale = 3;
    });
  });
cy.contains("DEF").should("have.css", "width", "390px");
```

![image](https://gyazo.com/52722b57be6389fc6ebef2b0825a6cd0/thumb/1000)

By the way, the test code is the default JS, but this makes the g in updateGlobal any.
I'm going to Typo sooner or later because completion doesn't work... and then I immediately Typo and say "I updated the position but the position doesn't change, aren't you reading the position value when you draw? The position isn't updating?" And I did.
![image](https://gyazo.com/aa50d968a68da1936e93ddd738262053/thumb/1000)

continued [[TypeScripting Cypress]].
---
This page is auto-translated from [/nishio/immerで更新してCypressでテスト](https://scrapbox.io/nishio/immerで更新してCypressでテスト) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "Cypress"
---

Testing framework that runs in the browser
Unlike testing with [[jest]]+[[jsdom]], there are no limitations due to the jsdom implementation because it uses the actual browser

Summary: The
- No need to distinguish between synchronous and asynchronous
    - Today's WebUI cannot be described without asynchronous updates.
    - It is burdensome for the person writing the test to figure out which operations to test are asynchronous and specify the appropriate wait.
    - So write the test description with a combination of "command to repeat retry for 4 seconds by default".
    - This makes the synchronous-asynchronous distinction unnecessary.
- Declarative description
    - Test cases are not written procedurally in raw JS,
    - Write declaratively by connecting commands and assertions with a jQuery-like method chain.
    - The code is apparently synchronous, but the test content is built synchronously and then it is executed asynchronously.
    - This is the same as saying, "I create a chain of Promises synchronously, but they are resolved asynchronously later.
    - Therefore, when you want to do something that cannot be expressed in the method chain, you can pass a function to the then method.

- Cypress accesses a server by specifying a URL and tests against it.
    - Other test runners have a form of render a specific component and test against it, but with Cypress that functionality is alpha and uses jsdom, so it doesn't work for my purposes [doc [https://docs.cypress.io/guides/](https://docs.cypress.io/guides/) component-testing/introduction]
    - We can test for values exposed in the form of window.app.foobar.
        - There's probably no way to access the unexposed internal state.
            - From the testing side, the test object is a black box.
        - There are tools such as spy, but they are a little more restrictive as they can only be used on exposed values.

- Tests are automatically re-run after editing source code.
    - I can normally use chrome devtool to inspect from there when the test is rubbish.
    - It would be better to write a test first, instead of checking the operation of a normal browser by a human operator.


JavaScript End to End Testing Framework [https://www.cypress.io/](https://www.cypress.io/)
> Cypress does not use [[Selenium]].
> Whereas Selenium executes remote commands through the network, Cypress runs in the same run-loop as your application.
[https://www.cypress.io/how-it-works/](https://www.cypress.io/how-it-works/)

[Introduction to Cypress | Cypress Documentation](https://docs.cypress.io/guides/core-concepts/introduction-to-cypress)
> This is the single most important guide



It's done.
![image](https://gyazo.com/b39c9e4c072c6cb62a32e71ab249b5d4/thumb/1000)
It's done.
- I was able to test the font size of a sticky that was first mounted and then updated with useEffect, and it took less than a second to complete all three tests, even though it was repeated three times from the visit.
    - [[Failure to remove wait(0)]]
    - I don't know what role wait(0) plays.
    - I added the eslint plugin for Cypress to solve [['cy' is not defined]] and now it tells me to "stop waiting".
    - The documentation seems to indicate that a retry is performed when an assertion fails, but why is this not the expected behavior?
        - If I grab an element with FIRST and then retry when another element appears in front of it, does it not change what FIRST points to?
        - I think I read a similar story early in the sample.
- ver. 2
    - I've started to add an ID for testing.
js

```javascript
/// <reference types="cypress" />

describe('adjust font size', () => {
  beforeEach(() => {
    cy.visit('/')
  })

  it('first fusen', () => {
    cy.get('.fusen[data-testid=">A"]').should("have.css", "font-size", "66px")
  })
})
```

- another patten
    - NG:
        - `cy.get('.fusen').eq(1).should("have.css", "font-size", "53px")`
        - Timed out retrying after 4000ms: Expected to find element: 1, but never found it. Queried from element: <div#hidden-fusen.fusen>
    - OK:
        - `cy.get('.fusen').should('have.length', 12).eq(1).should("have.css", "font-size", "53px")`
- Only the last command is retried.
    - > Cypress commands only retry the last command before the assertion
        - [https://docs.cypress.io/guides/core-concepts/retry-ability#Only-the-last-command-is-retried](https://docs.cypress.io/guides/core-concepts/retry-ability#Only-the-last-command-is-retried)
    - Here it is.
    - The problem was caused by the misunderstanding that "only the last command is retried" means "the entire chain is retried.
    - When there are multiple commands in a row, the first one is not retried.


[Assertions | Cypress Documentation](https://docs.cypress.io/guides/references/assertions)




-----
[Introduction to Cypress - Even Beginners Can Easily Create E2E Tests | Future Technology Blog](https://future-architect.github.io/articles/20210428a/)
    - [[E2E Test]]

[Cypress - Configuration | Future Technology Blog](https://future-architect.github.io/articles/20210428b/)
- Specify baseUrl in the configuration to prevent hardcoding in the test code
- Separate tsconfig for mocha+chai and jest because of conflicts with expect, etc.
- Frequent operation patterns can also be defined as commands, but a type definition file is required because a type error will occur in TS.
    - 🤔Wouldn't it be better to summarize it in a normal function...
        - I don't see the benefit of going to the trouble of defining the type and making it a cy method.

[Encapsulated Cypress for easy maintenance and extension | Future Technology Blog](https://future-architect.github.io/articles/20210428c/)
- What do you mean by the word 🤔encapsulated?
    - Does it not mean to summarize the data and procedures, nor does it mean to restrict access to them, but simply to say "we have put them together"?

[Cypress - Secrets of easy-to-write tests and implementation of proprietary commands | Future Technology Blog](https://future-architect.github.io/articles/20210428d/).
- @testing-library/cypress Some
- > Cypress has a different API granularity from WebDriver-based (Selenium) and Chrome DevTool Protocol-based (Puppeteer) tools.
- Cypress Retry Policy
- Declarative writing is weak feedback when it fails.
- The log output is Cypress.log

[E2E Testing Starting with React + TypeScript + Cypress - GiXo Ltd.](https://www.gixo.jp/blog/16086/amp/)


- [[Browser Test]]


---
This page is auto-translated from [/nishio/Cypress](https://scrapbox.io/nishio/Cypress) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
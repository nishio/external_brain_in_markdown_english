---
title: "Cypress Study Group"
---

2021-08-27
- [[Cypress]] written at the stage of using Kozaneba for testing for about a month, with additions made in the second month.

## Cypress runs test code inside a "real browser" such as Chrome
.
- Another approach is to use a "library that emulates the browser DOM
    - For example, [[Jest]] / [[jsdom]].
        - > Jest is provided with jsdom, which simulates the DOM environment as if you were using a browser. --- [DOM manipulation - Jest](https://jestjs.io/ja/docs/tutorial-jquery)
    - This approach would raise the issue of library adequacy.
        - For example.
            - getContext of canvas element is not implemented.
                - Most features of Regroup that use canvas could not be tested.
            - The scrollHeight of the div is always 0
                - Kozaneba font size auto-adjustment cannot be tested
        - A simple, common web app could be tested as if you were using a browser.
            - but when you try to do something a little more elaborate, you will bump into it immediately.
            - And <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>'s job is to do "something a little more elaborate...
    - The approach of using a real browser reduces this kind of problem considerably.
        - Not zero.
        - Example: no dataTransfer for dragstart event
            - Phenomenon that events synthesized by the test runner are slightly different from native events
        - Mimic user operations by creating and sending events
            - So, if for some reason the "events that occur when the user actually operates the browser" are different from those in the test case, the test will not notice it.
            - Example: a recent bug where the coordinates are shifted if the upper left coordinate of a group is changed by dragging within the same group.
                - The condition for reproducing the bug was that the mousemove event must occur for that group.
                - This was not occurring when mimicking a drag operation.
- Cypress first opens a specific page in the browser and then manipulates that page
    - (There is also a per-component test function, but since it is a beta version and uses jsdom, we will ignore it this time.)
    - Even services on other people's servers can be tested.
        - For example, you can do a test like, "If I do a share operation on my service, Twitter will open and this is what happens.
        - You can also test your service on the production server after deployment, rather than in a local environment.
            - Realistically, I don't think it can be done easily, for example, Firebase auth has to be replaced with an emulator to test, <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/> didn't do it.
    - Even services for which we do not have the source code can be tested.
        - <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>is putting the app code and the test code in the same repository, sharing type definitions, etc. and having VSCode complement them, though.

## Cypress runs test code "inside" the browser
.
- ![image](https://gyazo.com/966ce37818b54d52d17d3cbd946e70e0/thumb/1000)
- Compared to Selenium, which used to be well used
    - The HTTP server was embedded in the browser, and the test code operated by sending HTTP requests to the server.
    - Communication across processes seems slow? Actually, it was slow.
    - You can use Python or Java for writing tests, as long as you can send HTTP requests.
- Cypress in the same process
    - Since it runs in the browser, it must be written in JavaScript or TypeScript, which is converted to JavaScript.
- Note: Very deep down, there are problems caused by the split iframes.
    - [[Cypress+Firestore=invalid data]]

## Test-only language written in JS
.
- Cypress uses an in-language DSL to connect "get commands" and "assertions" to write tests.
    - I think it's very important to have this feeling, if you think you're writing raw JavaScript, you're wrong.
    - Imagine that executing JavaScript "builds the test by connecting the blocks" and then the test is executed after that is done.
- ![image](https://gyazo.com/1e2ed0d4667d0599a6b9f288684f752a/thumb/1000)
    - Automatically retries when acquisition or assertion fails for a default of 4 seconds
    - This makes it easier to deal with asynchronous behavior of the test object.
- For example, suppose the behavior under test is "press a button to make a network request and update the label when the result is returned".
    - Processing flow is cut off in the first half and the second half due to JavaScript specifications.
        - As a result, if you execute a "button press" from JavaScript, the process returns to the test code at the point of request
        - After the test code has finished running, the latter half of the "when the results are returned" section is executed.
        - ![image](https://gyazo.com/be4e5f522965311250fca1280dd6eae1/thumb/1000)
        - So, if you check synchronously in the test code after triggering the first half to see if the "label has been updated", it will fail for sure.
    - This happens because JavaScript in the browser is a cooperative multitasking mechanism, and some APIs are designed to "block and wait for processing is not allowed".
        - This is one of the reasons why writing tests for web apps is so difficult
    - One solution is to write test code that retries for a period of time until success
        - Cypress does it internally so humans don't have to write it in the test code.
        - Another tool, for example [[DOM Testing Library]], requires a human to write test code that explicitly calls [waitFor](https://testing-library.com/docs/dom-testing-library/api-async/#waitfor) provided by the library. that explicitly calls [[waitFor ]] provided by the library.

## Best Practices for DOM Acquisition
.
- Cypress is of the school that "elements accessed from tests should have a data attribute and be retrieved with an attribute selector".
    - Don't select by id or class."
    - What are data attributes?
        - [Using Data Attributes - Learn Web Development | MDN](https://developer.mozilla.org/ja/docs/Learn/HTML/Howto/Use_data_attributes)
        - Example: `<div data-testid="foobar">`
        - Selected by attribute selector `[data-testid="foobar"]`.
            - see [CSS Selector - CSS: Cascading Style Sheets | MDN](https://developer.mozilla.org/ja/docs/Web/CSS/CSS_Selectors)
    - This is because information such as id, class, display text, and DOM inclusions related to functionality and rendering can easily change during the implementation process, making tests more fragile.
    - Pointing to a specific element should be loosely coupled with function and drawing
        - If a particular id or class or display text or inclusion is really important, then make it an assertion, not an element fetch!
    - Cypress supports this.
        - >  Anti-Pattern: Using highly brittle selectors that are subject to change.
        - >  Best Practice: Use data-* attributes to provide context to your selectors and isolate them from CSS or JS changes.
        - >  ...
        - >  Don't target elements based on CSS attributes such as: id, class, tag
        - >  Don't target elements that may change their textContent
        - >  Add data-* attributes to make it easier to target elements
            - [Best Practices | Cypress Documentation](https://docs.cypress.io/guides/references/best-practices#Selecting-Elements)
    - <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>also supports this.
        - I also made a custom command to get it with data-testid.
    - On the other hand, there are those of the opposite ideology.
        - > Based on the Guiding Principles, your test should resemble how users interact with your code (component, page, etc.) as much as possible. With this in mind, we recommend this order of priority:
        - > 1. Queries Accessible to Everyone ...`getByRole('button', {name: /submit/i})` ... `getByLabelText` ... `getByPlaceholderText` ... `getByText` ... `getByDisplayValue`
        - > 2. Semantic Queries ... `getByAltText` ... `getByTitle`
        - > 3. Test IDs ... `getByTestId`
        - >  getByTestId: The user cannot see (or hear) these, so this is only recommended for cases where you can't match by role or text or it doesn't make sense (e.g. the text is dynamic).
            - [About Queries | Testing Library](https://testing-library.com/docs/queries/about/#priority)
        - In short, "DOM should be selected based on values that look like human behavior.
- My problem now, a little over a month after I wrote this.
    - Talk about data-testid or id-independent.
        - Under the policy of "selecting elements with a single string," this string corresponds to "the name of a variable in the global scope.
        - Problems with global variables occur here as well.
        - Example: The
            - T1: Add Kozane button in Add Kozane dialog with testid: `add-kozane-button`.
            - T2: Added Split Kozane dialog
            - T3: There is also an Add Kozane button in the Split Kozane dialog, what do we do?
    - Difficult for humans to remember the correspondence between elements and names
        - Well, I'll check the source for the test subject.
    - Possibility of unintentional duplication
    - If you treat it as a string, you won't notice the typo.
    - Do you want to 🤔 string Enum? (I haven't done it)
    - → Discussion
        - Typo is immediately noticed because the test is mocked up as "no such testid element" immediately.
        - As for unintentional duplicates, you can assert whether the one retrieved by cy.get is one or not, and you can notice immediately when there is more than one unintentional duplicate.

## test pyramid
- UI testing is slow and expensive
- Unit testing is fast and inexpensive
- So we should do a lot of unit testing.
- ...which was written by Martin Fowler in 2012 [article](https://martinfowler.com/bliki/TestPyramid.html).
- <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>is written mainly for UI testing in Cypress, ignoring the
    - I'll write a unit test in Jest if I ever think I should write one.
        - With the default configuration of create-react-app, Jest unit tests run in the background every time a file is modified, and are easy to use without any additional installation.
        - The test case has 0 cases.
    - State with more UI testing than unit testing
        - UI testing is faster and less expensive than in the days of Selenium, then the ratio should change.
        - I'm typing in a style that doesn't allow any in TypeScript, so I can say that type integrity testing is done.
        - Since the UI is tested, the logic called from it is also tested, of course.
        - So I don't have anything in particular I want to unit test.
        - Since we are mainly making the UI part now, it may mean that the UI is the only thing we have to test.
            - ![image](https://gyazo.com/85ee5fcf8126a1850a540a0ab530edcf/thumb/1000)
    - UI testing is fragile."
        - We should distinguish whether this is "the function is not broken, only the test is broken" or "the function is broken".
        - When UI testing was done in a way like "hard-code the coordinates to click" or "wait 100ms to test asynchronous processing", there were many "tests only break".
            - It should be decreasing with the refinement of testing tools.
            - Cypress auto-retries, fixed viewports, and other things are making UI testing more reproducible.
        - If you're doing something complex with the UI, the latter "broken functionality" is more likely to happen.
            - But this is likely to happen, which is why it should be tested and noticed as soon as possible.
            - With Cypress, for example, the test code "click this button" automatically tests if the button is not covered by other elements, if it is visible on the screen, etc.
                - Example: When a user dialog was opened and closed, the previous menu was forgotten to be closed.
                    - I noticed that the "close dialog and press tutorial icon to resume tutorial" test FAILS.
                    - Detected that the DOM covering the tutorial icons for the realization of "Close the menu when you click on the non-menu part".
    - This may be due to the fact that the specifications are not set in stone, so development starts with "this is what I want the display to look like when the internal state is like this".
        - First, set the internal state with the test code, then look at the Cypress screen to see if the display is as expected.
            - The fact that it runs in a browser and a human can visually observe the state after execution works.
            - If something is wrong here, you can use Chrome's developer tools or something to investigate.
            - One month later and added:.
                - It's a utility cutout of the "function that sets the internal state."
                - For example, "groups are nested" or
                - There are test cases that just "put the screen in its internal state" without specific tests, and the screen in a specific internal state can be immediately brought up and operated by a human.
        - If there is a bug report and you want to fix it, a little manipulation from the existing state will confirm that "the screen is not as expected".
            - A means of reproduction was found here.
            - Add test code to reproduce this "not the expected screen".
            - And fix the bugs.
            - When you get to the expected screen, make that an assertion in the test code.
        - Comparison: compared to modifying the code of the app itself to create a specific internal state
            - That way, after the work is done, the "code to create the internal state" has to be properly deleted.
            - If you're using Cypress style, it's test code, so you can leave it as is and run it after you've made other changes.
        - Comparison: compared to checking by hand
            - There are many environments that automatically reload the browser after editing a file, but it would be tedious to repeat the same operation by hand from there.
                - I made a mistake and had to reload and start over...
                - I thought I was repeating the same operation, but I made an operational error...
            - Automate the process of opening a specific page and performing a specific operation with test code first.
                - Can operate faster than a human can.
                - And it can be operated accurately and reproducibly.
                - For example, you can test the drag function by dragging exactly 10 pixels, then it should be this value.
                - Techniques to make various numerical values characteristic
                    - Put a characteristic value (42, 123, etc.) for each of the values that might be affected.
                    - You can observe the results and make a decision like "42 shift means that the bug is related to this value.
                - You can look back at a snapshot of the DOM at each step of the operation so you can see where things went wrong.
                    - After performing various operations, you may say, "Huh? Is it a little off?"
                        - You can go back in time and see which operation timing was off.
                    - Example: "4-pixel shift bug" was found with it.
                    - I might have missed it if I was operating it by hand.
- Postscript of 2021-08-24
    - I did a major surgery to realize all Kozane's drags and clicks with onMouseDown system without using onDragStart or onClick, so most of the tests were broken.
        - Well, that's just the way it is...

## internal state setting API
.
- <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>manages the internal state with [[ReactN]].
- The functions for reading and writing this are exposed as a JS API so that the internal state can be set from the outside.
    - PS: I further made it a custom Cypress command.
- This allows you to set up and test the internal state of the app from the test code.
ts

```typescript
  it("show loading dialog", () => {
    cy.updateGlobal((g) => {
      g.dialog = "Loading";
    });
  });
```

    - I felt like I should explain more about this place.
    - ![image](https://gyazo.com/ef5ebeddb670b083dc1a664b2923b2d2/thumb/1000)
    - To begin with, singleton-like internal state management objects are introduced by ReactN
    - The View is designed to be redrawn when its internal state changes by hooking (using) the object.
    - This internal state get/set is exposed to the test environment
    - If you set, the screen will be updated, so you can test "how it will be displayed if the internal state is such and such value".
    - You can also get and test "what is the internal state after a specific operation".
- It's only supposed to be exposed on localhost, so I can't touch it in the release environment.
    - Microwave Oven Parable
        - The contents of a microwave oven are dangerous if accidentally touched, so there should be a cover when the public is using it.
        - Anyone developing a microwave oven should be able to easily remove the cover and access the interior.
- React-like state checks for changes by object identity, so destructive updates are prohibited.
    - With [[immer]], you can comfortably write destructive updates in a non-destructive manner.
        - A copy of the non-destructive state is passed to the callback, which destructively rewrites it, and immer internally converts it to a non-destructive update.
    - So the code to update using immer is also a custom command.
    - This is very useful to rewrite a little internal state in a test case and check it.

## Custom assertions
.
- The assertion part of Cypress is [[Chai]], so you need to learn how to write Chai.
- Not doing much.
- I just added an assertion that confirms the position on the screen.
    - Would it match if I created a custom command "get the on-screen position of a given element and return it", or can I use the original one for assertions? I initially thought that would be a good idea, but that approach doesn't work.
    - That custom command succeeds, so if it fails in a subsequent assertion, no retry is made.
ts

```typescript
it("drag inside", () => {
  ready_one_group();
  cy.testid("1").should("hasPosition", [184, 199]);
  do_drag("1", "G1", 0, 0);
  cy.testid("1").should("hasPosition", [154, 144]);
});
```

- Self-tweezers who say `should have`.
    - I wanted to do `cy.testid("1").hasPosition(154, 144)` but I couldn't figure out how to do it, so I ended up with this

- Small story
- Test cases are now started with `test_`.
    - I wanted to make it easier to distinguish between test cases and non-test cases when opening a file by typing part of the file name with Cmd+P in VSCode.
- If you use Firebase Auth to use Google or other OAuth-based logins, an emulator is probably a must.
    - Normal OAuth flow doesn't seem to work in the test environment.
- When using Cloud Firestore
    - I use an emulator.
        - Editing object contents, etc., is as easy as in a production environment
        - Easier than production to change access control rules, etc.
            - If you change a local file, it's automatically reloaded and applied immediately.
    - Using it from Cypress is... using it, but it's been a rocky road to get it to work.
        - ExperimentalForceLongPolling must be set to true
        - You need to do this before you useEmulator.
            - [[Kozaneba Development Diary 2021-08-03#610a84dfaff09e0000e3b656]]
        - Objects created in the Cypress environment cannot be saved directly to Firestore
            - It's the iframe.
            - [[Cypress+Firestore=invalid data]]
            - Object.assign` on the app side
- When using Google Analytics
    - I'm crushing it by overwriting the gtag so it doesn't work on localhost.
    - Otherwise, the test run will throw away a cookie each time, thus recording "300 new users" and so on.
- I also write my test code in TypeScript.
    - I am already familiar with TypeScript...
    - At first I wrote it in JS, but I typo'd `position` with `positionision` and did "Hey, I changed the position, but it doesn't work, why?", so it was a waste of time.
    - Hard to create GUI without completion and type checking

---
This page is auto-translated from [/nishio/Cypress勉強会](https://scrapbox.io/nishio/Cypress勉強会) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
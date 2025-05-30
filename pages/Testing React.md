---
title: "Testing React"
---

- [test summary](https://ja.reactjs.org/docs/testing.html)
    - > React components can be tested just like any other JavaScript code.
- [Recipes for Testing](https://ja.reactjs.org/docs/testing.html)
    - > A collection of common test patterns for React components.
    - Good explanation of how to test React apps with Jest.
    - `jest.spyOn` [doc](https://jestjs.io/docs/ja/jest-object#jestspyonobject-methodname)
        - Replace methods with mocks
        - If no implementation is given, use the original implementation by default
            - Giving the implementation `jest.spyOn(object, methodName).mockImplementation(() => customImplementation)`
        - What is the point of a mock that uses the original implementation?
            - It will be observable what arguments the mock was called with, what values it returned, what exceptions it threw, etc. [doc](https://jestjs.io/docs/ja/mock-function-api)
        - They're called "methods", but they're not limited to class methods. If you want to rewrite a module's top-level functions, just name the module and import it.
            - `import * as fooModule from './foo';`
        - Can also spy on setter / getter [doc](https://jestjs.io/docs/ja/jest-object#jestspyonobject-methodname-accesstype)
    - You can also replace an entire module with a mock with `jest.mock` [doc](https://jestjs.io/docs/ja/jest-object#jestmockmodulename-factory-options).
    - Bubbles are required when throwing an event.
    - Processes that use timers mock timers.
    - Snapshot Testing [doc](https://jestjs.io/docs/ja/snapshot-testing)
        - They'll take a snapshot and check for any discrepancies.
        - Some are saved in a separate file and others are embedded in the test code
        - Not just the DOM.
        - When the snapshot no longer matches the snapshot due to intentional changes, use `jest --updateSnapshot`.
        - Values that change from snapshot to snapshot, for example the date of creation, are filtered by the first argument `propertyMatchers` [doc](https://jestjs.io/docs/ja/snapshot-testing#property-matchers).

- `mockFn.mockImplementationOnce` [doc](https://jestjs.io/docs/ja/mock-function-api#mockfnmockimplementationoncefn)
    - Replace the implementation only once.

- [Test Utility - React](https://ja.reactjs.org/docs/test-utils.html)
    - [React Testing Library | Testing Library](https://testing-library.com/docs/react-testing-library/intro/)
        - Test as close as possible to the user's actual usage conditions.
        - →User sees the label on the DOM and presses the button.
        - Successor to Enzyme
        - [[Mock Service Worker]]


- [test environment](https://ja.reactjs.org/docs/testing-environments.html)
    - > This document will outline the factors that affect your environment and recommendations for several scenarios.



[[test]] in [[React]].

---
This page is auto-translated from [/nishio/Reactのテスト](https://scrapbox.io/nishio/Reactのテスト) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
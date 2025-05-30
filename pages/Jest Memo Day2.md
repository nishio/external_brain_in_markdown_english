---
title: "Jest Memo Day2"
---

from  [[Jest Memo]]
Jest Memo Day2
- Mysterious behavior of test utility
    - Conclusion: Stop using ReactTestUtils
    - [Test Utilities - React](https://ja.reactjs.org/docs/test-utils.html) and follow the recommendation to use [React Testing Library | Testing Library [https://testing-](https://testing-) library.com/docs/react-testing-library/intro/] is recommended.
- At any rate, I thought I'd first render the component and observe.
    - `await render(<ShowLog talk="SJSLzd0PCLcJ3Nzlfdc4" />);`
:

```
(node:40175) UnhandledPromiseRejectionWarning: Error: FIRESTORE (7.24.0) INTERNAL ASSERTION FAILED: Unexpected state
(node:40175) UnhandledPromiseRejectionWarning: Unhandled promise rejection. This error originated either by throwing inside of an async function without a catch block, or by rejecting a promise which was not handled with .catch(). To terminate the node process on unhandled promise rejection, use the CLI flag `--unhandled-rejections=strict` (see https://nodejs.org/api/cli.html#cli_unhandled_rejections_mode). (rejection id: 36)
(node:40175) PromiseRejectionHandledWarning: Promise rejection was handled asynchronously (rejection id: 36)
```

    - Hmmm, it seems that calling Promise to access Firestore with await causes an error.
    - On the other hand, if you don't await, the process moves on to the next code before you get the data.
    - Split the "read data -> setGlobal" code in two, return Promise when you are done taking data, and then expect in then of it [doc [https://jestjs.io/docs/en/asynchronous#](https://jestjs.io/docs/en/asynchronous#) promises]
ts

```typescript
test("show log", () => {
  return loadLogsFromFirestore("SJSLzd0PCLcJ3Nzlfdc4").then((talkObject) => {
    expect(talkObject).toMatchSnapshot();
  });
```

        - No, still `FIRESTORE (7.24.0) INTERNAL ASSERTION FAILED: Unexpected state`.
    - Stop accessing Firestore in your test code!
        - Firestore does its own retries and such, so it's probably best not to touch it in the test.
    - Display the values taken from Firestore at the top level of the application.
ts

```typescript
function App() {
  const [logs, setLogs] = useState("");
  loadLogsFromFirestore("SJSLzd0PCLcJ3Nzlfdc4").then((talkObject) => {
    setLogs(JSON.stringify(talkObject));
  });
  return <pre>{logs}</pre>;
```

    - Save this content to talkObject.json
        - `import * as MockTalkObject from ". /talkObject.json";` to read
    - Replace functions read from Firestore with mocks
ts

```typescript
  const m = jest
    .spyOn(loadLogsModule, "loadLogsFromFirestore")
    .mockResolvedValue(MockTalkObject);
```

    - I'm mocking it, but I get an error.
        - This is the kind of behavior where function calls in the same module are not replaced by mocking.
            - Added [[Jest mocking does not affect calls within the same module]].
        - I made the function to be mocked an independent module and it worked.
    - Moved so far.
ts

```typescript
test("show log", () => {
  const m = jest
    .spyOn(loadLogsModule, "loadLogsFromFirestore")
    .mockResolvedValue(MockTalkObject);

  // no talkID needed beacuse loadLogsFromFirestore is mocked
  render(<ShowLog talk="" />);
  screen.debug();
});
```

    - But we still haven't reached the desired test.
        - React's setState is asynchronous, so even if I do this, I get a DOM that says "data has been received but the screen has not yet been redrawn".
    - rerender? [doc](https://testing-library.com/docs/react-testing-library/api/#rerender)
ts

```typescript
  const { rerender } = render(<ShowLog talk="" />);
  rerender(<ShowLog talk="" />);
```

:

```
console.error
    Warning: An update to ShowLog inside a test was not wrapped in act(...).
    
    When testing, code that causes React state updates should be wrapped into act(...):
    
    act(() => {
      /* fire events that update state */
    });
    /* assert on the output */
    
    This ensures that you're testing the behavior the user would see in the browser. Learn more at https://reactjs.org/link/wrap-tests-with-act
```

    - No, I'm getting the same error message with this code alone before rerender, I'm wrapping what I'm told to wrap in act, but I'm getting an error.
ts

```typescript
  act(() => {
    render(<ShowLog talk="" />);
  });
```

    - Review sample [doc](https://testing-library.com/docs/react-testing-library/example-intro)
        - You're waiting until certain elements appear.
            - `await waitFor(() => screen.getByRole("heading"))`
            - There's no way to know if it's been re-rendered, so it's a wind-up argument that waits over and over again to determine if an element is present.
        - However, there are no new elements that appear in this test, especially since the log is waiting to be loaded.
            - No, wait, the log data is fixed in the mock, so you just have to wait for the appropriate string to appear in the log.
        - Done, debug confirmed the logs are rendered.
ts

```typescript
test("show log", async () => {
  const m = jest
    .spyOn(loadLogsModule, "loadLogsFromFirestore")
    .mockResolvedValue(MockTalkObject);

  // no talkID needed beacuse loadLogsFromFirestore is mocked
  render(<ShowLog talk="" />);
  await waitFor(() => screen.getByText("🙁"));
  screen.debug();
});
```

    - Snapshot the text that is output as the export content when you choose Export from the menu.
ts

```typescript
const m2 = jest.spyOn(RegroupDialogModule, "openRegroupDialog");
fireEvent.click(screen.getByLabelText("menu"));
fireEvent.click(screen.getByText("Export for Regroup"));
expect(m2).toHaveBeenCalled();
expect(m2.mock.calls[0][0]).toMatchSnapshot();
```

        - `[0][0]` means the first argument of the initial call
    - This was tested as expected.

- yesterday
    - ![image](https://gyazo.com/29e227d54e0659616f0efb73f7f60c1c/thumb/1000)
- today
    - ![image](https://gyazo.com/08401b0c38956da44c29a55d969cefa8/thumb/1000)
- and they all lived happily ever after (traditional ending to stories)

remaining
![image](https://gyazo.com/2e99067085ced9ee46727cb443ad1fb5/thumb/1000)

Oh, yesterday's test was commented out in changing the framework. That's why NewTalk's coverage is so low.
Next time, rewrite yesterday's test with a new method.

--- matome
- ReactTestUtils [Test Utilities – React](https://reactjs.org/docs/test-utils.html#act)
    - > We recommend using React Testing Library
- React Testing Library:
    - > The @testing-library family of packages helps you test UI components in a user-centric way.  --- [doc](https://testing-library.com/docs/)
    - > The [[DOM Testing Library]] is a very light-weight solution for testing DOM nodes (whether simulated with JSDOM as provided by default with [[Jest]] or in the browser) [doc](https://testing-library.com/docs/dom-testing-library/intro/)
    - > [[React Testing Library]] builds on top of [[DOM Testing Library]] by adding APIs for working with React components. ... Projects created with [[Create React App]] have out of the box support for [[React Testing Library]] --- [doc](https://testing-library.com/docs/react-testing-library/intro)
    - [Example | Testing Library](https://testing-library.com/docs/react-testing-library/example-intro/)
    - [API | Testing Library](https://testing-library.com/docs/react-testing-library/api/#queries)
    - [About Queries | Testing Library](https://testing-library.com/docs/queries/about/)
- Jest
    - [The Jest Object · Jest](https://jestjs.io/docs/ja/jest-object)
    - [Testing React Apps · Jest](https://jestjs.io/docs/en/tutorial-react)
- [Promise - JavaScript | MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)

---
This page is auto-translated from [/nishio/Jestメモ Day2](https://scrapbox.io/nishio/Jestメモ Day2) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
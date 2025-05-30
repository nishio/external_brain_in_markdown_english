---
title: "Jest Memo Day1"
---

from  [[Jest Memo]]
Jest Memo Day1
2021-02-15
- Enter [vscode-jest
    - Starts to WATCH automatically.
- The default test for [[create-react-app]] suddenly rubs me the wrong way.
    - I don't understand what you mean by the mysterious message "undefined doesn't have a map."
        - ![image](https://gyazo.com/2f20a903f83e273c1e655ee01888d130/thumb/1000)
    - The OUTPUT tab shows specifically where I scraped it.
:

```
    TypeError: Cannot read property 'map' of undefined

      45 |   };
      46 | 
    > 47 |   const NGKW_Buttons = lastKeywords.map((x) => {
```

    - It was because the ReactN initialization I was doing in index.tsx was not running.
    - Similarly, Sentry initialization is not running.
        - This was an API access in the first place where I was using it, so I replaced it with a mock.
ts

```typescript
import * as getNewTalkID from "./getNewTalkID";
jest.spyOn(getNewTalkID, "getNewTalkID").mockImplementation(() => {
  getNewTalkID._gotNewTalkID("test");
});
```


- I'm not sure how to take snapshots.
    - The test edit caused it to run automatically, resulting in "Update snapshot?" and I pressed it when it popped up.
    - Snapshot test now passes.
    - ![image](https://gyazo.com/2e5d3fa95582b753e2352bf638fc6677/thumb/1000)
    - The snapshot is now named src/__snapshots__/App.test.tsx.snap

- KeyPress
    - I wanted to send a key press of the line feed key to a text area.
ts

```typescript
const textarea = container.querySelector("[id=textarea]");
...
act(() => {
  textarea?.dispatchEvent(
    new KeyboardEvent("keypress", {
      key: "Enter",
      bubbles: true,
    })
  );
});
```

    - Not responsive at all.
    - I've been searching, and there's mixed information on KeyPress, like you have to specify charCode, or you have to specify which, but if you specify either, you get a type error.
    - I was able to get there after referring to [Test Utilities - React](https://reactjs.org/docs/test-utils.html#simulate) and doing the following
ts

```typescript
import ReactTestUtils from "react-dom/test-utils";
...
ReactTestUtils.Simulate.keyPress(e, {
  key: "Enter",
});
```


- Show Coverage
    - Command Pallete: "Jest: Toggle Coverage Overlay" [doc](https://github.com/jest-community/vscode-jest#coverage)
    - In an if statement with only a then clause, such as the following, if only the then clause passes the test, it will be highlighted to the effect that "the branch is not covered".
ts

```typescript
if (props.visible) {
  return ...;
}
return null;
```

    - If you add an else clause at this time, it will not be highlighted (huh?).
    - Once you invert the conditional expression, of course the test fails.
    - Then when I undo it, it is not highlighted (huh?).
    - I was trying to switch things around and it broke lol.
        - ![image](https://gyazo.com/5a3eaaaeff76b79d1ab8f7723d2f8693/thumb/1000)
    - I restarted vscode and it's back to a decent display?
    - ![image](https://gyazo.com/a84a160e59f4fbded5736e83cb8a763d/thumb/1000)
    - Perhaps this is already not sane?
    - Does not match either figure in README

- Tapping on the command line
    - `$ npm test -- --coverage`
        - unsuccessful
    - `$ npm test -- --coverage --watchAll=false`
        - > react-scripts test runs Jest in watch mode by default, so you must explicitly specify --watchAll=false to remove watch mode.
            - [What to do when test coverage is not output in Create React App - Qiita](https://qiita.com/nbstsh/items/024391eb1c8ad068d2f6)
            - [https://github.com/facebook/create-react-app/issues/6888](https://github.com/facebook/create-react-app/issues/6888)
    - open `./coverage/lcov-report/index.html`
        - ![image](https://gyazo.com/544a8ffb93ea2d81f7a8ad6c64cb65a4/thumb/1000)
        - ![image](https://gyazo.com/ba313ac952cef099e3351d03f14ff4b4/thumb/1000)

I want to click on the menu icon and click on the menu that comes up.
- ![image](https://gyazo.com/86047ba4bcf1d8f5c93def3897b8fc17/thumb/1000)
- Yeah, two clicks and a ReactFiber error.

---
This page is auto-translated from [/nishio/Jestメモ Day1](https://scrapbox.io/nishio/Jestメモ Day1) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "jest-electron"
---

Run [[jest]] tests with [electron

- jest use JSDOM instead of a browser
- As a result, it can't handle canvas or storage.
    - `Canvas [object HTMLCanvasElement] is unable to provide a 2D context.`
- That's where electron comes in.
    - [hustcc/jest-electron: ❯ ⚛️The easiest way to run and debug test cases in electron with jest.](https://github.com/hustcc/jest-electron)
- Apps created with [[create-react-app]] require eject before configuration
- package.json
diff

```
+ "runner": "jest-electron/runner",
+ "testEnvironment": "jest-electron/environment",
- "testEnvironment": "jest-environment-jsdom-fourteen"
```

- Now we can run tests involving canvas.
- `$ DEBUG_MODE=1 npm test`
    - to display the browser and run the test.
    - Which means you'd expect the app screen to come up, but it doesn't...
    - I wonder how we'll see that screen when the test fails...
    - `$ npm test`
        - I couldn't see the console.log output even with various options when I did the following, but maybe it is supposed to be viewed on electron

---

`$ npm install --save jest-electron`

need eject before config
> Out of the box, Create React App only supports overriding these Jest options:
> These options in your package.json Jest configuration are not currently supported by Create React App:
    - • verbose
    - • runner
    - • testEnvironment
> If you wish to override other Jest options, you need to eject from the default setup. You can do so by running npm run eject but remember that this is a one-way operation. You may also file an issue with Create React App to discuss supporting more options out of the box.

- `$ npx create-react-app --typescript test-jest-electron`
- `$ cd test-jest-electron/`
- `$ npm run eject`

config
- package.json
- [Configuring Jest · Jest](https://jestjs.io/docs/ja/22.x/configuration)
diff

```
+ "runner": "jest-electron/runner",
+ "testEnvironment": "jest-electron/environment",
- "testEnvironment": "jest-environment-jsdom-fourteen"
```



:

```
console.error node_modules/jest-environment-jsdom-fourteen/node_modules/jsdom/lib/jsdom/virtual-console.js:29
    Error: Not implemented: HTMLCanvasElement.prototype.getContext (without installing the canvas npm package)
```


Keep the electron browser window for debugging, set process env DEBUG_MODE=1.
- DEBUG_MODE=1 jest
`$ DEBUG_MODE=1 npm test`

---
This page is auto-translated from [/nishio/jest-electron](https://scrapbox.io/nishio/jest-electron) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
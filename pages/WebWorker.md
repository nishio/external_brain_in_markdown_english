---
title: "WebWorker"
---

- Different from [[ServiceWorker]].
- Running heavy processing in a separate thread from the UI thread prevents the UI from freezing during processing
- Information is exchanged through message passing

- When creating a WebWorker, it is necessary to create a separate JS from the main body.
    - `var myWorker = new Worker('worker.js');`
    - [Using Web Workers - Web APIs | MDN](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API/Using_web_workers)
- But I want to share the code with the mainframe.
    - TS type definitions, utility functions that don't touch the DOM, etc.
    - I would like to implement it in TypeScript.
- It's done.
    - [https://github.com/nishio/tutorial-webworker-with-react/blob/master/README.md](https://github.com/nishio/tutorial-webworker-with-react/blob/master/README.md)



----memo
2020-03-16-2
- Cannot find module 'worker-loader!./webworker'.  TS2307
    - `import Worker from "worker-loader!./webworker";`
- [https://stackoverflow.com/questions/53818157/using-webpack-worker-loader-with-typescript-causes-cannot-find-module-error](https://stackoverflow.com/questions/53818157/using-webpack-worker-loader-with-typescript-causes-cannot-find-module-error)
    - typing/custom/index.d.ts

Uncaught TypeError: Failed to execute 'postMessage' on 'DedicatedWorkerGlobalScope': No function was found that matched the signature provided.

2020-03-16
- Based on the experiment on 2020-03-10
    - Raw webpack allowed multiple file outputs from multiple entry points.
    - Try to modify the webpack.config.js created by create-react-app
    - [https://github.com/nishio/learn-ww-wp-cra-t/commit/2b85f2fefb37d102989229b596622fee31632a47](https://github.com/nishio/learn-ww-wp-cra-t/commit/2b85f2fefb37d102989229b596622fee31632a47)
    - I was able to get multiple files out.
- problem
    - The specified output file name is not used as is.
        - Separate into chunks and assign hash values
        - This is the worst possible way to DISABLE it.
    - The output file is not usable until that
        - The webworker API expects there to be an on message at the top level of the script, but the actual output is as follows
        - This is the es2015 module syntax converted into a form that can also be executed in the browser via babel and webpack
        - What we need now is a combination of "this mechanism can be used to import" and "onmessage should be exposed in the global space without wrapping it in this mechanism".
            - How do we do it?
            - [Shimming | webpack](https://webpack.js.org/guides/shimming/)?
            - Here in worker-loader
            - The buildup to this point has helped me understand worker-loader!
ts

```typescript
(this["webpackJsonplaern-ww-wp-cra-t"] = this["webpackJsonplaern-ww-wp-cra-t"] || []).push([["webworker"],{

/***/ "./src/webworker.ts":
/*!**************************!*\
  !*** ./src/webworker.ts ***!
  \**************************/
/*! exports provided: onmessage */
/***/ (function(module, __webpack_exports__, __webpack_require__) {

"use strict";
__webpack_require__.r(__webpack_exports__);
/* harmony export (binding) */ __webpack_require__.d(__webpack_exports__, "onmessage", function() { return onmessage; });
console.log("webworker");
const onmessage = function (e) {
  console.log("Message received from main script", e);
  console.log("Posting message back to main script");
  postMessage(e, "*");
};

/***/ }),

/***/ 2:
/*!************************************************************!*\
  !*** multi (webpack)/hot/dev-server.js ./src/webworker.ts ***!
  \************************************************************/
/*! no static exports found */
/***/ (function(module, exports, __webpack_require__) {

__webpack_require__(/*! /Users/nishio/learn-ww-wp-cra-t/node_modules/webpack/hot/dev-server.js */"./node_modules/webpack/hot/dev-server.js");
module.exports = __webpack_require__(/*! /Users/nishio/learn-ww-wp-cra-t/src/webworker.ts */"./src/webworker.ts");


/***/ })

},[[2,"runtime-webworker",2]]]);
//# sourceMappingURL=webworker.chunk.js.map
```


2020-03-10
After yesterday's discussion, we decided it would be a good idea to delve into webpack
- First, create a small project for experimentation.
- Reference: [Getting Started | webpack](https://webpack.js.org/guides/getting-started/)
- Hit webpack directly on the command line and confirm that bundle.js is created

Entry points can be specified in the webpack configuration (e.g. index.ts)
- Maybe we should have two entry points, one for the main script and one for the worker.
- [Multi Page Application](https://webpack.js.org/concepts/entry-points/#multi-page-application)
webpack.config.js

```javascript
module.exports = {
  entry: {
    index: "./src/index.ts",
    webworker: "./src/webworker.ts"
  },
  ...
    output: {
      filename: "[name].js",
      path: path.resolve(__dirname, "dist")
    },
```


:

```
$ ~/node_modules/webpack-cli/bin/cli.js 
Hash: def769ed43f728038706
Version: webpack 4.42.0
Time: 808ms
Built at: 2020/03/16 18:02:28
       Asset     Size  Chunks             Chunk Names
    index.js  4.1 KiB       0  [emitted]  index
webworker.js  4.4 KiB       1  [emitted]  webworker
Entrypoint index = index.js
Entrypoint webworker = webworker.js
[0] ./src/common.ts 53 bytes {0} {1} [built]
[1] ./src/index.ts 82 bytes {0} [built]
[2] ./src/webworker.ts 265 bytes {1} [built]
```


I'm getting two JS outputs from three ts, each containing what I've defined in common.ts.
If you're building a project from scratch, this looks like a good idea.
In the project created with create-react-app, the entry is an array, so we need to do something about that.
- > What happens when you pass an array to entry? Passing an array of file paths to the entry property creates what is known as a "multi-main entry". This is useful when you would like to inject multiple dependent files together and graph their dependencies into one "chunk".
    - [Entry Points | webpack](https://webpack.js.org/concepts/entry-points/)

webpack.config.js

```javascript
    entry: [
      isEnvDevelopment &&
        require.resolve("react-dev-utils/webpackHotDevClient"),
      // Finally, this is your app's code:
      paths.appIndexJs
    ].filter(Boolean),
    output: {
      ...
      filename: isEnvProduction
        ? "static/js/[name].[contenthash:8].js"
        : isEnvDevelopment && "static/js/bundle.js", 
```


It's a mess of conditional branches packed into a configuration file, but in a production environment, the file names are hashed to prevent them from being cached.
I need a way to get the name of this file.

---2020-03-09
I'm using create-react-app to create templates, so webpack is now a black box.
EJECT first so that the settings can be rewritten.
Let's try it on a new project.
`$ npx create-react-app --typescript learn-webworker`
`$ cd learn-webworker/`
`$ npm run eject`
:

```
> learn-webworker@0.1.0 eject /Users/nishio/learn-webworker
> react-scripts eject

NOTE: Create React App 2+ supports TypeScript, Sass, CSS Modules and more without ejecting: https://reactjs.org/blog/2018/10/01/create-react-app-v2.html

? Are you sure you want to eject? This action is permanent. Yes

Ejecting...

Copying files into /Users/nishio/learn-webworker
  Adding /config/env.js to the project
  ...
  Adding /config/webpack.config.js to the project
  ...

Updating the dependencies
  Removing react-scripts from dependencies
  ...
  Adding webpack to dependencies
  ...

Updating the scripts
  Replacing "react-scripts start" with "node scripts/start.js"
  Replacing "react-scripts build" with "node scripts/build.js"
  Replacing "react-scripts test" with "node scripts/test.js"

Configuring package.json
  Adding Jest configuration
  Adding Babel preset

...
Ejected successfully!

Staged ejected files for commit.

Please consider sharing why you ejected in this survey:
  http://goo.gl/forms/Bi6CZjk1EqsdelXk1
```


`$ git status`
:

```
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        new file:   config/env.js
        ...
        new file:   config/webpack.config.js
        ...

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   package-lock.json
        modified:   package.json
        modified:   src/react-app-env.d.ts
```


`$ git add -u`
`$ git commit -m "eject"`
`$ npm install worker-loader --save-dev`

[https://github.com/nishio/learn-webworker/blob/04fe485/config/webpack.config.js#L362-L392](https://github.com/nishio/learn-webworker/blob/04fe485/config/webpack.config.js#L362-L392)
- This is going to need to be rewritten.
- [ecmascript 6 - How to use webpack babel-loader and es6 with worker-loader? - Stack Overflow](https://stackoverflow.com/questions/40323032/how-to-use-webpack-babel-loader-and-es6-with-worker-loader?fbclid=IwAR2tzXNRmbKmUYVkhGbMW0BqTtVi1IJQOoUxDRyCUez9fdsL6QNPq3Kkb5c)
:

```
{
    test: /\.worker\.js$/,
    loader: "worker!babel?presets[]=es2015"
}
```

- → Cannot find module: 'worker!babel?presets[]=es2015'. Make sure this package is installed.

[https://github.com/nishio/learn-webworker/blob/4d426fe/config/webpack.config.js#L363](https://github.com/nishio/learn-webworker/blob/4d426fe/config/webpack.config.js#L363)
→ Cannot find module: 'worker-loader!babel-loader'. Make sure this package is installed.

Hmmm, I wonder if it's a problem with the way webpack rules are written.
It's possible that the information you referenced is out of date and needs to be written differently in the current webpack.

[babel/babel-loader: 📦 Babel loader for webpack](https://github.com/babel/babel-loader)
[webpack-contrib/worker-loader: A webpack loader that registers a script as a Web Worker](https://github.com/webpack-contrib/worker-loader)
- [How to use with babel-loader ? · Issue #35 · webpack-contrib/worker-loader](https://github.com/webpack-contrib/worker-loader/issues/35)

-----Past notes
- [zlepper/typescript-webworker: An example repository for using typescript and webworkers with webpack](https://github.com/zlepper/typescript-webworker)
- `const worker = new Worker(workerPath);`
    - Individual files need to be loaded in the form of
    - Default settings combine them into a single file.
- `import * as workerPath from "file-loader?name=[name].js!./test.worker";`
    - Tell Webpack to make them into separate files like this
- But this approach is upsetting to [[ESLint]].
    - `import/no-webpack-loader-syntax`
- `// eslint-disable-next-line import/no-webpack-loader-syntax`
    - I tried to ignore it.
- with export
    - `Uncaught SyntaxError: Unexpected token 'export'`
- nonexport
    - `All files must be modules when the '--isolatedModules' flag is provided.  TS1208`
- Is it wrong that it's TS, I'll try JS.
js

```javascript
// eslint-disable-next-line no-restricted-globals
addEventListener("message", message => {
  console.log("Message received from main script");
  console.log("in webworker", message.data);
  postMessage("this is the response " + message.data * 2);
});
```

OK, it worked.

But when I try to import other files, error
- `Uncaught SyntaxError: Cannot use import statement outside a module`


...

- [ES-Lint Rule "import/no-webpack-loader-syntax" please deactivate · Issue #1015 · facebook/create-react-app](https://github.com/facebook/create-react-app/issues/1015)
- [Customize webpack configuration of React App created with Create-react-app](https://medium.com/@ryoldash/customize-webpack-config-of-react-app-created-with-create-react-app-7a78c7849edc)
- [javascript - where is create-react-app webpack config and files? - Stack Overflow](https://stackoverflow.com/questions/48395804/where-is-create-react-app-webpack-config-and-files)

---
This page is auto-translated from [/nishio/WebWorker](https://scrapbox.io/nishio/WebWorker) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
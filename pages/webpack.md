---
title: "webpack"
---

- I was avoiding it because I didn't want to go through the hassle of putting it all together after implementation.
- There is `webpack --watch`.
- tutorial
    - [https://webpack.js.org/guides/getting-started/](https://webpack.js.org/guides/getting-started/)
- `$ npx webpack --watch`


----- miscellaneous notes
After all, I thought, at each point in time, if you don't select and install the appropriate library at that point in time, it will rub you the wrong way.
If I write it down in detail, it won't work again the next time I do it anyway, so I don't write it down.
[https://www.valentinog.com/blog/react-webpack-babel/](https://www.valentinog.com/blog/react-webpack-babel/)

- npm init -y
- npm install webpack webpack-cli --save-dev
- npx webpack --mode=development
    - Well, I'm using JSX and it rubs me the wrong way.
- npm i --save-dev babel-core babel-loader babel-preset-env babel-preset-react
- npm i -S react react-dom
    - -S == --save

- > Error: Cannot find module '@babel/core'
- >  babel-loader@8 requires Babel 7.x (the package '@babel/core'). If you'd like to use Babel 6.x ('babel-core'), you should install 'babel-loader@7'.
`$ npm i --save-dev @babel/core`
- > Error: Plugin/Preset files are not allowed to export objects, only functions. In /Users/nishio/grouping/node_modules/babel-preset-react/lib/index.js
`$ npm i -S @babel/preset-react`


---
This page is auto-translated from [/nishio/webpack](https://scrapbox.io/nishio/webpack) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
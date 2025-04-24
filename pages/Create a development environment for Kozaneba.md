---
title: "Create a development environment for Kozaneba"
---

2023-01-11

[https://github.com/nishio/kozaneba](https://github.com/nishio/kozaneba)
- Git was in.

Open in VSCode
- It was in there.

`$ npm start`
`zsh: command not found: npm`
No npm.
- [Downloading and installing Node.js and npm | npm Docs](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm)
- `$ node -v`
- `zsh: command not found: node`
- I see, there's no Node in it.
    - nvm in
        - [https://github.com/nvm-sh/nvm](https://github.com/nvm-sh/nvm)
        - `$ curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.3/install.sh | bash`
- Put node in nvm
    - `$ nvm install --lts`
- `$ node -v`
- `v18.13.0`
- Node, OK
`$ npm install -g npm`
`% npm -v`
`9.2.0`
npm, OK

`% npm start`
`sh: react-scripts: command not found`
- You created it with [[create-react-app]].

`$ npm install react-scripts@latest`
:

```
npm ERR! code ERESOLVE
npm ERR! ERESOLVE could not resolve
...
npm ERR! Conflicting peer dependency: @types/react@16.14.34
...
npm ERR! Fix the upstream dependency conflict, or retry
npm ERR! this command with --force or --legacy-peer-deps
npm ERR! to accept an incorrect (and potentially broken) dependency resolution.
...
```

(Note: shouldn't this be `npm install`?)

- Find out about [Conflicting peer dependency
- [How do I read npm "conflicting peer dependency" error messages? - Stack Overflow](https://stackoverflow.com/questions/67185714/how-do-i-read-npm-conflicting-peer-dependency-error-messages)
    - >  Check out Yarn.
    - `$ npm i -g yarn`
    - `$ yarn install`
    - `success Saved lockfile.`
    - OK
    - (Note: it worked fine, but npm install didn't work in the first place? I proceeded without checking)

`$ npm start`
![image](https://gyazo.com/1ece088f5d6d285b74482f1ffc83f00f/thumb/1000)
:

```
Compiled successfully!

You can now view movidea in the browser.
  Local:            http://localhost:3000
```

The development environment is now working successfully.

Where's the production environment?
Netlify
- ![image](https://gyazo.com/eb5f650e05499d8fb3e0676f002b4f67/thumb/1000)
    - ![image](https://gyazo.com/bbed211e32805f5ee5058434fda828b5/thumb/1000)
    - There's some kind of warning.

-----
![image](https://gyazo.com/d54afcbefdc0349da03520d938520011/thumb/1000)


-----
`error expect@29.3.1: The engine "node" is incompatible with this module. Expected version "^14.15.0 || ^16.10.0 || >=18.0.0". Got "12.18.0"`

> You can choose the Node.js version we use to build your site ...
- [https://docs.netlify.com/configure-builds/manage-dependencies/](https://docs.netlify.com/configure-builds/manage-dependencies/)
- `$ echo "lts/*" > .nvmrc`

---
This page is auto-translated from [/nishio/Kozanebaの開発環境を作る](https://scrapbox.io/nishio/Kozanebaの開発環境を作る) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
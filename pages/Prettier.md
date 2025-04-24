---
title: "Prettier"
---

Most of the work to make the code look pretty can be automated and should not be done by humans.

Put the extension in [[VSCode]].
- [Prettier - Code formatter - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)

Format all files.
- `$ npx prettier --write .`

Automatic formatting when editing
- Cmd+Shift+P: Configure Language Specific Settings
settings.json

```json
{
  ...
  "editor.formatOnPaste": true,
  "editor.formatOnSave": true,
  "editor.formatOnType": true,
	...   
  "[typescript]": {
	...
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  },
	...
```


Well, sometimes I don't like it a bit, but I have to follow it honestly because it is barren to work hard on the configuration file to get it through.



--- old

`$ npm install --save-dev prettier`
`$ ./node_modules/.bin/prettier --write src/*.ts`
[[VSCode]]: [[prettier-vscode]] Cmd+Shift+P: Configure Language Specific Settings
settings.json

```json
{
  "editor.fontSize": 16,
	...
  "editor.formatOnPaste": true,
  "editor.formatOnSave": true,
  "editor.formatOnType": true,
  "editor.tabSize": 2,
  "editor.detectIndentation": true,
	...   
  "[typescript]": {
    "editor.insertSpaces": true,
    "editor.tabSize": 2,
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  },
	...
```


- Cmd+Shift+P: Prettier create config file
- Prettier config
json

```json
{
  "tabWidth": 2,
  "useTabs": false,
  "overrides": [
    {
      "files": ["*.ts", "*.tsx"],
      "options": {
        "trailingComma": "all"
      }
    }
  ]
}
```


---
This page is auto-translated from [/nishio/Prettier](https://scrapbox.io/nishio/Prettier) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
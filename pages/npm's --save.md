---
title: "npm's --save"
---

No harm in adding it, but it is a meaningless option as of 2021, since it has been the default behavior since npm@5 in 2017.

> `npm install` saves any specified packages into `dependencies` by default.
>  Additionally, you can control where and how they get saved with some
>  additional flags:
>  ...
>  * `--no-save`: Prevents saving to `dependencies`.
[https://docs.npmjs.com/cli/v6/commands/npm-install](https://docs.npmjs.com/cli/v6/commands/npm-install)

> Breaking Changes
>  npm will --save by default now. Additionally, package-lock.json will be automatically created unless an npm-shrinkwrap.json exists.
[https://blog.npmjs.org/post/161081169345/v500](https://blog.npmjs.org/post/161081169345/v500)


---
This page is auto-translated from [/nishio/npmの--save](https://scrapbox.io/nishio/npmの--save) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
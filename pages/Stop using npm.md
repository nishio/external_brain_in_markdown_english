---
title: "Stop using npm"
---

2025-09-25
- If I stop using npm altogether, I can't use npm dev or npm test, which is inconvenient.
    - [[Discontinue using only npm install]]


2025-09-19
<img src='https://scrapbox.io/api/pages/nishio-en/GPT5/icon' alt='GPT5.icon' height="19.5"/>
If the objective is to "make it unworkable" for a while, the following order is recommended.
In order of recommendation (macOS/Linux)

1. put "dummy npm" at the beginning of PATH (safe and reversible)
:

```
mkdir -p ~/.bin
printf '#! /usr/bin/env bash\necho "npm is temporarily disabled"; exit 127\n' > ~/.bin/npm
chmod +x ~/.bin/npm

Add PATH head to shell configuration (bash example)
echo 'export PATH="$HOME/.bin:$PATH"' >> ~/.bashrc

zsh would be
echo 'export PATH="$HOME/.bin:$PATH"' >> ~/.zshrc
exec $SHELL -l
which npm # → OK if ~/.bin/npm appears
```

The existing npm is not touched, and this dummy is always picked up first, so it will not break.
To remove, simply delete ~/.bin/npm or revert the PATH line.


---
This page is auto-translated from [/nishio/npmを使用停止](https://scrapbox.io/nishio/npmを使用停止) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
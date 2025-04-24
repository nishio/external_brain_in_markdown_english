---
title: "rebase all history"
---

The correct answer is.
- `$ git rebase -i --root`



<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I want to `rebase -i` all history. How?
<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>
- `$ git rev-list --max-parents=0 HEAD`
- `$ git rebase -i <SHA>`

This is "almost all" but does not include the very first root commit
- If you commit a,b,c, the above method will output b,c to the todo list.
- `$ git rebase -i --root`
    - This would be a, b, c.

---
This page is auto-translated from [/nishio/全履歴をrebase](https://scrapbox.io/nishio/全履歴をrebase) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
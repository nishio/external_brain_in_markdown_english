---
title: "I don't want to put in ssh passphrase over and over again."
---

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>How can I avoid to enter ssh-key passphrase repeatedly in console or Visual Studio Code?
<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>
- `$ eval "$(ssh-agent -s)"`
- `$ ssh-add ~/.ssh/id_rsa`

[[Ask GPT4 about technology]].

---
This page is auto-translated from [/nishio/何度もssh passphraseを入れたくない](https://scrapbox.io/nishio/何度もssh passphraseを入れたくない) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
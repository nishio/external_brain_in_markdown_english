---
title: "PopupMenu asking Keicho for a selection"
---

- [[Extension to use Keicho with Scrapbox]]
PopupMenu asking [/takker/selection to Keicho](https://scrapbox.io/takker/selection to Keicho).
- Tried the

I'll copy and paste the version as of 2021-07-29 and run it.
js

```javascript
import {insertText} from '../scrapbox-insert-text-2/script.js';
```

`https://scrapbox.io/api/code/nishio/scrapbox-insert-text-2/script.js net::ERR_ABORTED 404 (Not Found)`
That's right, fix to absolute paths.

`Uncaught (in promise) ReferenceError: getTalkId is not defined`
I missed that there are two scripts.

`Uncaught (in promise) SyntaxError: Unexpected token ')'`
Merge and extract the code block of the same name in the page of [/takker/scrapbox](https://scrapbox.io/takker/scrapbox).
Corrected by copying and pasting from

`Uncaught (in promise) ReferenceError: askKeicho is not defined`
Put the following UserScript in [[TamperMonkey]].
- [/takker/askKeicho](https://scrapbox.io/takker/askKeicho)

test
keicho.json

```json
{"talk": "Cl72730A3VXGskCtZ6gL"}
```

<img src='https://scrapbox.io/api/pages/nishio/nisbot/icon' alt='/nishio/nisbot.icon' height="19.5"/>What kind of "test" is this "test"?
Whoa, now I can talk to Keicho on Scrapbox!
<img src='https://scrapbox.io/api/pages/nishio/nisbot/icon' alt='/nishio/nisbot.icon' height="19.5"/>What kind of "Keicho" is this "Keicho"?

As already written in [/takker/UserScript to chat with Keicho](https://scrapbox.io/takker/UserScript to chat with Keicho), "I want to send answers without making selections / with one button or one keystroke."
- I don't have to make a selection to access the entire page content.
- How about creating something like `[ask_keicho.icon]`, and using a hotkey to enter the non-empty line before the icon, and inserting the answer before the icon?
1

```
Test (cursor)[ask_keicho.icon]
```

2

```
test
[nisbot.icon]What kind of "test" is this "test"?
(cursor)[ask_keicho.icon]
```

2

```
test
[nisbot.icon]What kind of "test" is this "test"?
Next sentence (cursor)[ask_keicho.icon]
```


- Would you rather this be "the line with the cursor"?
    - Image of hotkey becoming "ask me a question line break".
- Right now Keicho has a chat-like UI that looks human and behaves in a tightly coupled "only put a quote when asking a question in a sentence other than the one immediately preceding it", but you can always include the input text in the response.
    - Then the UserScript side can look at it and decide where to insert it...?
        - I'm still trying to figure out how the asynchronous text in Scrapbox works.
    - Ah, you're using a textarea inserted at the cursor position, then I can only write at the user's cursor position.
    - This is going to be difficult because of Scrapbox's philosophy of not providing an API for programs to write to arbitrary locations, so the user will have to move it themselves.

- line containing the cursor
    - Wow, Textarea is floating with position: absolute?
    - XPath
        - `$x("//span[@class='text' and contains(.,'[ask_keicho.icon]')]").slice(-1)[0].innerText`
        - `"\t\n Why don't you create something like [ask_keicho.icon] separately from [nisbot.icon], use the hotkey to take the non-empty line before that icon as input, and insert the answer before the icon."`
    - [https://developer.mozilla.org/en-US/docs/Web/API/Document/evaluate](https://developer.mozilla.org/en-US/docs/Web/API/Document/evaluate)
    - `document.evaluate("//span[@class='text' and contains(.,'[ask_keicho.icon]')]", document).iterateNext().innerText`
It's an icon, so can't you get it with this? → False.
- `document.querySelector("span.text img[alt='ask_keicho']").parentElement.parentElement.parentElement.parentElement.innerText`
- Incorrect: When the cursor is in front of the icon, the line is in edit mode, so it is text.
- Activate by pressing CTRL+Enter
    - ![image](https://gyazo.com/ef790c7995282a347141378543f0201d/thumb/1000)
    - Oops...
    - Keicho's specification that interprets keywords enclosed in square brackets as explicit keywords.
    - So let's just call it `(keicho)` then.

It's done.
    - [[Ctrl+Enter in Scrapbox to have Keicho ask a question.]]


---
This page is auto-translated from [/nishio/選択範囲をKeichoに尋ねるPopupMenu](https://scrapbox.io/nishio/選択範囲をKeichoに尋ねるPopupMenu) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
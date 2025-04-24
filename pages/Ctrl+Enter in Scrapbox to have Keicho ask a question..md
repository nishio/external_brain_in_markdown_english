---
title: "Ctrl+Enter in Scrapbox to have Keicho ask a question."
---

![image](https://gyazo.com/1858e84d0c918645c4c089ec8e92f3ee/thumb/1000)
Ctrl+Enter in Scrapbox to have Keicho ask a question.
[https://keicho.netlify.app/#talk=lSI8KHGqEfzXAACvih5f](https://keicho.netlify.app/#talk=lSI8KHGqEfzXAACvih5f)
<img src='https://scrapbox.io/api/pages/nishio/nisbot/icon' alt='/nishio/nisbot.icon' height="19.5"/>What kind of "Scrapbox" is this "Scrapbox"?
Wiki instead of chat
<img src='https://scrapbox.io/api/pages/nishio/nisbot/icon' alt='/nishio/nisbot.icon' height="19.5"/>What kind of "Wiki" is this "Wiki"?
...(keicho)

derived from [/takker/popupMenu asking Keicho for a selection](https://scrapbox.io/takker/popupMenu asking Keicho for a selection).
    - [[PopupMenu asking Keicho for a selection]]

script.js

```javascript
import { insertText } from "/api/code/takker/scrapbox-insert-text-2/script.js";
document.body.onkeypress = (e) => {
  if (e.key === "Enter" && e.ctrlKey) {
    ask_keicho();
  }
};

const REGEXP_URL = /https:\/\/keicho\.netlify\.app\/#talk=(\w+)/;
const getTalkId = () => {
  let talkId = null;
  scrapbox.Page.lines.forEach((line) => {
    const matches = line.text.match(REGEXP_URL);
    if (matches !== null) {
      matches.forEach((m) => {
        talkId = m;
      });
    }
  });
  return talkId;
};

const ask_keicho = async (text = null) => {
  // Get id
  const id = await getTalkId();
  if (text === null) {
    const XPATH = "//span[@class='text' and contains(.,'(keicho)')]";
    const current_line = document.evaluate(XPATH, document).iterateNext();
    text = current_line.innerText.replace("(keicho)", "");
  }
  console.log(text);
  let { id: _id, text: answer } = await askKeicho(text, { id });
  // Create a URL when the id is updated
  const code = id !== _id ? `https://keicho.netlify.app/#talk=${_id}\n` : "";
  answer = answer.replace(/\n+/g, "\n").replaceAll(">\n", "\n");
  const ICON = "[/nishio/nisbot.icon]";
  await insertText(`\n${code}${ICON}${answer}\n`);
};

scrapbox.PopupMenu.addButton({
  title: "🤖",
  onClick: (text) => {
    ask_keicho(text);

    // Make a bot entry.
    return `${text}\n`;
  },
});
```



---
ver.1
![image](https://gyazo.com/dd0fb433a12ee640218814c6b2307b2c/thumb/1000)
I'm Ctrl+Enter at the exact moment the input text is flowing on the console.

The reason for the last quote that is not on the screen is that the current system does not quote from the Scrapbox page, but from what has been entered in the past, so Keicho will remember what has been test-entered so far, even if Scrapbox erases it.

---
This page is auto-translated from [/nishio/ScrapboxでCtrl+EnterしてKeichoに質問させる](https://scrapbox.io/nishio/ScrapboxでCtrl+EnterしてKeichoに質問させる) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
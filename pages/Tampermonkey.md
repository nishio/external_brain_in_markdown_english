---
title: "Tampermonkey"
---

Chrome extension that allows users to write user scripts for any site to extend
[https://chrome.google.com/webstore/detail/tampermonkey/dhdgffkkebhmkfjojejmpbldmpobfkfo?hl=en](https://chrome.google.com/webstore/detail/tampermonkey/dhdgffkkebhmkfjojejmpbldmpobfkfo?hl=en)

Tried and Tested
- I thought I'd add a button to call up the code fragment I made earlier.
    - [[Organize Twitter in Scrapbox]]
- Trial and error at the console for DOM manipulation
- Paste and format into VSCode
- When I pasted it into Tampermonkey's configuration screen, it warned me about variables without let or const, so I fixed it.
- I know it's a pain in the ass to go back and forth between screens, but the solution couldn't be easier.

js

```javascript
const togetter_to_scrapbox = () => {
  const tweets = document.querySelectorAll(
    '.choices_box li[data-type="tweet"]'
  );
  const get_name = (tweet) =>
    tweet.querySelector(".user_link .status_name").innerText.substring(1);
  const remove_mention = (text) => text.replace(/@\w+\s+/g, "");
  const concat_line = (text) => text.replace(/\n+/g, " ");
  const quote_all_line = (text) => text.replace(/\n+/g, "\n>");
  const text = Array.from(tweets)
    .map((x) => {
      const name = get_name(x);
      const url = x.querySelector(".link[target='_blank']").href;
      let body = x.querySelector(".tweet").innerText;
      body = remove_mention(body);
      //body = concat_line(body)
      body = quote_all_line(body);
      return `>[${name} ${url}]: ${body}`;
    })
    .join("\n\n");
  document.querySelector(".title_input").value = text;
  navigator.clipboard.writeText(text);
};
const div = document.getElementById("settings");
const button = document.createElement("button");
button.onclick = togetter_to_scrapbox;
button.innerText = "Scrapbox";
div.insertBefore(button, div.children[0]);
```


---
This page is auto-translated from [/nishio/Tampermonkey](https://scrapbox.io/nishio/Tampermonkey) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
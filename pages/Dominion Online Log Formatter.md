---
title: "Dominion Online Log Formatter"
---

js

```javascript
// ==UserScript==
// @name         Dominion Online Log Formatter
// @namespace    http://nhiro.org/
// @version      0.1
// @description  Dominion Online Log Formatter
// @author       You
// @match        https://dominion.games/
// @icon         https://www.google.com/s2/favicons?sz=64&domain=dominion.games
// @grant        none
// ==/UserScript==

(function () {
  "use strict";

  const copy = () => {
    const log_lines = document
      .querySelector(".game-log")
      .querySelectorAll("log-line");
    const pad_stat = new Set();
    log_lines.forEach((line) => {
      const first = line.querySelector("div");
      if (!first) {
        // empty line
        return;
      }
      const pad = line.querySelector("div").style["padding-left"];
      pad_stat.add(Number.parseFloat(pad));
    });
    const pad_array = Array.from(pad_stat);

    const out_lines = [];
    log_lines.forEach((line) => {
      const first = line.querySelector("div");
      if (!first) {
        // empty line
        out_lines.push("");
        return;
      }
      const pad = line.querySelector("div").style["padding-left"];
      const pad_index = pad_array.indexOf(Number.parseFloat(pad));
      const out_text = line.innerText.replace("\n", "");
      if (out_text.startsWith("turn")) {
        out_lines.push("");
        out_lines.push(`[* ${out_text}]`);
        return;
      }
      out_lines.push(" ".repeat(pad_index) + out_text);
    });
    const out_str = out_lines.join("\n").replace(/\n\n+/g, "\n\n");
    console.log(out_str);
    navigator.clipboard.writeText(out_str);
  };

  const button_label = "copy game log";
  setInterval(() => {
    const parent = document.querySelector(".chat-display");
    if (!parent) {
      console.log("parent not found");
      return;
    }
    if (parent.innerText.includes(button_label)) {
      console.log("button already exists");
      return;
    }
    const b = document.createElement("button");
    b.innerText = button_label;
    b.addEventListener("click", copy);
    parent.appendChild(b);
  }, 1000);
})();
```



---
This page is auto-translated from [/nishio/Dominion Online Log Formatter](https://scrapbox.io/nishio/Dominion Online Log Formatter) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
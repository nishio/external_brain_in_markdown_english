---
title: "Extract titles and URLs from links on PowerPoint"
---

The situation is Mac.
Links are created in the form of hyperlinks on PowerPoint.
I want to transcribe that information outside of PowerPoint, but it is tedious to select each one and copy and paste the URL information.
How do you think it would be easier? You asked, and after a little thought, here's what I came up with.

- Copy the list on PowerPoint
- Paste into a Mac text editor
    - Rich text editor so you can paste in hyperlinks as they are.
- Text editors can save in HTML format, so do
- The saved HTML looks like this
html

```html
<p class="p1"><span class="s1"><a href="https://www.j-focus.or.jp/archives/001/201307/5715be09b5800.pdf">[Nanotech & Materials] Development of High Performance Tires with Reduced Environmental Impact</a ></span></p>
<p class="p1"><span class="s1"><a href="https://www.j-focus.or.jp/archives/001/201307/5715be09ba60c.pdf">[Nanotech & Materials] Catalyst Simulation for Exhaust Gas Purification</a a></span></p>
<p class="p1"><span class="s1"><a href="https://www.j-focus.or.jp/archives/001/201307/5715be09bc047.pdf">[Nanotech & Materials] Development of Lead-free Fishing Pole</a></p span></p>
```

- If you can use HTML, that's fine, and if you want to convert more, use regular expressions, etc. to replace.

remarks
- I thought you could get it in HTML format directly from PowerPoint. I thought so, but I couldn't find it.
- I remember doing a hack a long time ago that took advantage of Excel's ability to read and write HTML.

---
This page is auto-translated from [/nishio/PowerPoint上のリンク集からタイトルとURLを抜き出す](https://scrapbox.io/nishio/PowerPoint上のリンク集からタイトルとURLを抜き出す) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
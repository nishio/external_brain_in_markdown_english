---
title: "Japanese URL problem"
---

When a URL from iPhone is encoded in Japanese, both Safari and Chrome decode and display it.
When the URL is posted on Twitter, etc., the Japanese part of the URL is judged not to be a URL, so the link does not connect.

- Japanese part is judged not to be a URL: Twitter
- Japanese parts are also considered URLs: Facebook, Scrapbox

- URLs are displayed in Japanese and actually in Japanese: Safari on iPhone, Chrome on iPhone
- Looks Japanese but is encoded when copied: Chrome on MacBook

On the service side, when a string starting with http etc. is pasted using onPaste, it may be possible to determine that the entire pasted string is a URL, or something like that.
What can users do with services that are not supported...

- Proposal to tinyurl

- Proposal "should be encoded when it goes into the clipboard."
    - 'Should be encoded when it goes into the clipboard' is a possible solution, but it's a long shot because Apple needs to improve Safari's code.
    - The next best solution would be for services that use Japanese URLs to provide a way to copy encoded URLs. In fact, Scrapbox has a menu item called "Copy link. I wondered if this was the function. But it is not, and the Japanese decoded version is put into the clipboard, which is not useful at all.

- If "Share→Copy", the encoded version goes into the clipboard.
    - Here it is!

relevance
- [percent encoding - Wikipedia [https://ja.wikipedia.org/wiki/%E3%83%91%E3%83%BC%E3%82%BB%E3%83%B3%E3%83%88%E3%82%A8%E3%83%B3%E3%82%B3%E3%](https://ja.wikipedia.org/wiki/%E3%83%91%E3%83%BC%E3%82%BB%E3%83%B3%E3%83%88%E3%82%A8%E3%83%B3%E3%82%B3%E3%) 83%BC%E3%83%87%E3%82%A3%E3%83%B3%E3%82%B0]

---
This page is auto-translated from [/nishio/日本語URL問題](https://scrapbox.io/nishio/日本語URL問題) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
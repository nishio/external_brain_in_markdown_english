---
title: "Problem with extracted keywords not lining up in chronological order"
---

[[pKeicho-done]]
There is a lack of content stored by the chat server and the problem of extracted keywords not being in chronological order needs to be resolved. When organizing, it is inconvenient to not have the extracted keywords nearby.

I've been thinking about this, and I've saved the chat logs, and I've saved the question/keyword pairs, but the problem is that it doesn't record "at what point in the log was that question/keyword pair made", so I thought I could just give the current line in the log.
- If we simply give this to the user, it will break the in check for "do not repeat used questions", and rewriting it in a loop is not a good idea, so let's have it separately.



I want to make [[View to see what's in env in real time.]] first, to make it easier to observe.

It doesn't have to be real time.
There was originally talk of downloading data, so we could create a script for that.
If you take the data and save it in a file, it's a download, and if you display it on the screen for easy viewing, you can see the contents of the view.

Data format is changed and needs to be tested for corruption
I have a client that reads directly from Firebase and displays logs.

---
This page is auto-translated from [/nishio/抽出されたキーワードが時系列に並ばない問題](https://scrapbox.io/nishio/抽出されたキーワードが時系列に並ばない問題) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
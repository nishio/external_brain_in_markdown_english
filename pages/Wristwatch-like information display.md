---
title: "Wristwatch-like information display"
---

![image](https://gyazo.com/5b06e2cb82759898023164f06473075d/thumb/1000)

- Placed [[Canvas]] as a child of [[TrackedRemote]] and [[Text]] as its child
- Metaphorically, [[wristwatch]].
    - When you try to look at a wristwatch, it naturally "twists 90 degrees and points to the left," which is a different behavior from how it's used as a pointer.
    - It can be made to appear only when you make such a pose.
    - If you pull the trigger in that state, it becomes some special command, or

Parameter Setting
- ![image](https://gyazo.com/8070215d197db6213f49b192bdb41071/thumb/1000)
- ![image](https://gyazo.com/74fe45867fa42272f0a2a19e97f01c60/thumb/1000)

- Unfortunately, when you do a watch look [[gesture]], the TrackedRemote goes a long way from your actual arm position
- Rather than making it a child of TrackedRemote, it might be better to trigger the wristwatch gesture and bring up a separate information screen.

---
This page is auto-translated from [/nishio/腕時計的に情報表示](https://scrapbox.io/nishio/腕時計的に情報表示) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
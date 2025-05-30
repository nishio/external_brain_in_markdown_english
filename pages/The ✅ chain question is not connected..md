---
title: "The ✅ chain question is not connected."
---

I've implemented a chain question that returns a score of 1000 appropriately, so if there is a proposed response that exceeds a score of 1000, that will take precedence.
I was going to take care of it if it was happening more often, but it happened easily.

How do we resolve this?
- Proposal 1: Look at the scores of other responses and decide to surpass them.
    - You can definitely be the highest scoring question, but it's weird to have a design where the code that determines the score of an individual question refers to the scores of other questions.
- Proposal 2: Make it 3000 instead of 1000
    - Looks like we're going to solve the problem this time, but more mysterious magic numbers...
- →I'll go with proposal 2 this time and see how it goes.

:

```
0> What would you like to see happen regarding that "chat"?
1> With chat by itself, it would be good if we can notice something in the course of conversation like this. However, with this feature, even if you don't get any insights in the chat, you can simply talk about what you think would be good to write in the manuscript in the chat, and then reorganize it with stickies, so you can simply talk about various things on the chat side. It would be nice to have all the parts for the manuscript, but there is no support function for that, and since it is not clear what kind of manuscript is to be written, it is not clear what is needed either, so it is a chicken-and-egg relationship.
DEBUG:server.keicho.action:('What kind of 'sticky' is that 'sticky'?' , 'sticky', 813.4)
DEBUG:server.keicho.action:('Where is that "chat"?' , 'chat', 1154.2337936568226)
DEBUG:server.keicho.action:('Where does that "chat" come from?' , 'chat', 1151.3039452242817)
DEBUG:server.keicho.action:('How do you know its 'chat'?' , 'chat', 1153.5498217510662)
DEBUG:server.keicho.action:('What needs to happen to 'chat' for that to happen?' , 'chat', 1000.0)
```


:

```
0> What would you like to see happen regarding those "stickies"?
1> It would be good if users can understand the process of building up a story slowly by moving stickies
DEBUG:server.keicho.action:('What 'configure' is this 'configure'?' , 'configure', 694.4)
DEBUG:server.keicho.action:('What kind of 'user' is that 'user'?' , 'user', 825.4)
DEBUG:server.keicho.action:('Where is that "sticky"?' , 'sticky', 1307.4112194939348)
DEBUG:server.keicho.action:('What needs to happen to 'stickies' for that to happen?' , 'sticky', 1000.0)
```


- [[✅Use logging for debugging output]]

---
This page is auto-translated from [/nishio/✅チェーン質問が繋がらない](https://scrapbox.io/nishio/✅チェーン質問が繋がらない) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
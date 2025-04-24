---
title: "Specification Resolution"
---

from  [[Diary 2024-12-12]]
Specification Resolution

Instructions for having AI create a certain tool
- A tool to put all the source code of a project into the clipboard at once.
- Is there a Python library that reads gitignore?
- Use it and implement it.
- Use argparser to get target_dir, target_exts, and search up the .gitignore until you find it.

The reason I say "Mac" at the outset is that different operating systems handle the clipboard differently.
- I expected Mac would subprocess pbcopy, in fact AI did.
Using gitignore is like seeing that AI didn't do it and saying, "I would do it, but what?" I would do it.

Chatting with AI, "miscommunication that can be easily seen" can be immediately pointed out and fixed.

Now that the AI code generation is complete, the next step is to test its operation in the use case that humans are expecting.
- The reason why it's the law is because there is doubt about whether the resolution of the "specifications" in the brain is sufficient.
- For example, in this example, I realize before execution that the behavior "Merge all files under the specified directory" is not good enough.
    - I'll read inside node_module and so on.
    - So I'm playing it by gitignore.
- We know this before we run it.
- There's something I don't understand.
    - Humans are not convinced that the specifications in their brains are correct because they often overlook

![image](https://gyazo.com/3b7d4766878fab9dd3c0ba761a3974fb/thumb/1000)


---
This page is auto-translated from [/nishio/仕様の解像度](https://scrapbox.io/nishio/仕様の解像度) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
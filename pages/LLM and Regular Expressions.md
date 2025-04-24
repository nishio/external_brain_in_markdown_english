---
title: "LLM and Regular Expressions"
---

> [@nishio](https://twitter.com/nishio/status/1633284435952144386?s=20): I suspect that for many programmers, exposure to paradigms that are not [[procedural type]] is [[(computer) regular expression]] is the only paradigm that many programmers are exposed to that is not a [[procedural type]]. You describe what kind of pattern you want to match, and leave it to the regular expression engine to decide what exactly to do. The process of incorporating [[LLM]] into a program is similar.
> Just as passing the mysterious string "regular expression" and data to a regular expression engine will return a match object, passing "prompt" and data to an LLM will return a response object, there's not much difference in the current situation.

> [@koizuka](https://twitter.com/koizuka/status/1633289420102307840?s=20): programming languages will come out with large language models, like languages with a standard library of regular expressions ...?
- > [@nishio](https://twitter.com/nishio/status/1633291380629061633?s=20): @koizuka Currently, it's not practical to run it on hand yet, so it's probably going to hit the API, but eventually it's going to pass the flag to the regular expression engine and change the behavior. But eventually we'll be able to pass flags to the regex engine and change the behavior, so we'll be able to do it on hand or in the cloud.
- > [@ajiyoshi](https://twitter.com/ajiyoshi/status/1633290699188899842?s=20): hello world binary size will be 30GB in the future
- > No, well, but it would be normal.
- >  The linker might be able to cut down on code that is not used when LLM was first able to be incorporated into the runtime.
- >  Eventually, they'll say, "Well, it's a hassle, and if it's only 30 GB, why don't we just always bundle it?" > Eventually, it will become "why don't we always include it if it's only 30GB?
    - > [@nishio](https://twitter.com/nishio/status/1633292065353392128?s=20): @ajiyoshi "Please link `libllm.so` when compiling this program. I'm sure there will be a trend of "No, it's a pain in the ass, just use one binary..." sooner or later...
        - > [@ajiyoshi](https://twitter.com/ajiyoshi/status/1633292205778690048?s=20): @nishio I'm pretty sure it will w

> [@ooharak](https://twitter.com/ooharak/status/1633326421128142848?s=20): @nishio Personally, though, I felt the difference with procedural types when I learned about [[SQL]] than when I learned about regular expressions.
- > [@nishio](https://twitter.com/nishio/status/1633326885395656704?s=20): @ooharak You're right, SQL has a stronger "it's a different language" feel because it has a more solid syntax.

---
This page is auto-translated from [/nishio/LLMと正規表現](https://scrapbox.io/nishio/LLMと正規表現) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
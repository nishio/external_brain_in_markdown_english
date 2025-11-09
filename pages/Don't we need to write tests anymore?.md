---
title: "Don't we need to write tests anymore?"
---

> [kenn](https://x.com/kenn/status/1967738892297310301) When I see that gpt-5-codex thinks of the tests needed to confirm that it works, creates the environment on the spot, and runs them, I feel like I don't need to write tests anymore. I feel like I don't need to write any more tests.
>
>  Recently, when I have an implementation that is likely to take a long time, I have them write an md of the execution plan before starting, and when the implementation is finished, I extract the trade-off decision part in a compact format, transcribe it to the design doc, and discard the rest.
>
>  In the same way, I think we can turn off the tests. During the implementation phase, I would have the tests written first as an expectation of a correct implementation in test-first mode, and use them to run the iteration, and also to check that they are not broken in the refactoring phase immediately after the implementation is complete. But when that's done and git commit is done, it's okay to erase them.
>
>  In general, tests written by human beings are too often tempered by the psychology of avoiding trouble, and there are too many tests that are written only for the purpose of self-congratulation for having been written, even though they are of zero effectiveness.
>
>  But AI is tireless and never stops progressing, so an approach of another dimension that would be too tedious for a human to take, like trying to build every time and checking it works, may be possible when you come back to fix a bug or something, and the situation may have changed dramatically. The primitive unit tests that remain at that time may just be a liability.
>
>  It's been such a game changer that I'm starting to dabble in such hypotheticals.

> [S_N_W_E](https://x.com/S_N_W_E/status/1967809926719476052) [[test expiration date]] It's like building it into the development process!

> [kenn](https://x.com/kenn/status/1967838677423522207) That's exactly what it is! I like the term "test expiration date".

- [[software testing]]
- [[test]]

---
This page is auto-translated from [/nishio/もうテスト書く必要ないのでは？](https://scrapbox.io/nishio/もうテスト書く必要ないのでは？) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
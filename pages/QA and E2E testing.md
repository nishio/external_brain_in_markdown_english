---
title: "QA and E2E testing"
---

> [ssig33](https://x.com/ssig33/status/1791998315468673480) I was wrong that even [[DHH]] [[DHH]] can replace [[QA]] by humans with [[E2E Test]], interesting!
[System tests have failed](https://world.hey.com/dhh/system-tests-have-failed-d90af718)
<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>
David Heinemeyer Hanson shares his views on system testing in Rails.

The main points are as follows
- System testing is useful in theory, but slow, fragile, and full of false positives in practice
- Caused by browser complexity, UI timing issues with JavaScript, and difficulty identifying the cause of failure
- No return on the effort put into system testing
- Instead of discarding all system tests, a small number should be left for overall operation checks
- Business logic is sufficient for model and controller testing
- Automation is still insufficient for testing UI logic (JavaScript); manual testing is best
- HEY plans to significantly reduce system testing

In short, they argue that system testing should be kept to a minimum because it does not work as ideal and is not worth the cost. It also recognizes the limitations of automation and stresses the importance of manual testing. It is an interesting look at software testing.
---
This page is auto-translated from [/nishio/QAとE2Eテスト](https://scrapbox.io/nishio/QAとE2Eテスト) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
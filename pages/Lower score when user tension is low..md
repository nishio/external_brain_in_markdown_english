---
title: "Lower score when user tension is low."
---

- > Test
- > What type of test is that?
- > When a user responds with something like "nothing in particular," the score for the keyword used in the previous statement is lowered. Scores that have been high once before were never reduced, but that way, if a strange keyword is high early on, the question will keep revolving around that word all the time.
- > What type of score is that?
- > "How good would it be to ask a question about it?"
- > What kind of degree is that degree?
- > I don't know // // ← triggered here.
- > Is there anything else about the server?

When we trained a model that identifies "nothing in particular" type statements with a miscellaneous amount of features from a miscellaneous collection of data, we got about 70% correct, so we decided to lower the score of keywords used in the chatbot's previous statement when a user makes a "nothing in particular" type statement.

[Google Colab](https://colab.research.google.com/drive/1D7Qc7nNtpZxf0Z0HjDf5QIvdXPaBhjOE)

[[pKeicho-done]]

---
This page is auto-translated from [/nishio/ユーザのテンションが低い時にスコアを下げる](https://scrapbox.io/nishio/ユーザのテンションが低い時にスコアを下げる) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
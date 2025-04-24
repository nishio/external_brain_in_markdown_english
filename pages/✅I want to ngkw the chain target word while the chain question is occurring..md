---
title: "✅I want to ngkw the chain target word while the chain question is occurring."
---

from [[pKeicho]]
I want to ngkw the chain target word during 🤔 chain question generation.
- Not possible at this time.
- This is because the chain question was implemented with state transitions
- Just express it in terms of up or down selection probability.

Fix the test case first
- Right now I'm just observing the change in status.

status quo
- If I ask Q1 questions about a particular keyword K, then I want to ask Q2 and Q3 questions about K."
- This was represented by state transitions.
    - When processing the response to Q1, "If the previous question was Q1, transition to S2."
    - Only Q2 in S2.
    - Q2 uses keywords used in the immediately preceding question
    - It was achieved in a tricky way: a question that apparently takes a single keyword, but does not take a keyword in its implementation.
- This would lead to a fixed conversation flow, even if you ng after that flow has started.
    - Even if the target keyword disappears in NGKW, it's still a "question that doesn't take keywords" so it's relentless.
- I want to replace the score variation
    - Q2 increases the score when the immediately preceding question is Q1
    - Change the question to a keyword taking question.
        - Score increases when keywords match those used in the previous question

done: b4ed166473fee9b4b1ecbc2cb439d7102f5831cb
- I was going to link to GitHub, but the repository was Heroku.

point of concern
- Right now I'm returning a score of 1000, as appropriate.
- When there is a return proposal with a score over 1000, that takes precedence.
        - [[Maximum score reply]]
    - Sometimes it goes over 1000.
    - →The ✅ chain question is not connected.
- When the score reduction by NG is multiplied, the keyword itself is still alive, so it continues with a score of 1000.
    - This is behavior contrary to user expectations.
        - I decided to use NG pressure just before ✅ to reduce the score.
        - This looks good because the score is 0 when 100% NG pressure is applied.

---
This page is auto-translated from [/nishio/✅チェーン質問発生中にチェーン対象の単語をNGKWしたい](https://scrapbox.io/nishio/✅チェーン質問発生中にチェーン対象の単語をNGKWしたい) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
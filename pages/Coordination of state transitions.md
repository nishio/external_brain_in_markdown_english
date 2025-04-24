---
title: "Coordination of state transitions"
---

Originally, the system was designed to "transition to the next state once the conversation has developed to a certain degree.
- The "when it develops to some extent" was judged by "when the number of extracted keywords exceeds a certain level.
    - [[Motion Extraction]] now extracts keywords that were not previously extracted.
- As a result, state transitions began to occur before they were sufficiently developed
- I had foreseen this, but I didn't care and proceeded.
        - [[Motion Extraction Work Memo]]
        - > The case where keywords containing verbs are now extracted, if they are simply connected, the number of keywords extracted will naturally increase, and then the places that require a certain number of keywords to be extracted will all be triggered earlier than now.
        - >  [[Keyword appearance speed]]
        - >  I decided not to worry about it and integrate it.
- I observed the speed at which keywords appeared, and since many users were running out of keywords in the first place, I figured I could increase them without worrying about it.
    - However, a negative effect was observed: "Questions that assume that they have developed before they are fully developed are asked."
        - [[Conversation log 2021-02-05]]
    - [[Replay internal state changes]] so that the internal state at the time of state transition can be observed in the log.
    - Phase 3
        - Keywords with scores above 100, average 4.93, median 5
        - Keywords with scores over 200, average 1.06, median 1
    - Phase 2
        - Keywords with scores above 100, average 1.48, median 1
        - Keywords with scores over 200, average 0.69, median 1
        - Maximum score keywords, average 167
- Therefore, we changed the index to use the number of high-scoring keywords and the keyword scores themselves, rather than the total number of keywords.

[[pKeicho-done-2021-02-05]]

---
This page is auto-translated from [/nishio/状態遷移の調整](https://scrapbox.io/nishio/状態遷移の調整) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
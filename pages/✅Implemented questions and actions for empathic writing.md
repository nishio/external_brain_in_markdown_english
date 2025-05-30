---
title: "✅Implemented questions and actions for empathic writing"
---

from  [[Create ✅empathy writing mode]]
✅Implemented questions and actions for empathic writing
- No transition until you do the "next question" to the next question?
- No, we should transition when we run out of good keywords.
- Just the two basic questions? Do you want to include a metaphor question?
- Do you want to put them together in an empathy writing module or in a state transition description?
    - The transitions don't mix, so it's cleaner to separate them.
    - Let's run it once, cover it with tests, and then refactor it.
- Separated because it is hard to write if not separated.
    - I wanted to generate a loop of consecutive state transitions.
    - Writing where the dictionary describes it is messy.
    - Summarized in the empathy_writing module
- Need to enforce state transitions
    - Usually transitions to the next state when the next question is asked.
    - What if I use the "next question" command?
        - Ask the next question and transition to the next state
    - Can we add that as a plugin with the current structure?
    - The command only returns a bool whether it was a command or not, and if you should ask a specific question, you need to transition to a state where you only ask that question.
        - Tricky?
        - If you were to change it, how would you change it?
        - Hmmm, I feel like we'll end up just having a different form of state than state.
        - This is troubling.
    - Decided to increase the number of states.

---
This page is auto-translated from [/nishio/✅エンパシーライティング用の質問とアクションを実装](https://scrapbox.io/nishio/✅エンパシーライティング用の質問とアクションを実装) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
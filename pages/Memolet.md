---
title: "Memolet"
---

Memolet: Reifying the Reuse of User-AI Conversational Memories
[https://www.youtube.com/watch?v=KH9yn4pg2bY](https://www.youtube.com/watch?v=KH9yn4pg2bY)

[PDF](https://www.jeffjianzhao.com/papers/memolet.pdf) from his website

### Summary (Japanese summary)
.

Memolet" is a system for visualizing and manipulating the dialogue history (past interactions) between a user and AI as a reusable unit called a "Memolet" and easily recalling necessary information for use in new conversations and tasks.

- Background and Issues.
- Chat systems using large-scale language models tend to lose track of "past content" as the number of exchanges increases, and users themselves tend to have a hard time finding information they want to reuse from a long history and copying and pasting it.

- Proposed Method (Memolet).
1. Long-Term Memory Repository
    - Embed and visualize all past dialogues on a semantic basis, making it easier for users to find relevant conversations (Memolet).
2. Memory Sandbox
    - An area is provided for grouping and organizing (externalizing thoughts) by arranging the selected Memolets side by side.
- 3.direct reference to Prompt & modification of generated results.
    - Specify references in the prompt, such as "@Memolet name," to make it clear to the AI which past information is to be used. Also, the AI intuitively performs operations such as adding, excluding, and merging on the generated results, and modifies the output.

- evaluation experiment.
- The participants were asked to perform a task with a two-phase structure, leaving one day open, and compared the conditions of using Memolet with those of using regular chat (Baseline).
    - Memolet users rated Memolet significantly higher in task accuracy, efficiency, and ease of use by making it easier to extract, organize, and use information from past dialogue.
    - Control over the generated results was also increased, and operations such as eliminating unnecessary information or highlighting and regenerating specific Memolets were smooth.

### Summary
.
Memolet" proposes a mechanism that allows users to treat past conversational memos like thinking tools, supporting a sequence of search, organization, reference, and re-generation flows. This has been shown to facilitate the reuse of scattered information when interacting with a large-scale language model, and to reduce wasteful prompt engineering, scrolling, and copy-pasting.

private chat [https://chatgpt.com/c/679b3abe-54d8-8011-b234-429991c62396](https://chatgpt.com/c/679b3abe-54d8-8011-b234-429991c62396)

---
This page is auto-translated from [/nishio/Memolet](https://scrapbox.io/nishio/Memolet) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
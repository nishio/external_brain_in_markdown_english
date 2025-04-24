---
title: "AI writes daily research notes: how to select chunks"
---

from  [[AI writes research notes daily]]

AI writes daily research notes: how to select chunks
2023-08-11
There are a number of options for how to select chunks
- A: Random
- B: Recently updated chunks
- C: Chunk of recently created new pages
- D: The older the update date/time, the lower the probability
- E: Vector search on previous note
I think A or D would be appropriate under the condition that it be done automatically once a day.
- In B and C, we see things from the same perspective as humans.
    - The need for "AI to see and develop what humans are seeing now."
    - If that's what you're looking for, don't wait for a once-a-day opportunity to make an explicit request to the AI.
- E is "AI reads and thinks about Scrapbox in its own interest, independent of humans".
    - This is not a bad streak.
    - The problem is that naive implementation is where you read the same thing over and over again.
    - Need an implementation that remembers "what you've read in the past" and leaves it out.
    - On the other hand, "Do I really have to read something once and never again?" I mean, well, that's not true.
        - Well, maybe the last 100 or so.
    - Added on 8/14/2023
        - You could decide based on the amount of notes you had last time.
        - 0 means random
        - If there are a lot of them, it's unlikely that they are derived from a single existing chunk, so using the results of a vector search won't result in "all the same ones".
        - If the previous note has N tokens, there will be zero additional chunks to begin with.
        - I'd love to put one in at random.
    - Added on 2023-08-18
        - > If there are a lot of them, it's unlikely that they are derived from a single existing chunk, so using the results of a vector search won't result in "all the same ones".
        - It never happened.
            - I put a lot of different things in [[🤖2023-08-18 02:22]] but
            - [[🤖2023-08-18 02:27]] showed a commitment to a specific chunk
                - I could abstract the word here and get out of it.
                - [[🤖2023-08-18 02:37]]
- A is the easiest to implement, so I experimented with this implementation.
    - As a result, Hatena Diary became a hit, which worked rather well for me!
    - It's imported because it's worth zero if it's not a search hit.
    - but there are no Scrapbox-like links, so there are no Scrapbox-like suggestions.
    - This has resulted in a situation in which the product is contained but underutilized.
    - I don't want to parse Hatena notation and change it to Scrapbox notation because it's too much trouble.
    - AI will interpret this in natural language and make summary notes, a good "dig back".


---
This page is auto-translated from [/nishio/AIが毎日研究ノートを書く:チャンクの選択方法](https://scrapbox.io/nishio/AIが毎日研究ノートを書く:チャンクの選択方法) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
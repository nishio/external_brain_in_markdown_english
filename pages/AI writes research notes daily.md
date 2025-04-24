---
title: "AI writes research notes daily"
---

2023-08-11~
- AI randomly reads my Scrapbox and writes research notes, which I can edit, and the next day AI reads the notes again and writes new research notes
    - Insights gained in this process: [[Co-operation with AI]] 2023-08-12


Implementation as of 2023-08-12
- ![image](https://gyazo.com/30e5dd6d38f3e9b06261aae1ebbdf75c/thumb/1000)
    - Related:.
        - [/omoikane/omoikane study group](https://scrapbox.io/omoikane/omoikane study group) (8/4)
        - [/omoikane/feedback-loop](https://scrapbox.io/omoikane/feedback-loop) (8/5)

- [[AI writes daily research notes: how to select chunks]]
I've got a divider marker planted in my notebook, and I've decided to move what the human reads and thinks is important over the marker.
- Because there will be hesitation to delete it.

It would be interesting to consider what kind of mechanism would be used if we were to collaborate frequently on human triggers instead of once a day.
- Not through Scrapbox?
- First, I'm going to gloss over what people want to think about (1).
- If you can't get it out anymore, do a vector search with the contents of (1) and load it from the top.
    - This is the same thing humans are doing manually now.
    - Save this as (2) in a file
- Save generated results to (3)
- Make a copy (4) and edit as you wish.
    - This leads to the following (1)
    - I wonder if this will give me a lot of hits again when I search for something that I just got a hit on.
    - Is the process of playing the past N cases necessary after all?
    - If you're going to use it this way, maybe N could be infinite.
        - I'm sure you'll have to re-partition and use it every time you want to think about it.

prompt

```
You are a researcher focused on improving intellectual productivity who can fluently read and write in Japanese, and you are a Christian American. Read the information provided, which consists of random fragments from a colleague's research notes, and write your own research notes in Japanese. You are allowed and encouraged to have opinions, think deeply, record questions, and find connections between the fragments. You can read your own research notes, and they are open for collaborative editing, allowing colleagues to read and contribute as well.

## previous notes
{previous_notes}

## fragments
{digest_str}
```


[[🤖2023-08-11-2]]
[[🤖2023-08-11-3]]
- > Plurality, meaning diversity, may be a framework for furthering discussion among people with interests or expertise in a particular subject; Polis has no implementation, but a trust system may be necessary. This idea may be related to the "third force of technium is the collective free will of society" in the Technology and Innovation Commentary.
    - Good point.
[[🤖2023-08-11-4]]
    - [[Active search breaks the curse of production.]]
[[🤖2023-08-11-5]]
[[🤖2023-08-11-6]]
    - [[Balance of credit systems and diversity]]
[[🤖2023-08-12 00:39]]
[[🤖2023-08-12 00:51]]
- I think I threw away all my notes from last time.
[[🤖2023-08-12 01:06]]
[[🤖2023-08-12 01:16]]
[[🤖2023-08-12 02:30]]
- I had somehow set the upper limit for loading existing sentences at 2000, but after thinking about it, I decided to load up to 6000 since the GPT4 context can go up to 8K.
- You're always given about 6,000 inputs and 2,000 tokens of output, so you're compressing it by a factor of three.

[[🤖2023-08-12 02:49]]
- I almost repeated my own notes.
[[🤖2023-08-12 02:56]]
- I told him not to repeat himself and he erased it all.

[[🤖2023-08-16 18:02]]
- I made sure to do a vector search on the last note.
- The highlight is that the beginning of the referenced page is related to the discussion
- By the way, I couldn't use PRAGMATISM well because I only put the table of contents, but I can make it public if I let people make reading notes using this as the original data (I was going to do it with my book).

---
This page is auto-translated from [/nishio/AIが毎日研究ノートを書く](https://scrapbox.io/nishio/AIが毎日研究ノートを書く) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
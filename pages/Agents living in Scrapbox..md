---
title: "Agents living in Scrapbox."
---

from  [[Diary 2023-07-29]]
Agents living in Scrapbox.
- [[scbot]]


from [/omoikane/BabyAGI code reading](https://scrapbox.io/omoikane/BabyAGI code reading) #BabyAGI
- Based on this, think about "[Agents living in Scrapbox.
    - If you're an agent living in Scrapbox, it's natural to receive JSON data from Scrapbox.
    - If there's nothing explicit about the mission, it's natural to read them in order of newest first.
        - Reading each page will be the initial task.
    - Read pages updated in the last 24 hours if they are activated once a day.
        - [[What is "reading?"]]
        - Summary?
        - Pick up keywords?
        - Ask questions of humans?
        - Write your thoughts?
        - People don't react to everything they read either.
    - Give prompts for project objectives, etc.?
    - I should make a script to run this locally before I automate it...

- [[Blog text generation instead of translation]]
- How about an agent who reads this Scrapbox and blogs about his/her impressions, rather than translating or blog writing?
    - Sometimes he throws out questions.
    - If your impressions are good enough to write in Japanese, you can have them written in English.
        - [[Impressions by AI: neither 0 nor 100]]

"What is 'reading'?" Not "What is 'reading' for?" It is.
- For example, "keep a rough idea of where things are so that you can remember them when you need them" is, in today's terms, creating a vector index.
    - [[leveraged reading]]
    - The purpose of this is to reduce the cost of reading back by using a compressed representation
    - reading
            - [[Times when writing knowledge is not enough.]]

- [[(4.1) What is "reading"?]]
- > Entertainment, finding information, assembling understanding
- > Old format content with a string of letters
- > The content of the book is not the only material to assemble.
- > Gradation of "find" and "assemble

- What are [[Sources.]] and who are the [[beneficiaries]]?
- This is not clear, so the objective is not clear.
- When I thought about letting agents live in this Scrapbox, I implicitly assumed "source/nishio, beneficiarynishio".
    - This is a very special situation.
- For example, if the "source of information/nishio and the beneficiary is someone who cannot read Japanese but can read English", it would be a bot that creates translations and explanations in English.
- If "the source of information is a book and the beneficiary is nishio," then it will be a bot that creates a summary of the book based on an understanding of my interests.
    - English videos and especially "I'm not good at audio input such as videos even in Japanese" and high cost since it is "English".
    - I'd value a bot that would watch around English videos for me and generate links with summaries of interesting times.
- Can the beneficiary become an agent itself?
    - It can be done if the agent is curious and the value is to have that curiosity satisfied.
    - So, "[[what is]] curiosity?"
        - It's not enough to get new information.
            - That would keep me from reading the random number table.
        - Want to get one step ahead of what you already have?
            - [[I can only understand one step ahead of myself]].
            - [["what you already have"]].
                    - [[Chicken and Eggs]].
                - [[Without knowledge, it is impossible to judge the value of knowledge]].
            - The only way to do this is to give them knowledge of the presets.
                - Knowledge you already have = your Scrapbox
                - So once you clone yourself.
            - New updates in other people's Scrapboxes, books and YouTube videos as input.
            - Vector search in chunks
            - Equivalent to "find by association from past memory."
            - Omit those that are already connected after they are found.
            - This gives us "associations not yet connected".

Hmmm... then...
- It's not enough to have a vector index with only the contents of /nishio to show to others.
    - Only useful as a first stepping stone.
- A vector index is needed to stock all the "past reads" by the agent
    - This would, of course, include other people's works.
    - In the future, I'd like to give them books to read, but for the early stages of development, I'd like to crawl the publicly available Scrapbox.
    - Related: [[Finding links between multiple projects]].

reading  [[Diary of 2021-05-04]]
- > That's going to be beneficial for some of them, but it's a bit of a chore.
- > How about creating a "free room" (project for bots) first?
- Read /nishio and write about a page a day in /nishio and as many pages as you like in the "Room for Bots", sort of

I even put a script in omoikane-embed that writes to Scrapbox and confirmed that it works. Something minimal (process complete! ) and tag it as "We have a system that interacts with Scrapbox", then fork it and create a repository for Scrapbox over here and add some functionality...

Ah, the current omoikane-embed is thinking "it's not a big number of pages, so it's OK" and plugging all the pages into the vector index every time instead of updating them incrementally.
If you're going to put it in /nishio, you're going to have to fix that...

---
This page is auto-translated from [/nishio/Scrapboxに住んでるエージェント](https://scrapbox.io/nishio/Scrapboxに住んでるエージェント) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
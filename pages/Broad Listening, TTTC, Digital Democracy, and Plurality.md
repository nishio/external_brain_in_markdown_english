---
title: "Broad Listening, TTTC, Digital Democracy, and Plurality"
---

I recently created [[Talk to the City Study Group]] for a one-hour study group lecture. This was too long, so I made a 10 minute version for an LT.

# What is [Broad Listening
?
> [nishio](https://x.com/nishio/status/1801205477990359465) The Difference Between Broadcasting and Broad Listening
>  ![image](https://gyazo.com/1a5328d749ad7a4ad4525e7cbed2a01e/thumb/1000)
The direction of the arrow is reversed.



# What is [Talk to the City
(TTTC)?
![image](https://gyazo.com/e05735418ecaf67a8a95d29cd9806442/thumb/1000)
OSS (AGPL) tool that displays a summary of topics in clusters
- [https://github.com/AIObjectives/talk-to-the-city-reports/tree/main/scatter](https://github.com/AIObjectives/talk-to-the-city-reports/tree/main/scatter)
concrete example
- [Issues and questions being discussed at the Tokyo Metropolitan Assembly](https://takahiroanno2024.github.io/tokyo-metropolitan-assembly-analysis-20240615/)
    - 6/15 [Anno published at](https://x.com/takahiroanno/status/1801856440145219827)
- [People's reactions and issues regarding Takahiro Yasuno's run for Governor](https://takahiroanno2024.github.io/yahoo-comment-analysis-20240610/)
    - 6/12 [Anno published at](https://x.com/takahiroanno/status/1800734598344925656)
- [Public Comment on AI and Copyright](https://nishio.github.io/tttc_aipubcom_japan/)
    - 5/31 I did [[TTTC: Public Comments on AI and Copyright]].



# How Talk to the City works
.
- ![image](https://gyazo.com/0630e4176f72582ae4cb259e84268e0a/thumb/1000)
    - Simple CSV with only two input columns, "comment-id" and "comment-body
    - LLMs extract opinions of moderate size
    - Clustering and visualization in BERTopic
    - Web UI to display it is created in React and rendered in static HTML
    - That's now hosted on GitHub Pages.
- Just run one Python script and it will do it all! Easy!
- Input data can be irrelevant to politics
    - Example: I added a book: [[Visualize the contents of the Plurality book with Talk to the City]].



# Why has there been so much broadcasting and so little broad listening?
![image](https://gyazo.com/8aed1a6ee239c672d1e504cdb48d0e9e/thumb/1000)
        - [[broad listening]]
- Technology to "duplicate" information developed more quickly and made it possible to "carry a voice to many people" (e.g., radio in the 1930s).
- But it couldn't be reversed, there was a flood of information.
- In the 2020s, the development of LLM technology made it possible to "summarize" and convey information



# What is [digital democracy
?
- Digital democracy has nothing to do with voting and majority rule
    - Better to think of it as "a mechanism to improve communication at large and aid in group decision making"
- Polls were invented as a way to "summarize people's opinions" at a time when "summary" technology was poor.
    - The system works like this: "Put a piece of paper with names written in a box, choose people by majority vote, and the person chosen speaks on behalf of the person chosen."
    - Advances in LLM are enabling better "summaries of people's opinions"
    - However, it would be difficult to erase and rebuild the current "social system" that is built on "paper and box voting", so it is realistic to gradually improve it from the easiest places.
- Many people confuse digital democracy with [[digital voting]].
    - There is a strong assumption that "[[democracy]] = [[voting]] to elect [[politicians]]."
    - This idea would be "We need to amend [[the Public Offices Election Law]] to elect politicians by digital voting -" but that's not "improving where it's easy to do."
    - For example: [[participatory budgeting]] , [[Participatory Budgeting: The Tokyo Case]].
        - Participatory budgeting in Suginami Ward already determines the use of a portion of the budget through Internet voting.
        - The way a group makes decisions is not just by electing politicians.



# What is [Plurality
?
- Social movement promoted by former Taiwanese Digital Minister [[Audrey Tang]] and others
- Book by Audrey Tang and Glen Weyl out 5/20
    - ⿻數位 Plurality: The Future of Collaborative Technology and Democracy
    - Japanese: ⿻數位 Plurality: Collaborative Technology and the Future of Democracy
        - Books about future democracy (= [[digital democracy]])
    - ![image](https://gyazo.com/1778594b1d609d53004799b20872cf33/thumb/1000)
    - I am actually a Contributor.
- Japanese version is being translated by Hiroo Yamagata, who has finished translating up to chapter 6.
    - CC0 so you can read everything online and ask questions.
        - For more stories: [/plurality-japanese](https://scrapbox.io/plurality-japanese).
    - To be published by Cybozu Style Books by the end of the year.
- Audrey plans to tour the world to promote Plurality
    - Audrey and her friends are coming to Tokyo in July and we are planning to have an event [[Funding the Commons Tokyo 2024]].


# References
.
    - [[Talk to the City Study Group]]
    - Probably the most detailed summary of concepts around Talk to the City in Japan at this time.
    - The reason why I think so is because I was asking my friend from Taiwan's Ministry of Digital Affairs to write this article, and he introduced me to the developer as the leading expert in Japan.
    - I'm writing this after knowing a lot of information, including information that hasn't been made public.
- Audrey Tang's talk at Plurality Seoul on 2023-12 (with Japanese subtitles)
    - [https://youtu.be/4J9v-j995LU](https://youtu.be/4J9v-j995LU)
    - Talking about Talk to the City
- Trailer for [[Audrey Tang]]'s documentary film [Good Enough Ancestor
    - [https://www.youtube.com/watch?v=Sqyxvyh69cU&t=8s](https://www.youtube.com/watch?v=Sqyxvyh69cU&t=8s)
    - He also discusses the Democracy Update, released on 5/20.
---
This page is auto-translated from [/nishio/ブロードリスニング、TTTC、デジタル民主主義、Pluralityの関係](https://scrapbox.io/nishio/ブロードリスニング、TTTC、デジタル民主主義、Pluralityの関係) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
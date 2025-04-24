---
title: "pKomorebiKagami2023-07-03"
---

[[pKomorebiKagami]]
- [[pOmoikane]]
- [[pPersonalPolis]] and [[pMAGI]] will be absorbed into this once


from [/omoikane/polis-like-systems-building](https://scrapbox.io/omoikane/polis-like-systems-building).
[[Polis-like system]]
- [[Polis]]に相当する部分の自前実装を作らないと技術的に面白いところがあんまりないなーと[[LLM Meetup TokyoのLT資料を作る]]をやっていて思った<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>

Creating a muddy "foundation".<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
- In [[a tool that reads created shorts and converses with an AI]], we were focusing on the superficial UI.
- but if you put data into Firestore in a messy way, it will suffer later.
- For ease of statistics later on, why not use RDB?
    - [ChatGPT log](https://chat.openai.com/share/275095cc-f389-4d9c-8b24-1e9d13520546)
    - Putting it in Firestore is hard simply to make it count.

branding
    - [[Japanese cockchafer (Melolontha japonica)]].

pKomorebiKagami

Create project komorebi-kagami
- Create PostgreSQL instance
    - Enable the Compute Engine API for
- Hmmm, I don't have any skin in the game as to what kind of setup and how much to charge.
- I don't know anything about it, but I created it in the development environment configuration.
- What should I do next?

Table Design
- User authentication is handled by Firebase Auth, so there is no need to wait for RDB on your own.
- The basic premise is that there are multiple yes-or-no questions within a single topic.
- Don't we need to put the information about the question in the RDB as well?
    - Hmmm? Which is it?
    - If you feel like you don't have to include it, let's focus on flexibility over performance.
        - We can put it in later when it becomes a problem.
- The table for the voting contents will contain the ID of the topic, the ID of the voter, the ID of the question, and the voting contents which can be 1, 0, or -1, and the time of the vote.
- <img src='https://scrapbox.io/api/pages/nishio-en/GPT/icon' alt='GPT.icon' height="19.5"/>This design allows each user to vote only once for each issue on each topic
    - Hmmm, I don't think so.
    - Either design the ballots to be overwritten when they already exist at the time of voting, or always add them and use only the most recent information at the time of tallying.
    - → The former is easier to do aggregate queries, but not historical.

- Don't they need to be indexed or something?
    - →✅

- The design can be made to overwrite the ballot when it already exists at the time of voting, or it can be designed to always add the new information and use only the latest information at the time of tallying, creating SQL for voting and SQL for tallying.
- →One query in either case fits within the expressive power of SQL, but the former seems to make more sense.
    - I don't think we should be able to get a history of voting changes.



- Connect with Cloud Shell
    - Cloud SQL Admin API must be Enabled

Ha, it's done!
- I was able to get from the NextJS TypeScript code to putting values into the Postgres table.
- When I read the password from .env.local it didn't work and when I hard coded it I was able to do it. Is the $ in the password doing something bad?
    - I changed my password and it worked.

[ChatGPT log](https://chat.openai.com/share/6e15b62f-55c5-4751-8d33-bfd89aff443c)


---
This page is auto-translated from [/nishio/pKomorebiKagami2023-07-03](https://scrapbox.io/nishio/pKomorebiKagami2023-07-03) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
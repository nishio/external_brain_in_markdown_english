---
title: "Story study session about connecting my Scrapbox to ChatGPT."
---

- [I connected my Scrapbox to ChatGPT.
    - [[Cybozu Labs Study Session]]  2023-03-24
- On 3/8, I connected my Scrapbox (here) to ChatGPT so that ChatGPT can respond back to me after referencing this Scrapbox.
- Published on 3/9 because several "I wanted to do this, I want to do this, I can't do this due to lack of knowledge" type stories were observed on the Internet.
- Multiple people who have used it or created derivatives of it.
- I shared the index I used from this Scrapbox for easy testing, and there were about 5 people who shared it as well, so I could let them interact and brainstorm in a virtual personality.

Output Example
- If not referring to Scrapbox
- > >>> What is Kozaneba?
- > Unable to answer. The information provided is insufficient.
- When referring to Scrapbox
- > >>> What is Kozaneba?
- > Kozaneba is a digital stationery tool for organizing thoughts. It has been released for test users but has not yet been widely announced. The developer feels that it is valuable to be used by many people.
- Another example
- > >> What is a blind spot card?
- > (No reference) Blind spot cards are cards written anonymously by others to point out problems or shortcomings of which they are unaware.
- > (with references) Blind Spot Cards are designed to help people recognize their blind spots, categorize the process to eliminate them into cards, and use them to solve problems. It is like TRIZ with a typology of physical patent literature. I envisioned a card with a picture and an explanatory booklet, but it is also designed to be used on a tote bag or something similar.


structure
- It consists of two scripts `make_index.py`(129) and `ask.py`(63) with about 100 lines
    - In the world, [[LlamaIndex]] and [[LangChain]] are related libraries, but I decided not to use them because it would be too much code to do what I wanted to do with them.
- Index Creation
    - ![image](https://gyazo.com/11b2ef80922d5c5b9363f492e8b3d10b/thumb/1000)
    - Chop the text in an appropriate way and make it [[embedded vector]] in OpenAI's [[Embedding API]].
    - This correspondence between sentences and vectors is sometimes called a vector index.
- question
    - ![image](https://gyazo.com/2a3e1d2dd207e60e2f0add64865e3cc4/thumb/1000)
    - It's not necessarily a "question," but it's too complicated to call it that, so I'll just call it a "question statement."
    - Embedding a query sentence into an embedded vector with Embedding API
    - Calculate the similarity between that vector and the vector of vector indices
    - Put them in order of similarity and put in as many as you can in the prompts.
    - Throw it to the ChatGPT API and have it create an answer.
- Q: How big is a vector?
    - A: So far 1536 dimensions, but the number has no deep meaning
- Q: What is similarity calculation?
    - A: OpenAI's Embedding API returns a normalized vector, so simply take the inner product ([[Cosine similarity]])
- Q: How fast is the similarity calculation?
    - A: Currently, I'm not trying to do anything.
        - I'm just doing Python's List and np.dot.
        - In that state, 22,000 pieces per second (MacBook Pro), and with this Scrapbox, 39,000 pieces in all.
        - There are many ways to speed up the process, I don't feel the need right now (ChatGPT API is much slower).
            - [GitHub - facebookresearch/faiss: A library for efficient similarity search and clustering of dense vectors.](https://github.com/facebookresearch/faiss)
            - [Using Elasticsearch Vector Fields for Text Similarity Searches | Elastic Blog](https://www.elastic.co/jp/blog/text-similarity-search-with-vectors-in-elasticsearch)
- Q: What is the scale and cost?
    - embedding
        - This Scrapbox has 17,229,603 tokens.
        - Embedding API costs $0.4 / 1M Token
        - That means about $7.
        - Embedded "technology behind coding" in its entirety for $0.13
            - (Amazing that this Scrapbox is for 54 books...)
    - question and answer session
        - gpt-3.5-turbo	$0.002 / 1K tokens
        - They used GPT 3.5.
            - 4096 tokens is the upper limit of the context, and I wrote code to use the full limit.
            - So about $0.008.
        - The GPT4 API was also released later.
            - For the same use, $0.15
            - If you use the full limit, it is $1.98 for 32K context.
                - This would be the "read and answer at least 62 pages that might be relevant to this Scrapbox" behavior.
                - About 1,000 tokens for a text-only page of the Engineer's Guide to Intellectual Production, so you can "read 31 pages of a technical book that might be relevant to your question and then answer it" for $300.
                - Frankly, I don't think you need to read that much for most use cases.
        - GPT 3.5 will read and answer 3 pages from a book for $1, GPT 4 for $25.
            - And it will point you to which page it was referring to.
            - GPT4 is still too expensive for casual use.
                - But what happens when the price is 1/10th?
                - What if it could be used locally for free without hitting an API?
                - I feel that this change is going to happen within a year.
            - I personally don't use the GPT4 API right now.
                - I have a $20/month subscription to ChatGPT Plus.
                - It pays off quickly because it can be used up to 25 times per 3 hours.

Essentially not dependent on Scrapbox.
- People who have tried using it as a source of other information.
    - Hatena Diary: [I connected my Hatena blog to Chat GPT - hitode909's diary](https://blog.sushi.money/entry/2023/03/10/190000)
    - Discord: [load past messages from your Discord into ChatGPT](https://zenn.dev/sizumita/scraps/44c6af06eadb27)
    - Of course, groupware and videoconference transcripts can also be targeted.
- book
    - I let him read "The Technology Behind Coding."
    - > >>> What is an object?
    - > (GPT3.5) An object is a concept for creating a "model" of a "thing" in the real world in a computer, and in programming languages, it is expressed as a collection of data and procedures for manipulating that data. In addition, object-orientation is a method of designing programs around these objects. Specifically, there are classes that express relationships among objects and methods that manipulate instances created from classes.
    - Technology behind coding p.187~
    - ![image](https://gyazo.com/c07380aa591c368d3a5f1707d9e1fd10/thumb/1000)
    - ![image](https://gyazo.com/ac403c5a4b056f0da17ce0659b0bdae2/thumb/1000)
    - > (GPT4) An object is a structure for representing concepts and things in the real world in programming. In object-oriented programming, objects have attributes (data) and behaviors (functions and methods) of their things. An object is an instance created based on a blueprint called a class, which is manipulated in a program and interacts with different objects. The goal of object orientation is to represent real-world problems more naturally and to improve the quality of code, such as by improving reusability and maintainability.
    - The weight of "original knowledge" has increased and the "technology behind the coding" factor has been lost.
    - These "concepts that have a lot of other written text" don't need to have their own data read.
        - The advantage of this approach is that minor coined words can be understood
:

```
Create a promotional tweet for Kozaneba.

Want to visualize your ideas and information using Kozaneba? 🤔
Organize 🌟Discussion
Explore 🌟tweet connections
🌟Find adjoining keywords
Kozaneba is digital stationery that will accelerate your intellectual production! ✍️🚀
For more information 👉 https://kozaneba.example.com
#Kozaneba #digital stationery #idea organization #discussion visualization
```



round-table discussion
    - [[AI Panel Discussion]]
    - I let the data from different personal Scrapboxes be discussed by the panel as "virtual personalities".
- [/villagepump/Scrapbox ChatGPT Connector roundtable mode](https://scrapbox.io/villagepump/Scrapbox ChatGPT Connector roundtable mode).
    - It's interesting that each of the six of us speaks from a different point of view.
    - With this data, you can do [[brainstorming]] with yourself + 6 other people anytime, anywhere.


Future Development
- Technically, it is possible to do the same thing for information in groupware.
    - There will be customer backlash against any information in the groupware being sent to ChatGPT, here is the problem
- The first half of the vector search is useful in isolation from ChatGPT
    - So a company specializing in search will provide that (like Elasticsearch).
    - So app companies can't take advantage of doing this on their own.
    - All you have to do is "make sure it's connected properly".
- It is technically possible to provide a small convenience feature
    - For example, maybe a "summarize" button on the kintone thread.
        - Simply add a "summarize" to the thread and hit API.
        - It would be less repulsive than "send all" because it would only be sent when the button is pressed.
    - Whether to release it as a feature to be offered to customers in the long term, with scaffolding shaky in six months, and whether to devote manpower to maintain a feature that breaks fast.
        - I think it's a different layer of decision making than technology.
- A [[Toolformer]]-like approach is attractive in the long run as a coupling with ChatGPT-like
    - <img src='https://scrapbox.io/api/pages/nishio-en/GPT-4/icon' alt='GPT-4.icon' height="19.5"/>Briefly describe Toolformer in bullet points.
        - Toolformer is a model that [* allows language models to use external tools (search engines, calculators, calendars, etc.).
        - Because existing approaches often require large amounts of human annotation or are limited to task-specific settings, Toolformer proposes a different approach.
        - Use of the tool should be learned in a self-supervised manner, without requiring a large amount of human annotation.
        - The language model should be able to determine for itself which tools to use and when.
        - Use large language models and in-context learning to generate API use cases and train the models to learn API calls.
        - Use a self-supervised loss function to determine which API calls are useful for token prediction.
        - Fine-tune the language model with API calls deemed useful.
        - Toolformer achieves excellent results on a variety of tasks with zero shots after learning to use the tool.
    - In other words [* teach AI how to use groupware
        - Operate groupware as needed to pull information, read it, and make decisions.
        - Information about what kind of operation you want is embedded in the response text in microformat.
        - ![image](https://gyazo.com/d2fad242e843c88d9718a872aae62a90/thumb/1000)
    - A future where groupware has "AI accounts" and we can communicate with them via mentions and DMs.
        - The "chat look" makes it hard to make users wait a minute, but the groupware notification look makes it acceptable to ask an "AI employee" to do the work and have it done in 10 minutes.
        - Some applications want fast reactions and some don't.
    - Even at present, if you ask, "I want to do something like this, what should I search for?" the search keywords will come up. We will make this progress and output them in a form that can be handled mechanically.
        - Example
            - <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I am planning to write a discussion on the relationship between Merleau-Ponty and Polanyi. Please suggest some key words to help me find references
            - <img src='https://scrapbox.io/api/pages/nishio-en/GPT-4/icon' alt='GPT-4.icon' height="19.5"/>The following are keywords that may be helpful in researching the relationship between Merleau-Ponty and Polanyi. Use these keywords to search for relevant literature and articles.
                    - Maurice Merleau-Ponty
                    - Michael Polanyi
                    - Perception
                    - Personal knowledge
                    - Ontology
                    - Epistemology
                    - EXPERIENCE
                    - Embodiment
                    - Origin of knowledge
                    - Structure of knowledge
                    - Tacit knowledge
                    - Social dimension of knowledge
                    - Intuition
                    - Language
                    - Gesture
                    - Semantics (semiotics)
                    - Teleology
                - Using these keywords, you can find literature and research on the philosophical thought of Merleau-Ponty and Polanyi and their relationship. You can also examine the philosophical traditions with which they are associated and their relationship to other philosophers (e.g., Heidegger and Hassard).
            - Doing a search with keywords that come up this way and summarizing based on that information would be Bing AI-like.
            - Is the first step to make this search target internal groupware instead of the Internet?
    - At this point, [[LangChain's agent]] looks close, but I can't decide if this will be the de facto standard in six months or if it will have collapsed.
        - Generally speaking, frameworks that have become bloated by accepting a wide variety of requests when the ground has not yet been broken often become difficult to earthquake-proof and collapse during earthquakes, but in the After GPT-4 world, GPT-4 may be able to assist in the renovation work.
        - In that sense, it deserves attention as "a software project by the people who are most proficient in using GPT4.
        - If you use it, you should understand what's between you and the ground.
- Currently, ChatGPT assumes that the person it talks to is "mainly a human being," but if a machine is in between and reads the command sequence written in microformat, it would be a good idea to prepare "commands to be displayed to humans" in the near future.
    - Artificial languages with defined grammars are easier for LLMs
- ![image](https://gyazo.com/3a1de274da1461bd7875f9685bffeaec/thumb/1000)
    - Isn't this, in a sense, an [[operating system]]?
    - For a while, languages and APIs for the operation of this intermediate system will be mixed and disorganized
    - And after a while, a de facto standard (the equivalent of [[the C language]]) is created.
- Huh? [Humans are just one of the peripherals.
    - ![image](https://gyazo.com/9eb9249214f856b89965b028b29f3d79/thumb/1000)


---
This page is auto-translated from [/nishio/自分のScrapboxをChatGPTにつないだ話勉強会](https://scrapbox.io/nishio/自分のScrapboxをChatGPTにつないだ話勉強会) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
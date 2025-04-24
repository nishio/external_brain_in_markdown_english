---
title: "maintenance model"
---

- A method of representing a program in a highly abstract way that is not source code and that is maintained over time, [[Keeps]].
    - Synonyms are [[temporary model]]. Something created temporarily for design discussion or conversation.
- What is a model?
    - In this context:.
        - Conversations.
        - A common understanding
        - Diagrams that are seen and not conversational are not good modeling.
    - In that sense, it is a [[schematic]] designed to assist communication when verbal or written communication is impractical.
        - Seems to me this is often useful not just for software projects.

    - I learned the term from [[Modeling in the Agile Era]].
- Specifically, the following were proposed
        - [[architecture]] Package and class diagrams
        - [[domain model]] Class diagram, ER diagram
        - [[key use case]]
        - User perspective: Typical usage ([[user story]]) Use case diagram
        - Use case mechanism: description of what is done in the source code to realize the user story Communication diagram, sequence diagram
    - Reason for design
- What is the first step in creating a maintenance model when the code exists but no maintenance model exists?
    - Creation of terminology dictionaries
        - Equivalent to a domain model
        - A description of what a word means in this project
        - The variation in this perception is
            - have trouble holding a conversation
            - Used in mixed meanings to interfere with source code search
            - Especially when the documentation is written in Japanese and the code is written in English, the correspondence can be mistaken, or a new translation can be implemented without realizing that there is a standard translation and be omitted from the search.
        - Not yet "illustrated" at the terminology dictionary stage.
        - As you describe the meaning of a term, it is explained by another term.
            - This is where the "relationship between terms" is verbalized.
            - It is a relationship between entities → ER diagram
            - Terms" and "concepts" at this stage do not necessarily correspond one-to-one to the class
                    - [[ontology diagram]].
        - It was suggested that [[Word frequency in source code]] be analyzed as a means of finding words that should be described in terms of meaning.



---
This page is auto-translated from [/nishio/維持モデル](https://scrapbox.io/nishio/維持モデル) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
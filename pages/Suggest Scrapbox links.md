---
title: "Suggest Scrapbox links"
---

- We have a lot of language data, and we want to support the use of this data by computer.
- The current well-known methods are search and recommendation, and the proposal method is a nice combination of the two.
- Search is a system in which a human enters a short "search term" and documents containing that term are pointed to.
    - Humans must come up with "search keywords".
- The suggestion system allows long sentences as input. Part of this long input becomes "search keywords".
    - If we tried to force the existing search system to achieve this, we would have to chop long documents into small pieces and search them over and over again, which is time consuming. I made some technical innovations to make it work in a realistic amount of time. For example, it takes less than one second to search my Scrapbox, which has 6500 pages, with 10,000 characters.
    - There is no need to create keywords just for searching. You can use it in such ways as "enter a sentence you are about to write and find related articles."
- I actually put this paragraph into the proposed system: [[sample1]].

- Relationship to Recommendations.
    - Recommendations, for example, can be imagined as other articles being displayed as "related articles" at the end of an article.
    - That's a system that takes a "long article" as input and points to "other articles that might be relevant".
    - However, existing systems indicate "articles that are related" but do not often indicate "how they are related. Therefore, humans cannot know what exactly is the relationship between the articles that the system points to as "relevant.
- The suggestion system can show "what phrases are common. The system can show, "This phrase in this document is also in that sentence, so I think they are related.
- Existing recommendation systems can do something similar. A word frequency-based method could display "this word is common.
- However, when it is a word rather than a phrase, often humans fail to understand the meaning. For example, "General Manager's Association" would be inscribed as "Hon/Department Manager/Association. Even if it is displayed as "The word "general manager" is common to this article," the information is too reduced to be understood.
- The proposed system presents common parts in phrases (sequences of multiple words) rather than words.

- The most similar existing system to this system's output is Scrapbox's linked page display, in which a human explicitly brackets (brackets) a phrase and documents in which that phrase commonly appears are displayed at the end of the page as "linked".
- The Scrapbox method requires a human being to have bracketed a large number of documents in advance. The proposed system is a method that generates Scrapbox-like links to a pile of unmarketed documents.

- Detailed appeal points
    - If it is as long as one tweet, the result will return in the order of milliseconds. Explosion speed.
    - If integrated with a document writing tool that does not require active thought to search, recommendations can be made using the content of the document as it is being written while it is being created. Without having to switch the mode of mind to "think of search keywords" while writing, you can find common phrases in a huge stock of documents.
    - Ambiguous search. The search ignores verb conjugations, presence or absence of particles, and capitalization of English letters, thus absorbing notational quirks. For example, "information sharing" and "information sharing," "information sharing" and "information is shared" are all mutual search hits.


----- old
![image](https://gyazo.com/74fc2630ca4191cb6327b7c5c4dae1e3/thumb/1000)
A system that performs an ambiguous search of all 6500 pages in my Scrapbox for each edit and presents pages that have key phrases in common with the text you entered.
- ![image](https://gyazo.com/d68155570764c1439288c9021c57dc4a/thumb/1000)

Search vaguely
![image](https://gyazo.com/48cdb3505c123a4abc14aa2840a0b208/thumb/1000)

![image](https://gyazo.com/88b3e9528035d928ef0909d6a146d01d/thumb/1000)
- The major difference from the common "related article recommendation" is that "related" has a human-understandable label. This is quite sympathetic to Scrapbox's philosophy. For example, in the above example, if there is no name for the "related," the "related to probability integral" label would be "Why? in the example above. With this method, "DX is common" is displayed, so we can understand that "that dx is a symbol for integration.

---
This page is auto-translated from [/nishio/Scrapboxのリンクをサジェスト](https://scrapbox.io/nishio/Scrapboxのリンクをサジェスト) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
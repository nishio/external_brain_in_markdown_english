---
title: "A system that relies on a single search will be limited to about 1,000 cases."
---

On the topic of "information-storing services reach a limit of 1,000 cases," I tweeted about why and under what conditions that would happen.

3-line summary
- A system that relies on a single search will be limited to about 1,000 cases.
- A "link" is a useful solution to this problem
- Scrapbox is creating benefits beyond search with its link-related features.

    - [[Organizing Information]]
    - The meaning of the word "organize" when used in the context of "organizing information."
        - The purpose of the act is "to get what you need as soon as you need it.
        - Full-text searches of electronic information greatly aided that goal.
        - The "organizing" of using full-text search doesn't look like organizing to someone who sees organizing as categorizing and putting things in boxes.
        - From such a person's point of view, "I just put everything in one place in a jumble without organizing it.
        - On the other hand, those who are used to "organizing" using search perceive those who categorize as "playing inefficient organizers by dragging out physical images.

Limitations of the amount of information
- Perspectives on organizing information
- Approach to overhang so that all can be seen.
    - I reach my limit after about 100 sheets.
    - Human viewing angle and eye resolution issues
    - For larger amounts of information, the only choice would be to choose an "organization method that is not always visible.
    - [[Classify and put in a box.]] Approach.
    - It works well when the "proper classification method" for the subject is clear, but often it is a matter of "Huh? Where should I put this?" happens.
    - [[Search and find]] Approach
    - When there are 10,000 original data, a search for a keyword that hits 1% of the ones will yield 100 results.
    - If the search results simply "show all matches," we run into the limit of what a human can grasp by looking at the list.


original log
[https://twitter.com/nishio/status/1331887988943384577](https://twitter.com/nishio/status/1331887988943384577)
- In terms of organizing information, the approach of "sticking it all out so you can see it all" reaches its limit after about 100 sheets. This is a problem of the angle of human vision and the resolution of the eyes. For a larger amount of information, we have no choice but to choose an organization method that does not allow us to see the information all the time.
- The next item is "[[Container Metaphor]]". This is a method of preparing "containers" such as categories and folders first, and then categorizing the items into them. You may have been told to put your toys in a toy box when you were a child. This is a method that many people have experienced and mastered.
    - This works well when the "appropriate classification method" for the subject is clear. However, in the actual situation of "organizing what has not been organized well yet," the pre-made classification method is often not appropriate. It is not easy to say, "Oh, what is that? Where should I put this? will occur.
- When "something is found that cannot be classified well by the previously determined classification method," what should be done is "to think of a way to classify it well and reclassify everything accumulated in the past according to the new classification," but most people think this is too much trouble and put it in the appropriate place. As a result, the classification gradually breaks down.
- The more "properly stored items" that do not follow the classification method, the more "not where I thought it was" will occur when I look for it when I need it. This happens even when one person is organizing alone, but it is even more serious when many people are organizing together.
- That is why the idea of "don't expect ordinary people to maintain consistent classification, it is impossible. And as a solution to this problem, the idea that "if everything is digitized, it can be searched and found" was born.
- Many people may be ambiguous about the meaning of the word "organizing" in the case of "[[Organizing Information]]. In concrete terms, on the other hand, the purpose of the act is "to be able to retrieve what you need as soon as you need it. Full-text search of electronic information has been very useful for this purpose.
- This "organizing" doesn't look like organizing to those who see organizing as sorting physical things into boxes. To such people, it is "just putting everything in one place in a jumble without organizing it. On the other hand, those who are accustomed to this method perceive those who categorize as "dragging out physical images and playing inefficient organization.
- Now that we have reviewed the flow of "organizing by list," "organizing into boxes," and "organizing by search," we can see that there is a limit to the number of items in the "10,000 items" list, which is about the limit of what can be found when relying solely on search. This is due to the fact that "human beings decide search keywords" and "search results are listed.
- I finally got to the main topic I was going to write about. When there are 10,000 original data, a search for a keyword that hits 1% of the ones will yield 100 results. This is "the limit of what a human being can grasp by looking at the listings.
- In the past, when the Internet was idyllic, Google succeeded in providing high quality search results by aligning its search results based on the idea that "pages that are linked from many other pages are important pages. But that success has attracted self-serving SEO, which is no longer as effective as it once was. Transitional period of civilization
- The way to avoid this "too many search results problem" in operation is to "add keywords to narrow down the search results," but here another problem becomes a barrier. The keywords assumed by the person who wrote the document and the keywords considered by the searcher when searching for the document do not match.
- For example, let's say you need to touch something on your card when you enter your company's office. You accidentally forget to do that and come to work and think, "What am I supposed to do in a situation like this?" and you try to solve it by searching, what should you search? A card key? Security token? Employee ID card?
- Otherwise, for example, in a simple full-text search, expressions such as "sharing information" or "sharing information" will not be a hit when searching for "information sharing". Then, if you narrow down the search using the two keywords "information" and "sharing," you will get hits even if they appear separately in completely unrelated paragraphs, because in many implementations they are just ANDs.
- Incidentally, as part of my research at Cybozu Labs, I am working on a search engine that can absorb this kind of shaky notation, but I am not ready to put it into production yet.
- If we try to solve the problem of shaky notation with the current technology, the approach is to add shaky keywords as soon as we think of them. Therefore, it is necessary to be able to add keywords easily after posting.
- Even if there were no notational shaking at all, there would still be problems with the search. If the search results are sorted by most recent, the "most recent statement for that concept" will be at the top, which is often not what we really need. So we want to determine "importance" in some way.
- This is likely still valid in the context of organizing information within an individual or organization, since scoring based on PageRank and link count has been successful once before and the reason it stopped working is self-serving SEO. When it comes down to it, the "link" information becomes an important source of value.
- Even if there is no shaking, it doesn't solve the problem of wanting to know "what to do if you forget your card key" instead of the latest information "Mr. A forgot his card key today", but if there are free posts and links, the shaking will be absorbed by a post saying "I came to the office and didn't find my employee ID card, but I found the solution here" and the importance of the linked page will increase. It's a win-win situation!
- Scrapbox is a service that focuses on making it easy to create these "links" from the notation level. When I actually used Scrapbox, I found many times that "I couldn't find what I was looking for in the search, but I found something else that seemed related, and when I opened it, I found what I was looking for in the list of links at the end of the page.
- So, a system that relies on a single search will be limited to about 10,000 results, and "links" are a useful solution to that problem, and Scrapbox has already realized the importance of links and is actually creating benefits beyond search with its link-related features.
- Of course, I don't think the current situation is perfect, and I don't know if Scrapbox will evolve or if another better service will emerge, and even if the missing features are clearly identified, it's not a business decision how to prioritize the implementation of them.
- Specifically, when you start to link a certain policy and after a while you have a lot of content and you want to change the policy, refactoring is already implemented, but if you accidentally merge the content, you cannot revert back to the original policy, and I think that splitting is more necessary than merging. I think it is necessary to split rather than merge, but only heavy users can benefit from that.
- Regarding the topic of "information-storing services reach their limits at 1,000 cases," I wrote a story about why and under what conditions that happens. I'll let it sleep overnight and put it all together in Scrapbox tomorrow.

It was titled [[Nodal Point of Thought 20201127]] until 2022-03-01
Related Discussion Summary
- [/villagepump/Scrapbox's 10,000 page wall](https://scrapbox.io/villagepump/Scrapbox's 10,000 page wall).
Discussion in Nota
- [/nota-private-sample/blind-spots-in-full-text-search](https://scrapbox.io/nota-private-sample/blind-spots-in-full-text-search).

relevance
    - [[Information Organization 2.0]]
    - [[Search-centric UI]]

---
This page is auto-translated from [/nishio/検索一本に頼るシステムは10000件程度で限界になる](https://scrapbox.io/nishio/検索一本に頼るシステムは10000件程度で限界になる) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
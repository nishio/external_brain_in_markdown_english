---
title: "sample1"
---

Entry into the system
>  We have a lot of data on language, and we want to support the use of this data by computer.
>  Search and recommendation are two well-known methods today, and the proposal method is a nice combination of the two.
>  Search is a system in which a human enters short "search keywords" and documents containing those keywords are pointed to.
>  Humans must consider "search keywords".
>  The suggestion system can input long sentences. This long input is used as "search keywords".
>  If we tried to force the existing search system to achieve this, we would have to chop long documents into small pieces and search them repeatedly, which is time-consuming. I made some technical innovations to make it work in a realistic amount of time. For example, it takes less than a second to search my Scrapbox, which has 6500 pages, with 10,000 characters.
>  There is no need to create keywords just for searching. You can use it in such ways as "enter a sentence you are about to write and find related articles."

System Outputs
- ![image](https://gyazo.com/3fa14cbc53458503b4605dcffb4110ba/thumb/1000)

System Output Excerpts
- Enter the `keyword` and then the `keyword`.
    - This cutout is subtle.
        - [[Nodes of Thought2019-10-14]]
        - >   [[Knowledge Storage Format]]
        - >   [[The form of knowledge representation must be updated]]
        - >  Scrapbox is on a pretty good track.
        - >  But "[[Update of knowledge representation format]]" and "knowledge representation format must be updated" are not common keywords
            - I worked hard on an ambiguous search to solve this very problem.
        - >  There is a hint that the keyword might be "[[stock of associations]]" but it hasn't been solidified yet.
        - >  Searching for non-keywords (e.g. documents) from keywords can now be done by search, what we need is to find keywords from non-keywords, isn't it?
            - The system looks for keywords in long sentences that are not keywords and shows the results of searches with those keywords.
        - [[associative device]]
        - > [[recommendation]] engine for similar entries is "long text to long text"
        - >  [[search (e.g. for someone using a search engine)]] is "keywords -> long text"
        - >  Scrapbox link display is a combination of "long text -> keyword" and "keyword -> long text
        - >  [[2-hop link]] did it twice more
        - >  Given the idea that Scrapbox is a [[stock of associations]], this process is [[suggestion]].
        - > I feel we are one step closer to realizing the [[Knowledge Weaving Program]].
        - Talking about the relationship between search and recommendations, and the Scrapbox-like relationship between the best of both worlds.
        - When I wrote "associator," there was no proposed system yet, so I called the system that connects multiple "links (associations) explicitly written by humans" an associator, with Scrapbox in mind.
        - Proposed system associates without "explicit human associations".
- Document`.
        - [[link suggestion]]
        - This page was written recently in the process of creating this system
        - [[Support for combining your past writing with your current thinking]]
        - Written on 2015-07-13
        - > When I reread my past writings for some reason, I sometimes find myself thinking, "Oh, this is what I wrote, I can apply it to what I am thinking about now", and I wonder if this process can be enhanced by software or methodology.
        - > Tatsuo Yamashita [[Similar document search]] would be good... If you are Nishio-san, you can use "Intellectual production technique by [[word2vec]]" or "Idea support by word2vec" or something along those lines...
        - > Toshiyuki Masui Why not Wiki?
        - >  How can we use wikis to enhance the "process of realizing that what we thought in the past is useful for what we think now"?
        - >  Toshiyuki Masui In the case of Gyazz, pages that use the same keywords are shown, so there is a possibility of recalling old ideas.
        - > I see, same keywords. Are those keywords extracted by morphological analysis or something? Do humans add them?
        - > Toshiyuki Masui: A human being will put it on.
        - The [[Gyazz]] feature mentioned here later became Scrapbox, which I started using.
        - [[inverted index and pointing]] 2018
        - >  [[Documents are located]]
        - >  [[pointing at]]
        - I think it might have something to do with it.
        - [[hierarchical]] 2019
        - > Is there a scale that does not depend on the contours of the object?
        - I've been thinking about this problematic issue and noting another approach recently: [[DF with length as a parameter]].
        - This method uses [[suffix array]], so it seems to work well with the suggestion system.
- `Recommendations`.
        - [[The advantages of Scrapbox (Part 2)]]
        - > Bracketing verbs and so on.
        - > Key phrases in noun form often tend to be [abstract concept
        - > On the other hand, verbs are often close to [metaphor
        - This is why I was dissatisfied with keyword extraction that only extracts noun phrases
        - [[Intelligence systems]]
        - >  [[Interference Effects of Ideas]]
        - Exactly what's happening here right now is the interference effect of an idea.
        - >  [[Recommendations not based on similarity]]
        - At the time, I hadn't yet come up with what exactly a non-similarity-based recommendation would look like.
        - The suggestion system is "not similarity-based recommendation."
        - Not sorting documents with a "similarity to input" score.
        - Finding "good key phrases" in the input and sorting by goodness score
        - [[Recommendations and Scrapbox]]
        - In addition to word co-occurrence recommendation and Scrapbox recommendation by [[Explicit Bracketing]], tree structure is also considered as a kind of recommendation.

---
This page is auto-translated from [/nishio/sample1](https://scrapbox.io/nishio/sample1) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
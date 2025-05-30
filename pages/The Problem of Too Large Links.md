---
title: "The Problem of Too Large Links"
---

- The adjective "big" is hard to convey.
    - The basic premise here is that "[[link]]" refers to [[page set]].
    - An edge of an undirected graph is a set of two elements at a vertex, but the Scrapbox linker extends this to an arbitrary number of elements
    - Q: Isn't this a directed graph?
        - With naive hypertext, the link is an edge of a directed graph, so the order of the two elements makes sense.
        - A wiki-style system that automatically creates backlinks would make this an undirected graph.
        - Scrapbox can also distinguish "link/sublink", but here we have an undirected graph with the target relationship as the relationship to which the navigation is connected.
    - With Scrapbox, furthermore, "the link is not necessarily to an existing vertex."
        - Include non-existent vertices in the vertex set
        - Plus, the two-hop link is effectively a "link to a set of pages."
        - When this set is too large, there is little benefit to humans from displaying all of it.

The reason automatic linking doesn't work is because a way to make it work hasn't been created yet.
- The mistake of "trying to link all pages where a particular keyword appears."
    - That's like search results.
    - Easily becomes a "too-big-to-fail" link.
- The same problem occurs with automatic keyword extraction.
- On the other hand, the "links are made by humans" policy that Scrapbox has adopted hasn't solved the problem either.
    - I've manually added too many "KJ method" links because I thought it was important, and now it's clearly too big.
    - If you keep thinking about a particular subject, the links on that subject will grow too large, and the effectiveness of Scrapbox will be compromised.

In order to achieve a preferred state, we must know what kind of state is preferred
- At any rate, links that are too large are not good.
- How many Scrapboxes or more are rated "..."?
- Statistics on the size of each user's links.
        - [[Scrapbox Statistics 2019]]

- [[Splitting links that are too large]]

[[composter]] of [[PrivateBox]].
- You can pour an entire book into the current Scrapbox, but even if you do that, you won't be happy with the current Scrapbox.
    - Because links are scarce?
- Should we automatically generate links?
    - Keyword extraction and automatic linking
    - → Tragedy!
        - [[Mechanisms to turn them into "good links" after the fact]] are needed

The unexplored name list is also in a bad state due to the "supercreator" tag on all the supercreators.
- The link with the most people in it is not very informative.

> Even the "links are made by humans" policy that Scrapbox has adopted hasn't solved the problem.
- > I've added too many "KJ method" links because I thought it was important to do it manually, and now it's clearly too big.
- > If you keep thinking about a particular subject, the links on that subject will grow too large, and the effectiveness of Scrapbox will be compromised.
[/villagepump/problems with too large links](https://scrapbox.io/villagepump/problems with too large links).
- > A problem that inevitably arises as the number of pages increases
- >  Sometimes you don't think a link is too big at first, but as more pages are added, it becomes too big `[yosider.icon]`.
- The KJ Method."
    - ![image](https://gyazo.com/748c9ee5c30ba52363f02cde6bc296ce/thumb/1000)
    - I want to do something about it.

---
This page is auto-translated from [/nishio/大きすぎるリンクの問題](https://scrapbox.io/nishio/大きすぎるリンクの問題) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
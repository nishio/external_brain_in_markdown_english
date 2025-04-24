---
title: "pVectorSearch2023-06-02"
---

[[pVectorSearch]]
2023-06-01
- I tried it with various things in [[qdrant]], which I built locally with Docker.

2023-06-02
[[Scrapbox ChatGPT Connector]] first used a mapping from cleaned text to embedded vectors (1)
- This is a cache to avoid hitting [[Embedding API]] repeatedly with the same string when Scrapbox is updated.
- Later, I thought, "It would be better if I could not only find highly similar strings, but also display the Scrapbox page that contains them," and decided on (2).
- ![image](https://gyazo.com/4178a1bc88bc340262ee1dfd244c4b17/thumb/1000)
    - This check is O(1), so you can call it every time you process N cases.
- The search itself is done O(N) after the request is made.
    - ![image](https://gyazo.com/8f98367d6510519365d4b05d6ab9e1d8/thumb/1000)
    - My Scrapbox scale is 1-2 seconds, which was enough for local CUI use.
    - Files were created for each project, which made it possible to search by project.
    - But it's absurd to convert it to a service in this form, so I'd like to relegate the vector search part to other services.

Payload of qdrant
- ![image](https://gyazo.com/283e276e1699d03c47a402b6759f98b2/thumb/1000)
- Put data from multiple projects in one collection and distinguish them by payload
    - Another option is to separate the collection by project.
- How to determine the id
    - If the id is the same, it will be overwritten.
    - The idea that a hash value of text is fine
        - Assume that it is rare for an exact match to occur on different pages or projects, since multiple lines are chunked together.
    - ⭕️ to be a hash value of project, title, and text tuple
        - Stance that takes the hash value of the non-ID portion of the payload
        - Let's do this.
    - Hash value is determined by project, title, and chunks are sequentially numbered
        - When the original data is updated, it is generally overwritten without deleting the old one.
        - This is tricky.
        - We need to separate what to do with the updates.
- Put the thumbnail URL in the payload or
    - not allow in
        - Not included in the JSON exported from Scrapbox in the first place.
        - At the search results display, hit Scrapbox's API to get

What to do with the update?
- ⭕️The proposal is not a service that requires 24/7 operation, so I wouldn't worry about it.
    - It's not a big problem if an old fragment is hit.
    - If there's a problem, you can just delete it and reinsert it.
- When updating, delete the old one based on "which page of which project to update" before adding the new one.
    - If you're going to be serious, this is the way to go.
    - Either way, I'm tempted to skip "hitting additional APIs even though the vector is not updated" because it's useless.

I want to cache the embedded API, so this is what happens.
- ![image](https://gyazo.com/ee0a29a5dcf8a19d0681d56247e4fc88/thumb/1000)
- No, no.
- ![image](https://gyazo.com/17739a046b2fb05d3391bcc60f7cabfe/thumb/1000)
- Like this.
- This time I'll make a full one, so I'll send all the cache contents to qdrant, which is fine, but when I update it, I'll need to make a list of what pages are eligible for the update.
    - Well, but the mechanism to update the system should not be thought of now, it should be thought of after the MVP to user value is established.
- No [[parallelization of embedded API calls]].
    - I'm thinking we should do it, but it usually comes down to "let it run and sleep rather than implement it".
    - [Asynchronous HTTP requests in Python using aiohttp and asyncio](https://www.twilio.com/ja/blog/asynchronous-http-requests-in-python-with-aiohttp-jp)
    - I guess I need to make aiohttp.ClientSession hit where I am hitting with requests now...

Why are there clean text and non-clean text?
- It is recommended that text passed to the embedding API should have line breaks collapsed to spaces.
- On the other hand, if you put it in the payload, you can't do line-by-line processing in the UI, etc. afterwards.
- For example, [[URL Fragment Text Directives]].
    - [example](https://scrapbox.io/nishio/pVectorSearch2023-06-02#:~:text=%E5%9F%8B%E3%82%81%E8%BE%BC%E3%81%BFAPI%E3%81%AE%E3%82%AD%E3%83%A3%E3%83%83%E3%82%B7%E3%83%A5%E3%81%AF%E3%81%97%E3%81%9F%E3%81%84%E3%81%8B%E3%82%89%E3%81%93%E3%81%86%E3%81%AA%E3%82%8B%E3%81%8B)
    - Scrapbox has per-row permalinks, but the exported data doesn't include row IDs, so I can't create row links from search results.
    - So use URL Fragment Text Directives
        - (Wouldn't it have been better to implement the link in Text Directives, since the link with the line ID is not human readable to begin with, and there are no hints at all when it breaks? I think it would have been better to use Text Directives.)

2023-06-03
- done: `44784/44784 [15:12:59<00:00,  1.22s/it]`
- I'll put in 100 for now.
    - `100/100 [00:02<00:00, 46.72it/s]`
    - 2 seconds for 100 cases, 16 minutes for 50,000 cases
- I'll try to put in a batch of 100 cases each.
    - `10/10 [00:05<00:00,  1.80it/s]`
    - 5 seconds for 1,000 cases, 250 seconds for 50,000 cases
- I'll try to get it all in.
    - VM RAM consumption reaches 1GB at about 17%.
    - `446/446 [04:08<00:00,  1.80it/s]`
    - I'm not sure about the free POD for the cloud version, which is 1 GB.
        - Will memmap kick me out if I go over, or will I fall?
        - `404 page not found`
            - I hadn't used it for a while and it was inactive.
        - `446/446 [09:46<00:00,  1.32s/it]`
            - I was able to upsert normally without any errors.
- Search for.
    - I'd like to be able to not only find "highly similar strings" that are not yet in the data, but also display the Scrapbox page that contains them.
        - ![image](https://gyazo.com/673b71ee15f87d69f87418357558fcf7/thumb/1000)
        - (of) good appearance
        - It would be interesting to get some info on the VERSION.
    - "Not the final work, but to assist the person in the intellectual production of the work at the stage of creating it."
        - ![image](https://gyazo.com/a1f5470fb6ba3e215dd0aa7a8bde1e85/thumb/1000)
        - Hmmm, this is a `What's this? It`s a passage, but it`s not a hit.
        - In other words, if themes A to C are written as "ABC" in short, and only B is written as "BBB," the latter is the one that is hit when searching for B.
            - It would be interesting to put all lines longer than a certain length in Scrapbox into a line-by-line vector search (a barbaric idea).


---
This page is auto-translated from [/nishio/pVectorSearch2023-06-02](https://scrapbox.io/nishio/pVectorSearch2023-06-02) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
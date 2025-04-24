---
title: "pVectorSearch2023-06-07"
---

prev [[pVectorSearch2023-06-06]]
- > Next action is to suck the data from the public project and index it without going through export

[/halsk](https://scrapbox.io/halsk) 1281 pages
[/yuiseki](https://scrapbox.io/yuiseki) 2679 pages
[/tkgshn](https://scrapbox.io/tkgshn) 5648 pages
First from /halsk
- 127 sec
Two left.
- 335 sec
done

[[pVectorSearch2023-06-02#647a080aaff09e00006bd34e]]
- [[Parallelization of embedded API calls]]
    - [Asynchronous HTTP requests in Python using aiohttp and asyncio](https://www.twilio.com/ja/blog/asynchronous-http-requests-in-python-with-aiohttp-jp)
    - I guess I need to make aiohttp.ClientSession hit where I am hitting with requests now...
- Now hitting on requests" is False
    - I'm using the official openai library.
    - This can be passed in a list for batch processing.
- [Rate limits : OpenAI API](https://platform.openai.com/docs/guides/rate-limits/overview)
    - 3,500 RPM / 350,000 TPM

The layer of parallelization was not what was originally planned.
- I thought it was a function that calls the embed API.
- A class that represents an index with a method to execute it in batch.

It's done, so we run it and go to lunch.

> This model's maximum context length is 8191 tokens, however you requested 9158 tokens (9158 in your prompt; 0 for the completion). Please reduce your prompt; or completion length.
- oops

Stop at PDB and observe
:

```
(Pdb) print(list(map(get_size, texts)))
[85, 122, 88, 118, 5, 106, 100, 100, 9158, 9152, 9164, 121, 113, 81, 456, 133, 45, 6, 6, 7, 514, 351, 278, 441, 322, 27, 210, 515, 517, 252, 23, 28, 363, 92, 486, 318, 350, 326, 276, 340, 418, 355, 309, 292, 366, 334, 273, 387, 349, 341]
```


Ah, I see, that's one line.
- [https://scrapbox.io/yuiseki/https:%2F%2Fplatform.twitter.com%2Fwidgets.js#613321a0bb24d40000440059](https://scrapbox.io/yuiseki/https:%2F%2Fplatform.twitter.com%2Fwidgets.js#613321a0bb24d40000440059)
- If the chunked file is huge, only the first part of the file is taken and embedded.
    - I originally did that, but when I made the parallelization, it was embargoed, so I threw it into the API as long as it was.

I don't know how long this trouble will take.
- `238/238 [11:46<00:00,  2.97s/it]`
    - This is the [/tkgshn](https://scrapbox.io/tkgshn)data that ran after the fix
    - The 5748-page Scrapbox is divided into a little over 10,000 chunks and processed in 238 batches of 50 pieces each.
    - It is about 3 seconds per batch, and the total time is like 12 minutes.

Put in Qdrant
- `ResponseHandlingException: The write operation timed out`
- I was able to hit it without `wait=True` on /nishio, but when I tried to get 3 people in at once, 1.5 people died.
    - WAL overflowed?
    - PS: Conflicts with indexing
- If you add `wait=True`, it looks like this
    - `117/117 [02:57<00:00,  1.51s/it]`
    - `44/44 [00:54<00:00,  1.23s/it]`
    - Well, I'll be in there in a few minutes, so it's nothing to worry about.

Now you can cross search.
- What's that? Why do I get hits only on yuiseki?
- Is that possible?
- Oh, I was doing `client.recreate_collection`.

redoing
- I get `ResponseHandlingException: The write operation timed out` even if `wait=True`.
- It happens even if you `sleep(1)`.
- [Bulk upload vectors - Qdrant](https://qdrant.tech/documentation/tutorials/bulk-upload/)
    - Ah, I see, you stop the generation of indexes.
- `23/23 [00:34<00:00,  1.48s/it]`
- `117/117 [02:59<00:00,  1.53s/it]`
- `44/44 [01:15<00:00,  1.72s/it]`
- It's done.
- ["On Computer Assisted Deliberation and Consensus Building"](https://nishio-vecsearch.vercel.app/result/qomP1z9fIIWcaX0YZ4Vp)
    - I can do a cross search.

![image](https://gyazo.com/e23a56be5c403dfdf5d2452e0ec051bf/thumb/1000)
- Plenty of room.

What we were able to verify this time
- If the other party is a public project in Scrapbox, no special work by the other party is required
- The time and monetary costs are not significant.

> [@yuiseki_](https://twitter.com/yuiseki_/status/1666402716841840641): If you say that we will combine multiple people's personal Scrapboxes and make them vector searchable to test their usefulness in [[cooperation]], [[consensus building]], etc., I feel the priority of what and how much to write in my Scrapbox explode!

> [@nishio](https://twitter.com/nishio/status/1666413721210740736?s=20): in a little while, anyone can throw an agenda at this
> [/villagepump/Scrapbox ChatGPT Connector Roundtable Mode](https://scrapbox.io/villagepump/Scrapbox ChatGPT Connector Roundtable Mode)

I looked at it on my iPhone and it looked terrible.
- ![image](https://gyazo.com/fb090d7d77fef80327e2a58e395d05fb/thumb/1000)

> [@yuiseki_](https://twitter.com/yuiseki_/status/1666415420323291141?s=46&t=gkSZtjGEtUZPO0JCzBxCBw): added about 100 pages of important information for now!
- We need to implement an update function...


---
This page is auto-translated from [/nishio/pVectorSearch2023-06-07](https://scrapbox.io/nishio/pVectorSearch2023-06-07) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
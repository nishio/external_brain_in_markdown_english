---
title: "pPersonalPolis"
---

Thinking about "Personal Polis" as the next social networking service after Twitter.
Polis + Mastodon

Mastodon
- Federation
- In short, it sends update notifications to those who have pre-registered to receive them.
- Our system does not have to be Twitter-like.
    - Strong feeling that Twitter is not suited for [careful deliberation
- Wouldn't it be better if it was Polis-like? The story of "Polis-like

Personal Scrapbox
- There are two styles of posting on pre-verbalized "themes" and one style where one "person" can post anything that interests him or her.
- Confidence that the latter will work
    - Pre-linguistic themes are existing frames of thought, and if space is delimited by them, they hinder the discovery of cross-border ideas

But want to interact with others
- Scrapbox needs a mechanism to do this well.
- Some [[invite people to their personal Scrapbox]] approach.
- I have a feeling I'm not going to be able to do much work with this Scrapbox.

2023/4/28
Personal Polis
- Mastodon is notified when one of your friends posts an issue
- So, reactionarily, we can immediately pass for and against.
- Retweet it and your own friends will get the message.
- Isn't that enough? I have a feeling that's it.
    - Is it another screen to see the distribution?

The theory that if you can post anything, the visualization using that anything will not work.
- Well, I can manage if I work hard at the math, but I'm not sure that's the easiest way to understand it - I'm not sure.
- For example, when you think of creating software to handle structure on a network, the idea from graph theory is "all you need is vertices and edges.
    - The story started a little too abstract.
- Scrapbox pages are on the network, but the pages as containers contain serialized rows.
    - Kozaneba is something that works independently of each of these lines, but even the author doesn't use it all the time.
        - Use only when necessary
    - That's because there are different degrees of freedom in operating the elements depending on the work you want to do.
        - People who say things like "wouldn't it be nice if we could do the KJ method in three dimensions" are KJ method airplayers, and most of them don't even use the two-dimensional degrees of freedom.
        - They say that bullet points are two-dimensional, and they don't take full advantage of the freedom of two dimensions, so they don't recognize that bullet points are a more restrictive state than that.
    - And that bullet points are sufficient for the appropriate degree of freedom when writing down the thoughts that come to mind.
    - Similarly, considering Polis, the constraint that each opinion corresponds to a line, so there is a container to wrap it in, is natural.
    - It would be nice to have a container that doesn't have to be titled first.
        - I'd move the line to another container after the fact.
- Like [[metanote]] for notes, it would be nice to have a meta-Polis based on Polis, with new stuff added

2023/5/8
- In the meantime, if you just want to host Polis on your own, it looks like you just need to set it up with Docker.
- If you want to use Polis for internal discussions that you don't want to put on an outside server, that sounds like a good idea.
- I found a description of Google Cloud Translation API settings in the configuration file, so I think I can create a version with machine translation that I experienced at Plurality Tokyo if I configure those settings.

Assuming Polis can be moved at hand, what is the next action?

I want to issue credits to people who voted for me based on the number of votes they cast.
- Aside from whether or not that will be the cost for opinion submissions in the future.

With the current Polis, 1 conversation = N posts, so I have to share the URL of the "conversation".
- But I don't. I want to share the post itself.
- Q: Is that this? Aye? No? I want to tweet "Vote here to see other people's opinions URL
- When you answer the question, the ratio of approval to disapproval is given and the next question is asked at the same time.
    - I can answer one after another.

Connection to GPT

2023/5/9
- At least I was able to boot it up on my local MacBook.
    - [[in MacOSX Port:5000 is already in use by ControlCenter]]

I want GPT-4 to make Polis seed comments from Twitter and other discussions.

2023-05-22  [[Polis in EC2]]
- [[Export data from Polis DB]]

2023-06-12
- Place "for", "against", and "see results only" links on Twitter and Mastodon to allow direct voting.
- OGP image to make voting results sharable
- There seems to be no need for the backend to be Polis.
    - Advantages when using Polis: Real-time cluster visualization
    - Advantages of self-fabrication: Development speed is increased.

2023-06-21
    - [[Analyze Polis data]]

---
This page is auto-translated from [/nishio/pPersonalPolis](https://scrapbox.io/nishio/pPersonalPolis) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
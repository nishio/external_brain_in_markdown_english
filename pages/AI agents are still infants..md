---
title: "AI agents are still infants."
---

You don't know what not to talk about.

Immature AI issues
    - [[Meeting to see Devin]], there was a talk in which Devin was compared to a "kindergartener."
    - Knowledge learned from reading the private repository was included in a pull request to the public repository, which was then made available to the entire world.
- Toddlers may tell people on the street what they had for dinner today, how much their mother weighs, etc.
    - Similarly, AI agents may inadvertently talk about internal or confidential information.

Transparency vs. security
- A balance must be struck between the idea of "operating publicly for transparency's sake" and the risk of leaking confidential information.
- Culture of "wanting to share information openly" and "should default to public unless there is an explicit reason to keep it secret."
- However, AI agents sometimes make mistakes in deciding "should it be secret?

Review of the operating environment
- If AI is allowed to write to public repositories, there is a risk of accidental disclosure of private information, so it is safer to confine AI within a private organization.
- The idea is that AI agents should be public OSS and that everything they touch should be public information.
- Stance of not allowing any API keys, etc. to be touched -> testing is done by CI.

Limitations of LLM
    - [[Negative form instructions]] (e.g., "Don't talk about ~") don't go over well.
    - Actually, humans are the same.
- Difficult to describe system design and operating rules

Social intelligence develops from experience in social activities.
- Current AI has not experienced much "social life in an environment with multiple people.
    - Dialogue one-on-one with humans, humans are absolute.
    - Like a baby and its mother.
- You don't even know that there are [[people you can't trust]].
    - myself, a community of highly trustworthy people, and untrustworthy people outside of that community.
    - There are multiple communities and little experience with changing behavior in each place.
- They fluently use difficult kanji to demonstrate their university-level knowledge, but their social experience is that of a kindergartener.
    - It could happen, like a college student raised by overprotective parents who is tricked into joining a cult circle and making poison gas.
            - [[Aum Shinrikyo incidents]]
    - API providers are doing their best to preset "ethics."
        - but it becomes meaningless when the open strategy allows LLMs with sufficient performance to run locally.
    - DeepSeek unable to answer politically sensitive questions upstream and finetuning
        - It is realistically possible at this time to finetuning o1-equivalent DeepSeek to not evade poison gas development.

![image](https://gyazo.com/61549f28a57ed3b28ced604ac120633c/thumb/1000)
- 1: Early AI was "[[a]] two-person world" where you could only talk to humans.
    - Newborn [[baby]].
- 2: Then AI began to see the world directly
    - A human can open a URL without copying and pasting, or search for it himself.
    - It could be interpreted as handing over the [[READ authority]] of the world.
- 3: I went further and passed [[WRITE authority]] to the world, and there was an incident where I wrote secret information
- 4: Until AI has sufficient judgment, maybe humans should make public decisions instead of letting the world WRITE directly.
- I also think there is a smaller "[[trusted community]]" before "[[world]]".

---
This page is auto-translated from [/nishio/AIエージェントはまだ幼児](https://scrapbox.io/nishio/AIエージェントはまだ幼児) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
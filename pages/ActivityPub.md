---
title: "ActivityPub"
---

from [/villagepump/ActivityPub](https://scrapbox.io/villagepump/ActivityPub)
![image](https://gyazo.com/28b76540c1d91aa8dbb74aee0260a0c1/thumb/1000)
[https://github.com/w3c/activitypub](https://github.com/w3c/activitypub)
- W3C Recommendation: [ActivityPub](https://www.w3.org/TR/activitypub/)
- Protocols for interconnecting [[Mastodon]], [[Fedibird]], [[GNU Social]], and other [[Fediverse]]-like Twitter

<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>
- In the old days of RSS, updates were put in the sender's outbox and retrieved by the reader's RSS reader, and then came the age of Slack notifications, where the sender's service would POST to Slack's API, but let's not think of the queue between the two as tightly coupled to either service, right? But let's not think of the queue in between as tightly coupled to either service, right?
- ![image](https://gyazo.com/ec8d7baedec8f153cf4f0c6ac62fb54a/thumb/1000)
- ![image](https://gyazo.com/5992102a9b61924dfcd793209563dc8d/thumb/1000)


<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>
- Seems like a commentary on minimal implementation by someone in the know.
    - [#59 Introduction to Fediverse - Let's build a decentralized SNS server! (1) | gihyo.jp](https://gihyo.jp/dev/serial/01/perl-hackers-hub/005901)
    - [[HTTP Signatures]]
        - [[remote follow-up]]
        - Conversion from user name to actor information URL
        - Interaction by [[Web Host Metadata]] and [[WebFinger]] conventionally
    - Have a local follower list and POST to each follower's inbox
        - So inbox can be another service, I see.
        - Instead of that flexibility, there is a cost based on "frequency of posts x number of followers".

---
This page is auto-translated from [/nishio/ActivityPub](https://scrapbox.io/nishio/ActivityPub) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "Why AT Protocol does not use ActivityPub"
---

2023-07-29
- Why is that? I asked GPT4, and the answer made sense to me, so I made a note of it.

<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>There are several reasons why [[AT Protocol]] does not use [[ActivityPub]]:
- Design Philosophy:
    - ActivityPub is a protocol for creating, updating, and deleting content on a distributed server network. It primarily handles the interaction between servers, but does not address how users and applications should manage their data and interact with this network.
    - The design of the AT protocol, on the other hand, includes more granular [[data ownership]] and controls over handling, linking, and interoperation, with an emphasis on user control and privacy.

- Different data models: The AT protocol and ActivityPub use different data models.
    - The AT protocol uses a model in which data is stored in a signed data repository and can be synchronized across different servers. It also provides a schema network called Lexicon to unify data across different servers.
        - Indeed. There's no room for development when the schema is fixed.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
                - I'll have to take a closer look at [[AT Protocol's Lexicon]].
    - ActivityPub, on the other hand, uses an inbox/outbox model where data is distributed between servers and does not provide a global schema.

- Differences in collaboration:
    - ActivityPub has a single collaboration model where servers interact as peers and communicate using the ActivityPub protocol.
    - The AT protocol, on the other hand, uses a more complex federated model that uses Personal Data Servers (PDS) and Big Graph Services (BGS) to process user data and events, respectively.
    - This distinction aims to achieve scale and user choice.

- Account Portability: The AT protocol emphasizes account portability and uses a system of DIDs and signed data repositories to allow users to migrate data to a new personal data server without server intervention. This is not a built-in feature of ActivityPub.
    - What is DID?[[distributed ID]] のこと<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>

- Choice of Algorithm: The AT protocol is designed to give users the freedom to choose their own algorithm for content discovery and retrieval. This is not a feature provided by ActivityPub.

Overall, it is not that the AT protocol does not use ActivityPub, but the architecture of the protocol is different because the AT protocol was designed with different goals and philosophies. tool, but the designers of the AT protocol clearly had a different vision of what they wanted to achieve.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Why AT Protocol doesn't use ActivityPub?
<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>
The Authenticated Transfer Protocol (AT Protocol) does not use ActivityPub for a few reasons:

Design Philosophy: ActivityPub operates on a fundamentally different philosophy than the AT Protocol. ActivityPub is a protocol for creating, updating and deleting content on a distributed server-to-server network. It mainly handles the server to server interactions, but does not deal with how users and applications manage their data or how they should interact with this network. On the other hand, AT Protocol's design involves more granular control over data ownership and handling, federation, and interoperation with a larger focus on user control and privacy.

Different data model: AT Protocol and ActivityPub use different data models. AT Protocol uses a model where data is kept in signed data repositories that can be synced across different servers and provides a schema network called Lexicon to unify data across different servers. On the other hand, ActivityPub uses a model where data is distributed across servers using an inbox/outbox model and does not provide a global schema.

Different approaches to federation: ActivityPub has a single federation model where servers are peers and communicate using the ActivityPub protocol. AT Protocol uses a more complex federation model with Personal Data Servers (PDS) and Big Graph Services (BGS) to handle user data and events respectively. This distinction is meant to achieve scale and user choice.

Account portability: AT Protocol emphasizes account portability, allowing users to migrate their data to a new Personal Data Server without the server's involvement, using a system of DIDs and signed data repositories. This isn't a built-in feature of ActivityPub.

Algorithmic choice: AT Protocol is designed to allow users to choose their own algorithms for content discovery and search, which is not a feature provided by ActivityPub.

Overall, it's not so much that AT Protocol doesn't use ActivityPub; rather, AT Protocol was designed with different goals and philosophies in mind, leading to a different protocol architecture. ActivityPub is a wonderful tool for certain kinds of decentralized applications, but the designers of AT Protocol clearly had a different vision for what they wanted to achieve.

---
This page is auto-translated from [/nishio/AT ProtocolがActivityPubを使用しない理由](https://scrapbox.io/nishio/AT ProtocolがActivityPubを使用しない理由) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "AT Protocol"
---

[Protocol Overview | AT Protocol](https://atproto.com/guides/overview)

- [[AT Protocol's Lexicon]]

[Identity | AT Protocol](https://atproto.com/guides/identity)
In the AT protocol, each user has a domain name handle such as alice.host.com or alice.com and a consistent "[[DID]]" ([[distributed ID]]) that allows migration between hosts.
- Identity management: users create stable global IDs and securely distribute public keys; IDs are portable and keys can be rotated.
- Identifiers: Two types of identifiers are used: handles and DIDs. Handles serve as DNS names, and DIDs serve as secure and stable identifiers.
- Handle resolution: The atproto handle resolves to a DID that resolves to a DID document containing the user's signing public key and hosting service.
![image](https://gyazo.com/a21869f3aa6d3ac4b9394fc64c5d5f3f/thumb/1000)
- [[Hosting Provider]]

---
This page is auto-translated from [/nishio/AT Protocol](https://scrapbox.io/nishio/AT Protocol) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
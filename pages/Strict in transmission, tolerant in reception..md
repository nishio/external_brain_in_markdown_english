---
title: "Strict in transmission, tolerant in reception."
---

    - [[Postel's law]]
- Postel's Robustness Principle
- > Be liberal in what you accept, and conservative in what you send
    - RFC 1123 - Requirements for Internet Hosts - Application and Support
    - [http://tools.ietf.org/html/rfc1123#page-7](http://tools.ietf.org/html/rfc1123#page-7)
- > In general, an implementation must be conservative in its sending behavior, and liberal in its receiving behavior.
    - RFC 791 - Internet Protocol
    - [https://tools.ietf.org/html/rfc791#section-3.2](https://tools.ietf.org/html/rfc791#section-3.2)
- > TCP implementations will follow a general principle of robustness: be conservative in what you do, be liberal in what you accept from others.
    - RFC 793 - Transmission Control Protocol
    - [http://tools.ietf.org/html/rfc793#section-2.10](http://tools.ietf.org/html/rfc793#section-2.10)
- #communication #protocol

    - [[network externality]]
- If "strictly according to standards for both transmission and reception" were required from the start, the barrier to entry into the network would be raised.
- Therefore, the major policy is that "in transmission and reception, it is more important that the transmission be strict" and "the receiver should accept things that are slightly out of the standard to the extent that they are acceptable.
- This led to a "[[de facto standard]]" (de facto standard), which was not a written standard but was tolerated by many players.
- Some people refer to this as a failure of Postel's law, but the author believes that [[de facto standard]] is naturally created when multiple people form a network.
    - It is a dubious idea to assume that there was a problem in decision making prior to the success of the network because of the success and the large network and the complexity within that network. [[hindsight]]?
    - IP and TCP were very successful when Postel's Law was introduced. It is not observable whether they would not have been successful if they had not been introduced.
    - Postel's law had the effect of increasing the probability of success.

---
This page is auto-translated from [/nishio/送信は厳密に、受信は寛容に](https://scrapbox.io/nishio/送信は厳密に、受信は寛容に) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "Clubhouse"
---

It's a confusing series of stories broken up into multiple walls, so I've summarized them once.

- Can the speakers overlap each other in a chorus -> not overlap well, weird [src [https://www.facebook.com/nishiohirokazu/posts/10223981308457088?comment_id=10223983418149829](https://www.facebook.com/nishiohirokazu/posts/10223981308457088?comment_id=10223983418149829) ]
    - Audience member who heard it: "It sounded like you got it right."
    - There was about 1.5 seconds of silence at the timing of the elevation from audience to speaker."
    - (incorrect guess) My guess is that the speakers have a P2P connection to each other and are mixing locally. I think the audience is receiving the delivery of the server-side mixing from the server.
        - It was weird when the speakers tried to sing in chorus with each other, but the audience heard it decently, I guess that's what I mean.
        - I couldn't think of a way to verify this sort of thing in the field, but using time reports would be a good idea.
- I got the results of the packet capture.
    - > The clubhouse server is probably located in Tokyo and does not seem to be P2P while the speaker is participating. Here is Kengo Nakajima's log [src](https://facebook.com/ohkubo.kohei/posts/10158086651341476)
:

```
Only two places to send it to
107.155.29.138 4005 This is over 90%.
164.52.32.58 8913 Sometimes this mixes.
...
```

    - The possibility of P2P has been clearly ruled out by the fact that there is almost only one destination for communication.
        - ![image](https://gyazo.com/ed9d04fab21a5c921a6c379f4086531f/thumb/1000)
        - I guess this is it.
        - > Kengo Nakajima: like 50 80 byte packets per second, much different from zoom and others [src [https://www.facebook.com/ohkubo.kohei/posts/10158086651341476?comment_id=](https://www.facebook.com/ohkubo.kohei/posts/10158086651341476?comment_id=) 10158086740376476]
        - You mean the red line is a proprietary UDP-based protocol?
            - The small latency ensures that the servers are located in Japan, leaving the money to the major countries? Cities? The server itself may only forward UDP packets. The server itself may only forward UDP packets. [src](https://www.facebook.com/kuchii.jun/posts/4194099850641216?comment_id=4194328553951679&reply_comment_id=4194340363950498)
                - Oh, and even if it's not P2P between speakers, I'm not denying anything about "the audience is receiving the stream after it's been mixed by the server with a slight delay", so I guess that's true there!
    - > Tatsuya Takahashi: I checked the IP and it seems to be an IP owned by a service called Zenlayer. I think it's an access point in Tokyo. [src](https://www.facebook.com/ohkubo.kohei/posts/10158086651341476?comment_id=10158086855531476)
        - [Zenlayer for ultra-fast data processing in the "edge cloud" - TECHBLITZ [https://techblitz.com/zenlayer/?fbclid=IwAR2yvELVexps81wfsEWoN_u_](https://techblitz.com/zenlayer/?fbclid=IwAR2yvELVexps81wfsEWoN_u_) HrGciqezxHYcUtFu7cFEIiA0eTaRjqXAQ1Q]
            - Ha, I see. You're building an edge server that throws back UDP packets at high speed with this [src](https://www.facebook.com/nishiohirokazu/posts/10223986141217904).
            - The one written in the small box in the above figure is called Zenlayer.

Nicely illustrated
- [https://www.facebook.com/kuchii.jun/posts/4194099850641216](https://www.facebook.com/kuchii.jun/posts/4194099850641216)

More Detailed Packet Capture Explanation
- [https://gist.github.com/kengonakajima/31cb28404f4b96199fb9a84ea99c44f2](https://gist.github.com/kengonakajima/31cb28404f4b96199fb9a84ea99c44f2)

Inference from DNS packets
- [https://zenn.dev/voluntas/scraps/9403b803320d6f](https://zenn.dev/voluntas/scraps/9403b803320d6f)
- Same in network structure
- Opinion that the server may not be doing speech synthesis.
- > I would like to use Clubhouse, which is based on E2EE and has a whiteboard.
    - Oh, that's what I want too lol.

---
This page is auto-translated from [/nishio/Clubhouse](https://scrapbox.io/nishio/Clubhouse) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
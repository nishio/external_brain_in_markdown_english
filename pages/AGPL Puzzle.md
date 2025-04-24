---
title: "AGPL Puzzle"
---

I was discussing licensing at some point and realized that although it's not the actual event, with a little twist I could come up with an interesting set of questions (and I was wrong).

context setting
- Mr. A intends to provide a web service for a limited period of time and to release the source code after the service is finished.
- As of t1, AGPL's library X was used to provide web services ver. 1.
- He then realized that the MIT-licensed library Y could achieve the same objective as X,
- Replaced by Web Service ver. 2 using library Y as of t2.
- It is currently at t3 at the time of the end of the service. I am about to release the source code. Is it required to be published in AGPL at this time?

Mr. B:.
- Shouldn't it have been published in AGPL at t1 in the first place?
Mr. C:.
- No, providing the source code after a user requests it is sufficient to satisfy the terms of the license.
- So, as for ver.1, it is OK to terminate the service without any source code request.
- And as for ver.2, it is not using the AGPL license, so there will be no need to make it AGPL in future releases.
Mr. B:.
- The code of ver.1 must continue to be released even after the service is terminated as of t3.

question
- Explain which opinion is correct or neither is correct, with reasons.

---
This page is auto-translated from [/nishio/AGPLパズル](https://scrapbox.io/nishio/AGPLパズル) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
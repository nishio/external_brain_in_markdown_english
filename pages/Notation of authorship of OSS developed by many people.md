---
title: "Notation of authorship of OSS developed by many people"
---

> I'm not sure if the MIT or BSD license of the OSS license can be used freely as long as the author is indicated, but if it is applied to a program developed by a large number of people, should the copyright be indicated for all the people or just the ones in the license file? [mhiramat](https://twitter.com/mhiramat/status/1035873905959784449)
This is an interesting topic, so I'll try to write down my understanding of it.

First of all, more than 150 countries, including Japan, have adopted the "no-formality principle," under which copyright arises as soon as a work is created. So "whose name after (c)" is not a procedure for determining authorship. see [[Berne Convention]].

The license is also not a procedure for determining who the author is, since it is merely a statement of "the author grants use to others, under what conditions.

In the case of a program jointly created by several persons, where the contributions of each person cannot be separated and used individually (joint work, [Article 2(1)(12) of the Copyright Act, [https://nishio.github.io/better_egov/chosakukenhou.html#2.1.12](https://nishio.github.io/better_egov/chosakukenhou.html#2.1.12)), ### the moral rights of the author cannot be exercised without the agreement of all the members
 ([Article 64(1)](https://nishio.github.io/better_egov/chosakukenhou.html#2.1.12)) and ### the shared copyright cannot be exercised either
 ([Article 65(2) [https://nishio.github.io/better_egov/chosakukenhou.html#2.1.12.](https://nishio.github.io/better_egov/chosakukenhou.html#2.1.12.) moral rights cannot be exercised without agreement] ([Article 64(1)](https://nishio.github.io/better_egov/chosakukenhou.html#64)) and ### shared copyright cannot be exercised
 ([Article 65(2) [https://nishio.](https://nishio.) github.io/better_egov/chosakukenhou.html#65.2])
- To put it more gently, "If something is made by everyone, everyone should agree on how to use it and decide together.
- Therefore, if Mr. A decides on a license and grants a license to use program X, which was jointly developed by Mr. A and Mr. B, without obtaining the agreement of Mr. B, Mr. A simply infringes the copyright.
    - Whether the license is something like "This software is under the MIT license, and you can use it freely if you put 'Program X Development Group' as the author" or not is completely irrelevant.
- On the other hand, it is OK to write "This software was created by Mr. A alone" as long as it can be agreed.

When there are many authors, the cost of "getting everyone to agree" when trying to change a license becomes very high, so move to a system where decisions can be made by a small number of people before that happens.
- As a concrete example, a mechanism called Sign-off is often used
- A mechanism to make it clear that the authors have agreed on various matters in advance.
- For example.
    - Donate copyrights to the project
    - I will not exercise my moral rights.
    - Mr. A agrees to exercise his moral rights on behalf of the author ([Article 64(3)](https://nishio.github.io/better_egov/chosakukenhou.html#64.3))
- Linux Example
    - [https://developercertificate.org/](https://developercertificate.org/)
        - Surprisingly, there's no mention of moral rights.
        - Well, if I insisted on letting them exercise their personal rights, Linus would probably give me a foul mouth...

---
This page is auto-translated from [/nishio/多人数で開発するOSSの著作者表記](https://scrapbox.io/nishio/多人数で開発するOSSの著作者表記) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
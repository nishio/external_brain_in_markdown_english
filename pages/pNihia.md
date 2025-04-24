---
title: "pNihia"
---

2024-05-05
- Create GPTs for assistants to read this Scrapbox
    - [[⿻Plurality Assistant]] was useful.
- Server side is in private repos: `nishio/vecsearch-service`.
- I got 503 because I take uid as a required param, I made it required on the OpenAPI Spec side, but I can fix the server side.

Icon Creation
![image](https://gyazo.com/88e13329336c6e03b4d9c8aa651f6415/thumb/1000)
Why you thought this icon was a good idea is a mystery.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Explain "Yasukazu Nishio."

<img src='https://scrapbox.io/api/pages/nishio-en/pNihia/icon' alt='pNihia.icon' height="19.5"/>Yasukazu Nishio is a researcher with a multifaceted perspective and a flexible mindset, particularly in his deep consideration of intellectual labor and productivity, values that cannot be replaced by AI. He researches ways to help individuals and teams be more productive, and is involved in developing software that facilitates smooth communication. Nishio's research focuses on how the act of working creates customer value, rather than just earning compensation.

He also participates in the Young Scientists' Group of Information Science and is pursuing research on intellectual productivity at Cybozu Labs, where he also holds a position as a specified associate professor at the Tokyo Institute of Technology. Nishio's book "The Intellectual Productivity of Engineers" has also received high praise (from ` [🤖🔁Yasukazu Nishio] `).

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Explain the philosophy of Yasukazu Nishio.

<img src='https://scrapbox.io/api/pages/nishio-en/pNihia/icon' alt='pNihia.icon' height="19.5"/>Yasukazu Nishio's philosophy focuses primarily on
- Multiple perspectives and flexible thinking:
    - Nishio recognizes the importance of looking at issues from different angles. He studies intellectual labor and productivity and contemplates the value of humans not being replaced by AI. His research and practice explore how individuals and teams can become more productive.
- Facilitation of communication:
    - Nishio is involved in the development of software that facilitates communication and aims to enable people to communicate smoothly by providing a "place" to do so.
- The Nature of Work:
    - Mr. Nishio emphasizes that working is not just about getting paid, but also about creating customer value. In his view, it is important to create value through work.
These ideas are reflected in the diverse projects in which Nishio is involved and in his writings. His ideas contribute to intellectual productivity that responds to the flexibility and diversity required in today's society (from ` [🤖🔁Yasukazu Nishio] `).


Well, since [[Done is better than perfect]], let's release it as it is for now (Ver. 1.0).
[ChatGPT - NISHIO Hirokazu's Assistant](https://chatgpt.com/g/g-V6olZSQJI-nishio-hirokazu-s-assistant)


Ver. 1.1 [[Technology Supporting Coding]] and [[The Intellectual Production of Engineers]] loaded on Knowledge

Let's use this as a hub to rebuild the various projects we've been working on.

Ver1.2 released
> [nishio](https://twitter.com/nishio/status/1787087217095287103) I sometimes get errors when searching, GPTs are hard to debug.
> [nishio](https://twitter.com/nishio/status/1787105265944535222) There's a user ID entry in the API, but GPT doesn't know anything about it, and it's giving me an error saying "there's no such user" because I put in an appropriate User ID. I was getting an error saying "there is no such user".
>  I fixed that, but I still get an error sometimes, and the server side is 200, so I think it's probably over the response size.

> [nishio](https://twitter.com/nishio/status/1787108456077672802) Ah, I see, the Plurality Assistant is an experimental mix of 100token and 500token, and this is the pre-experimental implementation of that. I guess all the hits are 500token because this is a pre-experimental implementation.

> [nishio](https://twitter.com/nishio/status/1787111091715416413) For now, I've created a new API for GPT that returns 1/5 of the number of items in a response and changed to call that API, so I think the number of errors has decreased dramatically. I think it has reduced the number of errors dramatically.
Ver.1.3

Ver.1.4
- Changed to return compact results, discarding data not needed for GPT decisions
- Don't take chunks from the same page.
> [nishio](https://twitter.com/nishio/status/1787117492026171718) Various improvements.
>  ![image](https://pbs.twimg.com/media/GM0d4Mhb0AA-0Ph?format=jpg&name=medium#.png)

![image](https://gyazo.com/d07787600db724125538c48f95fc6acb/thumb/1000)

2024-05-07
Ver1.5 Name change (put Nihia in the name)
Ver1.7 Prompt improvement


---
This page is auto-translated from [/nishio/pNihia](https://scrapbox.io/nishio/pNihia) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
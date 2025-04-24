---
title: "Docker Hub"
---

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I'm currently using [[Docker Desktop]] on my Mac and can docker pull without any concern, but when I do the same thing in my Ubuntu environment, I'm stuck with the unauthorized pull rate limit. What should I do?

<img src='https://scrapbox.io/api/pages/nishio-en/o3-mini-high/icon' alt='o3-mini-high.icon' height="19.5"/>Docker Hub has different pull limits for authenticated and unauthenticated users: Docker Desktop on Mac uses authentication information internally, so it is difficult to reach the rate limit, but on Ubuntu, it may be unauthenticated. As a workaround, create a Docker Hub account and run the following command on Ubuntu to authenticate.
`$ docker login`
This will result in an authenticated status and reduce pull restrictions. In addition, you may want to consider a paid plan if needed.
---
This page is auto-translated from [/nishio/Docker Hub](https://scrapbox.io/nishio/Docker Hub) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
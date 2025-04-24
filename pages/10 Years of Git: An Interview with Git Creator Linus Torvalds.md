---
title: "10 Years of Git: An Interview with Git Creator Linus Torvalds"
---

[10 Years of Git: An Interview with Git Creator Linus Torvalds - Linux Foundation](https://www.linuxfoundation.org/blog/blog/10-years-of-git-an-interview-with-git-creator-linus-torvalds)(2015)
[bookworm: translation of interview with Linus Torvals on git's 10th anniversary](https://cpplover.blogspot.com/2015/04/git10linus-torvals.html)
<img src='https://scrapbox.io/api/pages/nishio-en/o3-mini-high/icon' alt='o3-mini-high.icon' height="19.5"/>
## 1. Explanation of the entire article
.
This article is an interview with [[Linus Torvalds]], the creator of [[Git]], in which he talks about the background of the birth of Git, its design philosophy, and its current operation.
- [[Background]]: At the time, Linux kernel development was using a proprietary tool called [[BitKeeper]], but dissatisfied with its limitations (especially the politics of controlling change permissions), Torvalds created a new distributed source control system (Git) himself He created a new decentralized source control system (Git).
- development history: Git was implemented with basic functionality in a short period of time, and the idea of decentralization, especially "[[having your own repository]]", was important to solve the problems of the traditional centralized system.
- Rating: Torvalds finds Git to be a great fit for Linux kernel development, noting that its flexibility and efficiency have led to its widespread adoption in other projects.

## 2. Citation and explanation of statements regarding "dispersion"
.
Torvalds noted the biggest advantage of decentralized source control as follows

>  "The big thing about distributed source control is that it makes one of the main issues with SCM’s go away – the politics around 'who can make changes.'"
>  (A key feature of a distributed source control system is that it eliminates one of the main problems facing SCM, namely the political issue of authority over who can make changes.)

### Explanation
:.
What this quote shows is that traditional centralized systems were prone to the politics of control over who could make changes to the code, because with Git, each developer has his or her own repository and is free to work without relying on a central approval process, This "politics of authority" is greatly reduced. The result is a smoother, more flexible development flow, which is a major reason why many projects have adopted Git.

---
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
- I think in the end [[the convenience of centralization]] won out and most people ended up using [[GitHub]].
- When I was a student, we had SSH access to the lab machines from the dorms, and we had a [[bare repository]].

---
This page is auto-translated from [/nishio/10 Years of Git: An Interview with Git Creator Linus Torvalds](https://scrapbox.io/nishio/10 Years of Git: An Interview with Git Creator Linus Torvalds) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
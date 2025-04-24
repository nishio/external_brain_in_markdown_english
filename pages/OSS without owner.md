---
title: "OSS without owner"
---

> [dmikurube](https://x.com/dmikurube/status/1480559538529239041) I think the official package registry and pre-built binary distribution may be creating a strange sense of responsibility for OSS. In the old days (when the term "open source" had not yet been defined), it was common for people to collect patches and build their own software, and use it by themselves.
> [dmikurube](https://x.com/dmikurube/status/1480560359522312197) The concept of "[[official]] build" or "official release" and "[[ownership]]" tend to be strongly connected, and when you have (or are made to have) ownership, [[liability]] (feeling) tends to occur. I think that [[liability]] (feeling) tends to occur when you have ownership (or are made to have ownership).
> [dmikurube](https://x.com/dmikurube/status/1480561043168718849) Most programming languages nowadays have official (OSS) package registries and build systems that use them. I wonder if it is actually a road to hell paved with good intentions.
> [dmikurube](https://x.com/dmikurube/status/1480561395750309888) Maybe it was more peaceful for developers in the turbulent world of forks and patches flying all over the place.
> [dmikurube](https://x.com/dmikurube/status/1480561638898290689) i.e. [[semver]] and enemies
> [dmikurube](https://x.com/dmikurube/status/1480563128111087623) The same goes for a central source code repository like GitHub. Even if there is something like GitHub, only /user/repo exists, not /user/repo, and everyone pushes branches around on their own. Instead of specifying a release or version, you can just use a commit hash and use it.
> [dmikurube](https://x.com/dmikurube/status/1480563489035137025) Actually, this one might be closer to Linus' original git view.
> [dmikurube](https://x.com/dmikurube/status/1480564517667225600) I'm talking about the above in the extreme, of course, but there are definitely some bad aspects that the ownership concept has brought about.
> [dmikurube](https://x.com/dmikurube/status/1480570166383878147) Sounds close to the idea you are talking about here
>  >takiuchi: maybe we don't need a dedicated maintainer, but just have the users send patches... or maybe we can merge PRs semi-automatically and the branch with the most patches becomes the main one, like in a blockchain...


from [[how to deal with the tragedy of shared land in OSS#61dc73cdaff09e00007320f7]]
> [nishio](https://x.com/nishio/status/1480480672498466821) The OSS maintainers who were producing scarce goods are destroyed as a result of no one paying for society's common goods because they can be copied and used without payment, It's the so-called "tragedy of the commons". I don't know what to do about it.
- > [takiuchi](https://x.com/takiuchi/status/1480543563494883330) I think it would be better if the user could send patches without a specialized maintainer. semi-automatic merge of PRs and the most patches like blockchain. branch would be the main one, and so on.
- > [takiuchi](https://x.com/takiuchi/status/1480546444398706695) It's not a programmer Way like joining forces to help. I'm trying to figure out how to make it work more lazily and automatically.

Unlike a blockchain, a patch for branch A can be applied directly to branch B.
- Each branch has an AI that looks at modifications in other branches and automatically merges them if it finds them useful for its own purposes.
    - If you are as good as Devin, you can do it as long as you create the mechanism.

>  Linus Original git view
<img src='https://scrapbox.io/api/pages/nishio-en/o3-mini-high/icon' alt='o3-mini-high.icon' height="19.5"/>
When [[Linus Torvalds]] first designed [[Git]], his goal was to create a distributed system in which each developer could freely have his or her own repository and manage state with a unique identifier, the commit hash, rather than relying on a centralized official repository.

Specifically, Linus wanted a system where patches could be freely worked on locally by individual developers and later integrated (merged) as needed, in order to efficiently manage the vast amount of changes in the Linux kernel. This eliminated the heavy responsibility associated with official builds and releases, but rather aimed for a worldview where each individual's commit hash was the true measure of their "version" ([Git - Wikipedia [https://en.wikipedia.org/wiki/](https://en.wikipedia.org/wiki/) Git])

The modern [[GitHub]] mode of operation, where repositories are centralized and official releases are emphasized, differs from this original design philosophy of Linus, leading to the point that it may create an extra sense of ownership and management responsibility for developers.

[[dmikurube]]

---
This page is auto-translated from [/nishio/オーナーのいないOSS](https://scrapbox.io/nishio/オーナーのいないOSS) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
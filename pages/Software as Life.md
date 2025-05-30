---
title: "Software as Life"
---

- I feel that what is important for software as life is not design but fault tolerance and interoperability, the former is chain-of-responsibility and the latter is HTTP and JSON.
- It is humans who have needs, and if they can be met, even locally, then the organism can survive in ecological [niche
- By satisfying the user's needs, it acquires resources from humans to keep moving. In other words, it is the equivalent of obtaining food from the human ecosystem.
- For the time being, the interface with humans will be mainly HTML and JS. Eventually, sensor input will be thrown to the tuple space via HTTP.
- Think of Twitter as an existing tuple space.
- It's also a place of practice.
- Existing software that is doing useful work can be incorporated as an organelle
    - That's how mitochondria were created.
- The reason why code cloning is not good and why code needs to be abstracted is because humans with limited cognitive abilities need to understand it in the first place, and to overcome that cognitive barrier, we first need to figure out how to augment human cognitive abilities, or give up and let natural selection do its thing.
- The problem with code cloning is that fixing a bug in one does not spill over to the other, and the reason why it is so difficult to put it together is because a human being with limited cognitive ability cannot determine if two codes can be made common, and organisms do not make common.
    - As for the common sequences written in two places in the DNA, RNAi can suppress them both together, a kind of commonality.
- Wouldn't organisms be more prone to crossover if they have code clones?
- I'll call both and take the one that worked.
- Values can be written in the global scope of cytoplasm, or they can be enclosed in a small area like lysosomes
- It is not correct that the caller dies when the function argument changes, the caller who did not receive the message should die.
- If a function fails to work correctly, the person who implemented it can be contacted
- If it didn't work correctly, just fall back to the old implementation.
- Just as we can combine weak classifiers to make a high-performance classifier, we need a mechanism to combine weak programmers to make an awesome program.
- Is it troublesome when it returns a non-error but incorrect value? Is the program that loses the majority vote hanged?
- If you can define the distance, choose the correct answer with generalized median, and the furthest one is tied up and hanged.
- Genes and cytoplasm are passed on, but not experience.
- I'd like to have a framework that would copy the data on import, call it, fall back to the previously copied version if an error occurs, and if it works, report what data and which version changed behavior between the two versions.
    - Kouhei Okubo Biologically evolved software will sometimes get sick like a cold, and then get better when left alone. Now it's just a matter of tying the requirement specifications to death properly."

- Programming language design based on the premise that "humans cannot grasp the entire software, nor can they grasp the scope of the impact of the changes they are about to make.
- The two import options now are "copy a specific version at hand" and "refer to a library that someone in the share might rewrite". The latter can follow the latest version but may be broken, the former will not break on its own but will not be the latest version either. Copy and run the latest version on import, and if it fails, fall back to the previous copy sequentially.
- Fundamentally speaking, it is a mistake that only the type of exception handling that propagates upwards and eventually dies became major, reexecutable exceptions are necessary, and the example above can be seen as an example of this being used in a controlled manner.
- The decision to save the costly contents of memory is now made by a human being, but why not save the return value of a function that took more than a minute by default?
- After that, if you explicitly indicate that you don't need the memoization, you can just stop saving it.
- Score your report with the size of your surprise
- The problem with having a lot of forks is that it costs a human to try each one, and if you know it's a fork, you can switch automatically to try it.
- I thought about keeping the process alive and replacing the module... or referring to erlang... but if the time-consuming process is written down in the file system, it's not too costly to restart the process.
- Assuming the source code is maintained in git, I can go back through the history myself and find the appropriate version.

[[2015]] [Facebook](https://www.facebook.com/nishiohirokazu/posts/10205061820081703) [Facebook](https://www.facebook.com/nishiohirokazu/posts/10205067886313355)

---
This page is auto-translated from [/nishio/生命としてのソフトウェア](https://scrapbox.io/nishio/生命としてのソフトウェア) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
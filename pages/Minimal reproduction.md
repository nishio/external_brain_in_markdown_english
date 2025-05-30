---
title: "Minimal reproduction"
---

Sometimes when I'm writing a program and I'm not sure about something, I take the approach of "let's make [[minimum]] [[reproduction]] code".
I don't recall learning this explicitly, and probably acquired it naturally as I watched senior programmers debugging at my side.
It would be good to verbalize what kind of action this is to understand how to solve the problem.

What exactly is the state of that "not sure"?
The program I wrote does not work as expected.
I don't know what to fix in a program that doesn't work as expected

- Cannot [[Binary Search Debugging]]. Cannot [And debug execution.
- If a sequentially executed program behaves differently than expected, a breakpoint can be placed in the middle of the program to ask, "Is the program in the expected state at this time?" to narrow down whether the location of the problem is before or after that point. Situations where this is not possible.

Why can't we do it?
That's because you recognize that it's a "process that can't be split."
In the case of the program I wrote, I can split it up, but it's a "I put X in the external code I trust, and I thought I'd get Y, but I got Z" situation.
- Because they assume, "It's a lumpy process, it can't be broken up."
- One approach at this time is to "read the framework code.
- To reduce the cognitive burden, you're unconsciously abstracting and assuming that it's a lumpy process.
- And while some approaches to reading, often become "so vast, I don't know where to read
- This time, specifically, there's something I don't understand about the TypeScript type system, but you're subconsciously avoiding it because you think it's "hard" to read the relevant code in TypeScript here!
- It's like, "I put X into an external code that I trust, and I thought I'd get Y, but I got Z." In other words, I don't understand the behavior of that external code correctly. I don't grasp what the external code is actually made up of, so it looks like a "big lump of a task," and I am unmotivated by not being able to estimate its size.
    - But the story of creating a minimal reproduction code is a bit different from that.
- Unlike dividing "a lump of external processing" into multiple smaller processes, the process of reducing the size of "input data to be passed to the process" while keeping the lump of processing intact.
- It's attached to the talk about reproducibility when it's not reproducible, but in this case it's "reproducible" and "I want to minimize it."
- Repeatedly say "Let's cut this part because it's not necessary to reproduce the problem" on the assumption that the problem is reproducible.
- "Let's remove this part because it is not necessary to reproduce the problem (experiment) → does the problem continue to reproduce itself? (observation)"
- The entire process is a verification of the hypothesis that "creating a minimal reproduction of the code is useful to solve the problem.
- The assumption that hypotheses must be "created from scratch" in the hypothesis testing process is not appropriate, and there is often a formulaic pattern
- The process of creating a minimal reproduction code is a collection of small hypothesis tests, so for something "unfamiliar," if you say, "It shouldn't be necessary," you can reduce the size of the problem, and if you say, "Don't reproduce," you can understand the gap between your understanding in your brain and the real phenomenon. Either way, you will make progress in solving the problem.
- It is not beneficial to stop at "I'm not sure," so this approach is used to solve the problem.
- This approach can only be used if it is repeatable and can be experimented with repeatedly. For example, in interpersonal communication, if the other person has unexpected and problematic behavior in response to our input, repeated problematic input is not appropriate problem solving
- context
    - [https://www.facebook.com/1129148772/posts/10220683212006738?d=n&sfns=mo](https://www.facebook.com/1129148772/posts/10220683212006738?d=n&sfns=mo)
    - Notes at this time
        - Replaced some implementations with any in an attempt to minimize the problem, but it creates its own problems
        - I found that the presence or absence of REVERSE, which worked fine on its own, affected the results.
        - I mean, where I thought, "Well, this place has been verified and there's no problem here," there's a problem.
        - Elements by themselves are not problematic, but in combination they cause problems
    - Perhaps the timing of the problem is different. At the time of creating an instance of a type, if the given type argument is a literal type, it can be handled without falling into an infinite loop, but for a general type, you don't know "it is a type when it will end sometime

[Engineer Shigeo Mitsunari's "The Art of Tracking Down Bugs" | Cybozu Style](https://cybozushiki.cybozu.co.jp/articles/m000349.html)

---
This page is auto-translated from [/nishio/最小限の再現](https://scrapbox.io/nishio/最小限の再現) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
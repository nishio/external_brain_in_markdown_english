---
title: "The process of acquiring technical skills in the age of AI"
---

Is sutra copying still useful in the age of AI?" Tentative solution to the question "Is Shakyo useful in the age of AI?

![image](https://gyazo.com/85dceeea9364a7e439a85edfde4349b0/thumb/1000)
- When learning a new programming language, the first step is to follow the tutorial or manual and observe the results.
- And beyond that, they will encounter difficult problems, which will take time to overcome.
- Even in the AI era, this remains basically the same. The similarity of the arrows in the figure expresses this.
- The difference is that the target of that sutra changes from "a tutorial written for a large audience" to "a procedure generated for you by an AI" and the author of that procedure answers your questions.
    - [[AI generates procedures]].
    - Mainly the latter effect makes it easier to overcome somewhat smaller mountains.
        - ![image](https://gyazo.com/c79edaf595fb233955f32d2e7c1d87c8/thumb/1000)
            - This part
    - This means that learners assisted by AI in the AI age will go farther and hit bigger walls in the same amount of time


## Making ver.1
> [nishio](https://x.com/nishio/status/1900407051601473536) "I don't know anything about Azure"
>  "AI helped me understand Azure! I'm getting set up!"
>  "Unexplained phenomenon ......I don't know anything about Azure ......" ← here and now

After following the AI-generated instructions to build an Azure environment (by a nearly inexperienced amateur), I was able to do it smoothly until the middle of the process, and finally it behaved in a way that I did not understand and was not completed. w

Maybe this is the same thing you experience when you program in AI without knowing how to program.

When the system grows too large, it doesn't understand this and can't handle trouble. However, the speed at which we reach this "limit" is accelerated by AI, and although we get stuck in a shorter time than before, the results of progress made by the time we get stuck are greater than before.

I think the next step is to review these "results to the point of dead end" and take out the useful components and reuse them, so that we are on a better path than we were the first time around.

Specific examples of useful parts: I did a docker build on my MacBook and pushed to Azure and got a confusing error because the CPU architecture is different, the explanation is simply written assuming the same architecture, so I need to reread it or get the same build environment.

A little bit of verbalization has been achieved. Even if AI comes, the "sutra copying" work of following the text in an unobtrusive manner will not disappear, but the object of that copying will change from "a tutorial written for a large audience" to "a procedure manual generated for me by the AI.

teramotodaiki
- I was excited to think this was going to be a dark story about Azure, but it was a Docker thing.
- I can do rather anything with Azure CLI, so I think I can baton over to Cline if I work up to the point of logging in to the CLI.
    - nishio I can do it, but when I put az in the auto approve list, it started doing things I didn't understand what it was doing at the speed of explosion, so I stopped. w

nishio
I can't verbalize the darkness of Azure because I haven't gone through it yet...
- At any rate, it turns out that the Key Vault reference is not being resolved and is passing as a string to the environment variable.
    - [[Key Vault and RBAC]]

I'll add the example of the "small mountain can be quickly overcome by AI" person, because it's hard to understand.
- ![image](https://gyazo.com/c79edaf595fb233955f32d2e7c1d87c8/thumb/1000)
    - This part

next:  [[The process of understanding Azure for the Azure layman]]

---
This page is auto-translated from [/nishio/AI時代の技術力獲得プロセス](https://scrapbox.io/nishio/AI時代の技術力獲得プロセス) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
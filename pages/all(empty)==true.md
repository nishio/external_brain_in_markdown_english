---
title: "all(empty)==true"
---

> [@fumieval](https://twitter.com/fumieval/status/1663161595009314819?s=20): When defining a function that "returns true if all elements of the array satisfy the condition", does it return false if you pass an empty array or True" is one of the boundaries between a good programmer and a bad programmer.
> [@fumieval](https://twitter.com/fumieval/status/1663322995744718848?s=20): In the process of "put all attachments of an email in the inbox if they are safe", what about emails without attachments? It is easy to imagine the answer naturally if we think about what we should do

> [@kumagi](https://twitter.com/kumagi/status/1663468951677075456?s=20): There is a gulf deeper than the ocean between "this is mathematically natural, so this is what we should do" and "I've taken the liberty of thinking that the requirements of this project are in line with the requirements of mathematics, so we should do this. There is a gulf deeper than the ocean between "this should be done because it is mathematically natural" and "I think the requirements of this project are in line with the requirements of mathematics, so we should call anyone who disagrees with the requirements of mathematics as having no sense", but there are people who cannot see it.

> [@IgnorantCoder](https://twitter.com/IgnorantCoder/status/1663571120354897920?s=20): I'm scared of a lot of people saying it depends on the requirements, like whether 1+1 is 2 depends on the context. I'm afraid they'll never implement it...

> [@chokudai](https://twitter.com/chokudai/status/1663702986160308225?s=20): ・True is the only logical choice. false people need to study logic.
>  I don't want it to be dependent on the situation, as it is not good to increase the effort to refer to the document on items that can be determined by > logic.
> / In many environments, it is better not to assume that "everyone can think logically", so documentation and comments should be taken care of

> [@Cryolite](https://twitter.com/Cryolite/status/1663439852409622534?s=20): You are the author of a programming language. If you pass an empty array to the "function all, which returns true if and only if all elements of the array satisfy the condition" and "function any, which returns true if and only if some elements of the array satisfy the condition" in the language's standard library, you implement the following behavior:
> ![image](https://gyazo.com/a507fe50693b99f4d99fcad94968ed94/thumb/1000)
- > [@GarterBlue2303](https://twitter.com/GarterBlue2303/status/1663501743882371072?s=20): in @Cryolite kotlin's all documentation [wikipedia.org/wiki/Vacuous_truth Vacuous truth - Wikipedia](https://en.).
- > [@nishio](https://twitter.com/nishio/status/1663526973686321152): try to reduce misunderstandings by writing the definition of any as "one or more elements of an array are ~"

> [@3156](https://twitter.com/3156/status/1663747595905413121?s=20): I wonder if the fierce people who are saying true is the only choice in this discussion and anything else is disqualifying are usually only implementing the standard library?
> I thought most programmers work at the application level?
> If the customer's request is ambiguous, you would work out the details before implementation.
> Is the subject of "programmer" too big?

> [@kis](https://twitter.com/kis/status/1663749216706101248?s=20): if it's a customer request, that would be about the business logic implementation, not "true if the array meets all the conditions" or "if the cart meets the shipping conditions. I think it would be about something like "does it meet the requirements?".
> [@kis](https://twitter.com/kis/status/1663749950235373568?s=20): Also, in the end, when creating application logic, it tends to be a more robust process if the business rules are based on mathematical principles, so a sense of body I think it is better to have it as a physical feeling.

> [@ito_yusaku](https://twitter.com/ito_yusaku/status/1663714609700941824?s=20): I feel like the factor that divides the opinions in this discussion, is how the person in question was born and raised as a programmer. I think the factor that divides this discussion is the environment in which the programmer was born and raised. People with formal programming education probably choose true. (additional fuel dropped)

> [@kazuho](https://twitter.com/kazuho/status/1663556196522164227?s=20): You know, it's interesting that there is no argument like "the name of the function can be all or something like that, but the definition should say "a function that returns whether or not any element in the array does not satisfy the condition". It was interesting that there was no claim like "the name of the function should be all or something like that, but the definition should say "a function that returns whether or not any element in the array does not satisfy the condition. It's a balance between correctness and not creating misunderstandings.

> [@chokudai](https://twitter.com/chokudai/status/1663911825514086402): The reason I strongly insist that you return true is because I believe that doing something that goes against logic in a place where logic can be understood has a significant impact on the overall delay in development speed and seriously reduces Japan's development capability. I'm sorry if you don't agree with me, but I'm not good enough at explaining myself.
- > [@nishio](https://twitter.com/nishio/status/1663918316547723268?s=20): To explain this with another metaphor, "I think it's a good idea to put an automatic 10% sales tax on the sum implementation, because it's used to total the price of the item!" I think it's a good idea!" to someone who says "No, it's not a good idea! to someone who says, "It's not a good idea!
    - > [@chokudai](https://twitter.com/chokudai/status/1663918490766409732?s=20): you definitely explain it better this way!
    - > [@methane](https://twitter.com/methane/status/1663922489116721153?s=20): great clarification.
    - > I think you say "it depends on the requirement" because you assume that a requirement that is clearly a generic process must be blurring out some specific business requirement instead of the actual requirement.
    - > It's a question of reading what is written as it is written.
    - > [@inuro](https://twitter.com/inuro/status/1663931662571548673?s=20): I see this kind of design where the separation of responsibilities is vague, often unfortunately.

> [@yururi0818](https://twitter.com/yururi0818/status/1664063094535131136?s=20): personally I think it's a good metaphor,
> There are so many systems in the world where sums are implemented in this way,
> I feel that the more you speak in parables, the more diffuse the discussion becomes.
- > [@nishio](https://twitter.com/nishio/status/1664082500430487553?s=20): it doesn't spread. For example, if there are many "buggy programs" in the world, it doesn't mean that the buggy ones are right.
- > This is a variant of this.
- >   [[Deteriorated copies spread]]
        - [[Just because there are a lot of buggy programs out there doesn't make being buggy right.]]

---
This page is auto-translated from [/nishio/all(empty)==true](https://scrapbox.io/nishio/all(empty)==true) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
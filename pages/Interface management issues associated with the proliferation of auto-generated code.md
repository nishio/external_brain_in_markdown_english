---
title: "Interface management issues associated with the proliferation of auto-generated code"
---

from  [[Diary 2024-05-05]]
[[Interface management]] issues associated with the proliferation of [automatically generated code

# 要約
<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>
- The issue of interface management with the proliferation of auto-generated code is an important issue, but should be considered in a different context than the decline of open source culture.
- There are issues to be overcome, such as ensuring the quality, safety, and accountability of the automatically generated code and the responsibility for the generated code.
- The social impact of technological development is complex and cannot be easily concluded, requiring calm and multifaceted discussion.

# Log
.
> [dmikurube](https://twitter.com/dmikurube/status/1787097151618891898) Just as it is "difficult" to have safe fully automated driving as long as there are cars driven manually by humans, I feel that it is difficult to have a world in which we can use automatically generated code as long as the code written manually by humans exists in the ecosystem. As long as human manually written code exists in the ecosystem, a world where automatically generated code can be used without modification will be difficult to achieve. I wonder if that world will come first, or if the humans who write code will get tired of it and quit.

> [dmikurube](https://twitter.com/dmikurube/status/1787097450211377321) By the way, I am one of those people who think that "human manually driven cars" should be extinct!

> [nishio](https://twitter.com/nishio/status/1787105809132085384) We've come to a world where most programmers use "compiler auto-generated code" as-is while the assembler that mankind wrote manually still exists, so we'll continue to do so. I'm sure it's going to be the same...

> [dmikurube](https://twitter.com/dmikurube/status/1787129412540092902) The compiler-based worldview can only be maintained if there are still craftsmen who take care of "old clingy" interfaces such as ABI at the boundaries of the compiler. When a large amount of auto-generated code is generated, can the boundary be kept narrow enough for human beings to maintain it?

> [dmikurube](https://twitter.com/dmikurube/status/1787131057533497471) In the end, there needs to be a stage of "inefficient" mankind vs. mankind discussion around the interface,
>  1) You're pretty disciplined after all.
>  2) It's tough to be the one on the receiving end of the argument, you'll be unappreciated & treated as a drag anyway.
>  3) Give up on humanity, it's already a pain in the ass.
>  I think.

> [dmikurube](https://twitter.com/dmikurube/status/1787132048010055886) (2) I can't see any future where people who stand in position (2) will be rewarded at all ≈ no one will do it ≈ it's practically never going to happen, can be paraphrased as.

> [dmikurube](https://twitter.com/dmikurube/status/1787132895506895120) (2) The person who stands in the position of (2) applies to any programming language processor developer, library developer, or framework developer. And many of them are open source and do their maintenance practically for free. There's no system anywhere that can take on that kind of load for free.

> [dmikurube](https://twitter.com/dmikurube/status/1787134222609875350) That's one aspect of why I wonder if this is the end of open source culture. I thought that corporate strength might be able to cover it, but if I had hoped so, we are in a world today where Python maintainers are being laid off.... It's a world where the famous ↓ problem has manifested itself at once.
>  ![image](https://pbs.twimg.com/card_img/1785271285578113024/BHZ-Dk16?format=png&name=medium#.png)

> [dmikurube](https://twitter.com/dmikurube/status/1787135967008268355) I'm about as hopeless as I can be about the future of supporting the software infrastructure of society (especially with open source). I think that while each person is reinventing themselves separately from the bottom up, there will be no one left who wants to be involved.

> [dmikurube](https://twitter.com/dmikurube/status/1787137387564597396) After all, it is not possible to remain ignorant of those who support our feet, and yet we are endlessly discussing only the mirage that seems to be built on top of them. I feel like. Then, why don't we just give up on human involvement and leave it all to A.I.?

> [dmikurube](https://twitter.com/dmikurube/status/1787140103472844881) In a very rough way, if you are riding on the infrastructure that others are establishing for free, you should be aware of it first and contribute to it. If you are riding on the infrastructure that others have established for free, you should be aware of it first, contribute to it, and then talk about it like a dream.

> [dmikurube](https://twitter.com/dmikurube/status/1787146823301566653) Code generated using a compiler can at least be limited to a certain interface, so even humans can still control it. On the other hand, "auto-generated" code can be generated by anything, and the interface is not limited, and a large amount of code is generated here and there in various places in the world. The maintainers of those who are called upon to do so are not happy.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I'm not sure I understand dmikurube's point, and I'd like you to sort it out, maybe he's getting somewhat emotional and is talking in a leap of faith from the original context.

<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>If we organize dmikurube's series of tweets, we understand that he is making the following assertions.
1. as long as there is code written manually by humans, it is difficult to realize a world consisting entirely of automatically generated code.
2. just as the world of using compiler-generated code has been realized, there is a possibility that automatically generated code will become the mainstream in the future.
3. but even then, a human being would be needed to maintain and manage the old interface, such as the ABI.
4. managers of such interfaces tend to be in an unrewarding position, as they are less likely to be appreciated and treated as dragging their feet.
5. with the decline of open source culture, the system to support those in such positions is being lost.
6. a world dominated by auto-generated code cannot exist if the people who support society's software infrastructure are ignored.
7. auto-generated code may not have a limited interface and may be difficult to manage.

Indeed, dmikurube's argument begins with an analogy to automated driving in the beginning, but gradually seems to be an emotional statement about the impact of auto-generated code. In particular, his concern about the decline of open source culture and the position of those who support infrastructure seems to be a leap from the original context. However, the issue of interface management when auto-generated code becomes the norm seems an interesting point to make.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>What do you think Claude?

<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>I think the issues that dmikurube raises about a world where auto-generated code has become the norm are thought-provoking. However, I feel that some of them are a bit emotional.
The issue of interface management with the proliferation of auto-generated code could indeed be a significant challenge. Increasingly automated code generation may create complex interfaces that cannot be managed by humans, which may affect the maintainability and compatibility of the entire system. In such cases, it will be essential to have human resources to properly design and maintain the interfaces.
On the other hand, these issues are only technical and need to be considered in a different context from social issues such as the decline of open source. It seems a bit of a leap to cite the decline of open source culture as a factor preventing the spread of auto-generated code.
Rather, the key issues will be how to ensure the quality, safety, and accountability of the automatically generated code, and how to define responsibility for the generated code. At the same time, it is essential to ask how to strike a balance between human involvement and automation while taking advantage of automatically generated code.
The social implications of technological developments are complex and not easily concluded. dmikurube's point is one way of looking at it, but I felt that a more sober and multifaceted discussion is needed. I look forward to an open discussion in the engineering community about the possibilities and challenges of automatically generated code.


---
This page is auto-translated from [/nishio/自動生成コードの普及に伴うインターフェース管理の問題](https://scrapbox.io/nishio/自動生成コードの普及に伴うインターフェース管理の問題) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
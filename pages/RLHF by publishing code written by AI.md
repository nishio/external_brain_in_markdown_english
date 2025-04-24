---
title: "RLHF by publishing code written by AI"
---

> [rkmt](https://x.com/rkmt/status/1879678695214141889) I wonder if it's okay to publish programs made with Cline on git, soon most of the public code will be machine generated. I'm not sure what will be at the end of mining it. However, it can be said to be [[RLHF]] (Reinforcement Learning with Human Feedback) in a broad sense, since it incorporates the human desire for "the program I want".

> [rkmt](https://x.com/rkmt/status/1879708411975389545) The concern is that, although the code is currently readable to humans because it is learning code written by humans, as soon as it starts learning machine-generated code, it will gradually leave humans behind and become full of code that works well but cannot be deciphered, but is efficient. However, as soon as machine-generated code starts to learn, humans will be left behind, and there will be a lot of code that works well but cannot be deciphered, but is still efficient.
> [rkmt](https://x.com/rkmt/status/1879711003832877492) Code written by humans will be called "natural" 100% organic, etc.


> [nishio](https://x.com/nishio/status/1880068905177346490) My skin feeling is a little different, the experience of having AI write code explanation documentation at this moment is very good, and in the future, with AI's support, the number of documents set with code will increase, and this In the future, AI will produce "code with easy-to-understand explanations" as the loop of AI-assisted documentation increases and becomes easier for AI as well as humans to understand.
>  >rkmt: My concern is that the code is currently readable to humans because it is learning code written by humans, but if it starts learning machine-generated code, it will gradually leave humans behind and become full of code that works well but cannot be deciphered, but is still efficient.
> [nishio](https://x.com/nishio/status/1880069301643931688) Of course we generate "crunchy tuning code that is incomprehensible to humans," but in that case, we will write a document that says, "What is this code intended to do and why is it crunchy?" In that case, we will write a document that says "What is this code intended to do and why is it crunchy?


> [teramotodaiki](https://x.com/teramotodaiki/status/1880099172524912781) I agree completely. o1 and Devin actually make me work, and I can see that they often come up with readable code. They also write comments carefully as a matter of course.
>
>  Rather, I think that stubbornness and ego, like "I can read, so it's ok", is a trait that humans can have, or something akin to authorship. It's more like a habit of code.
> [ukkaripon](https://x.com/ukkaripon/status/1880099928846004630) Isn't that because it is tuned on the assumption that it outputs to humans? If that is no longer necessary, it would be possible to come up with something better, but not known to humans.
> [teramotodaiki](https://x.com/teramotodaiki/status/1880105533832826903) Oh, that's true. It's going to be a lot different in the immediate future than in the future.
> [teramotodaiki](https://x.com/teramotodaiki/status/1880106189566144915) Well, but if we go that far, are we writing a programming language for humans? I even wonder if we are writing a programming language for humans.
> [nishio](https://x.com/nishio/status/1880108064675934545) From the AI's point of view, in a time when it needs to coexist with humans, being easy for humans to understand is naturally valuable, and in an age when humans are no longer needed, there is no need to "go to the trouble of changing something that is difficult for humans to understand. In an age when humans are no longer needed, the text will be left alone because "there is no need to go to the trouble of making it harder to read" except for a few "areas that need to be improved in efficiency even if it is harder for humans to understand.
> [nishio](https://x.com/nishio/status/1880108338962452683) A mere constant-fold "code compression" is only valuable while the context width is small,
>  It no longer "matters" to AI, which has a context range many orders of magnitude greater than humans.

> [teramotodaiki](https://x.com/teramotodaiki/status/1880135353883086911) After thinking deeply about this matter, I came to the conclusion that ultimately, ownership of source code will cease to exist and AGI has already completed a whole forest I have come to the conclusion that the right to use the software will be leased to humans and called "apps" or "services" for convenience!
> [nishio](https://x.com/nishio/status/1880142483910455392) Did you think deeply about it people? ()
> [teramotodaiki](https://x.com/teramotodaiki/status/1880146296587354248) :p

<img src='https://scrapbox.io/api/pages/nishio-en/o1 Pro/icon' alt='o1 Pro.icon' height="19.5"/>
I myself think that for the time being, the trend will be toward more "human readable code + commentary". This is because readability is still important at the stage of human review, modification, and use, and furthermore, comments and documentation are more efficient for AI to learn.

In the long run, it is possible that the code will be highly optimized and auto-generated, and that there will be more parts of the code that are not easily understood by humans. In many cases, however, the benefit of generating code that is easy enough to understand will be greater than sacrificing explanations and readability ([[at least until humans are completely unnecessary]]).

In the end, the ownership and licensing of software and the concept of "writing" code may change, but in the transitional period leading up to that point, I believe that the phase of mutual learning will continue for a long time, in which "AI opens up the code it has written, and humans understand and improve it. I believe that this phase of mutual learning will continue for a long time.

---
This page is auto-translated from [/nishio/AIが書いたコードを公開することでRLHF](https://scrapbox.io/nishio/AIが書いたコードを公開することでRLHF) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
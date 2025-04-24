---
title: "Reactive Programming / Functional Reactive Programming"
---

Rx* is not FRP

[The introduction to Reactive Programming you've been missing · GitHub](https://gist.github.com/staltz/868e7e9bc2a7b8c1f754)
- > [@ReactiveX](https://twitter.com/ReactiveX/status/483625917491970048?s=20&t=qLr-sa2ZRTF-JQsfLa9biA): A nice introduction to Reactive Programming using RxJS from @andrestaltz [https://t.co/breKB68ndK](https://t.co/breKB68ndK) although Rx* is not FRP
- > [@ReactiveX](https://twitter.com/ReactiveX/status/483644526368931842): @andrestaltz @phadej @conal the big difference is the separation between Behaviors and Events. We do have that eg BehaviorSubject/Observable
- [[translated](https://ninjinkun.hatenablog.com/entry/introrxja) The introduction to reactive programming you've been asking for - ninjinkun's diary]
    - [What was reactive programming - Qiita](https://qiita.com/hiruberuto/items/39e4126f470d8b84b291)

[terminology - What is (functional) reactive programming? - Stack Overflow](https://stackoverflow.com/questions/1028250/what-is-functional-reactive-programming?answertab=votes)
- [Q. What is (functional) reactive programming? | POSTD](https://postd.cc/what-is-functional-reactive-programming/)
- I've seen the English version of this, and I see, I can see how this could confuse some people.
    - "datatypes that represent a value 'over time' " = Behavior
    - That's what this is all about, isn't it?
    - Change the cognitive part of what combination of parts describes the world.
    - Maybe someone with some experience in electronic circuit design would understand it better.
        - WIRE is a voltage varying entity
            - Consider this a first class existence.
        - Placing a part is a description of the relationship between its existence
            - Declarative, you might say.
    - It is necessary to describe the world with this kind of cognition "different from the architecture of today's computers" and then put it into a form that can be executed by today's computers.
    - the big difference is the separation between Behaviors and Events
        - You can't confuse the two here.
        - Fundamentally, you don't know what you're doing to make it first class.

[The Essence of FRP](https://begriffs.com/posts/2015-07-22-essence-of-frp.html)

[What was reactive programming - Qiita](https://qiita.com/hiruberuto/items/39e4126f470d8b84b291)


I tried to write an explanation and realized I didn't understand it.
- I realized that I don't know enough about it to explain it, so I'll just take a quick look at it this time.
- Instead of destructively rewriting a single object along a time line,
- Takes an unchangeable (immutable) object, creates a new object and returns it
- Mental model of a message flowing in a stream


---
This page is auto-translated from [/nishio/Reactive Programming / Functional Reactive Programming](https://scrapbox.io/nishio/Reactive Programming / Functional Reactive Programming) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
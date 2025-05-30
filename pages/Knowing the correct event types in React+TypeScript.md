---
title: "Knowing the correct event types in React+TypeScript"
---

It is important to put the correct type of event, but I tend to put it on in a messy way because I don't know what the correct type is (my mistake in the past).
You don't have to remember the correct event type or anything, just "make it void or some other type that is obviously incorrect, and TypeScript will tell you the correct answer and you can use it".
![image](https://gyazo.com/b69ada33003d39d9ef432c8a51b40987/thumb/1000)

context
> [qnighy](https://twitter.com/qnighy/status/1416745698918244356) e.target often used incorrectly issue
>  ![image](https://gyazo.com/afa6e2820782a7cef3293d9afb83dc32/thumb/1000)

[nishio](https://twitter.com/nishio/status/1416805618686435328) This reminds me of recently when I passed e directly to foo and then looked at the completion candidates and thought "hmmm, currentTarget, I don't know this kid, but it has the expected type, so I'll take it, I'll look it up later.
ts

```typescript
const onDragStart = (event: React.DragEvent<HTMLDivElement>) => {
    event.target.clientHeight // Huh? No?
    event.currentTarget // this one?
```

the "like this" trend

type information
`event.target: EventTarget`
`event.currentTarget: EventTarget & HTMLDivElement`

MDN
- [Event.currentTarget](https://developer.mozilla.org/ja/docs/Web/API/Event/currentTarget)
    - > Events traverse the DOM and identify the current target of the event. It always refers to the element to which the event handler is attached, as opposed to event.target, which identifies the element on which the event occurred.
- [Event.target](https://developer.mozilla.org/ja/docs/Web/API/Event/target)
    - > A reference to the object that fired the event. Unlike event.currentTarget when the event handler is called during the bubbling or capture phase.

Ah, I see, so target can be any of the child elements, but currentTarget is the DOM element with the event handler. So the `event: React.DragEvent<HTMLDivElement>` type argument that says "This is an `HTMLDivElement`" does not affect target, but currentTarget does.

This means that I was unknowingly protected from pitfalls by correctly typing events, but I don't think I typed events correctly when I first prototyped with TypeScript+React, just to see what would happen.
If it is implicit any, I get a warning and have to explicitly set it to any, or say event: Event.
![image](https://gyazo.com/db8b07cad53478a411b439df60485031/thumb/1000)

The "implicit any" means that the type information cannot be guessed, so a human must type it properly, and it cannot be detected if you type it incorrectly. As a result, the implementation of the contents of the event handler may not get the support of the type.
ts

```typescript
  const onDragStart = (event: Event /* NG: not of the right type but not warned */) => {
    console.log(event.currentTarget.clientHeight); // Error here
    // Object is possibly 'null'.  Event.currentTarget: EventTarget | null
    // Property 'clientHeight' does not exist on type 'EventTarget'.
  };
```


Knowing the correct event types in React+TypeScript (this page)
Since I noticed this technique, it has become easier for me to put the correct type on, but where do I learn these things?

[[TypeScript]]
[[React]]

---
This page is auto-translated from [/nishio/React+TypeScriptで正しいイベントの型を知る](https://scrapbox.io/nishio/React+TypeScriptで正しいイベントの型を知る) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
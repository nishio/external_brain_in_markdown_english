---
title: 'But" in programming language'
---

> [rashita2](https://twitter.com/rashita2/status/1435434283481534467): If you think about it, in programming, one line is not connected to the next line by a contraposition. In a sense, everything is a contraposition, and that is to say that it is not even a contraposition (it is just arranged in the order of execution).
- > [rashita2](https://twitter.com/rashita2/status/1435434493247037441): there is also an if statement, but it controls the order of execution (lines), not the "content" of lines and lines expressed in a non sequential manner.
- > [rashita2](https://twitter.com/rashita2/status/1435434709652180993): Maybe this story and the [[paragraph writing]] story are connected.

> [nishio](https://twitter.com/nishio/status/1435438293827522567): "How to express 'but' in a programming language?"
> You're right, in the following, it's not "but" but "however."
ts

```typescript
let x = 0; // x is zero
if(some_condition()){ // but if certain conditions are met
	x = 1; // x is 1
}
```


> [nishio](https://twitter.com/nishio/status/1435438869441224713): why do we need a "but" in natural language?
> When writing "A is A, but B is B, so C is C" in a programming language, only "C is C" should be written and A and B should be comments or something.

> [dankogai](https://twitter.com/dankogai/status/1435439602622287874): perl has an expression "0 but true" which is 0 when evaluated as a number but true when evaluated as a boolean
- > [nishio](https://twitter.com/nishio/status/1435449873579474944): does that mean x but y is "a binary operation that creates an object that is x as a number but y as a boolean value"?
- > [dankogai](https://twitter.com/dankogai/status/1435450846808973315): not an operation but a (scaler) value. Of course, as a string, it is exactly what is inside the quotation marks. The type of the value is determined at the time of evaluation.

> [torus](https://twitter.com/torus/status/1435566883927777280): but that doesn't sound like a good use for imperative programming because it's not used to tell people what to do.
>  but if it's a declarative language, I guess it's possible.
> Haskell functions are written with the most common case last, but the order could be reversed so that the most common case is marked after the second line.
> [torus](https://twitter.com/torus/status/1435589050396602368): I've heard people say "say" when giving orders to others.
> Please proceed at a reasonable pace. However, this is the critical time, so don't expect a weekend.

> [arton](https://twitter.com/arton/status/1435570684785152001): we can meet today. But not today.
> today? ? i.can : i.cant
> The term ":" is used to refer to a "young man" who is a "young man."

> [takiuchi](https://twitter.com/takiuchi/status/1435574269606387713): isn't it exception handling?

> [nishio](https://twitter.com/nishio/status/1435611140860510213): yes, it's true that else and catch (instead of if) would be more "but" like.

ts

```typescript
if (you.age >= 18) { // if you are over 18
  you.watch(this_site); // you watch this site
} else { // but if not
  return; // Go home!
}
```


---
This page is auto-translated from [/nishio/プログラミング言語で「しかし」](https://scrapbox.io/nishio/プログラミング言語で「しかし」) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
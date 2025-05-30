---
title: "Don't guess, measure."
---

You don't understand where the program is consuming your time. [[bottleneck]] is where you least expect it. Don't guess. Don't speed up until you can prove where the bottleneck is.
Measure. Don't accelerate until you measure. Don't speed up unless you measure it and one part of the code is consuming significantly more time than another.
(Translation by Nishio of Rob Pike's text)

[Basics of the Unix Philosophy](https://homepage.cs.uri.edu/~thenry/resources/unix_art/ch01s06.html)
> [[Rob Pike]], who became one of the great masters of C, offers a slightly different angle in [[Notes on C Programming]]:
>
>  Rule 1. You can't tell where a program is going to spend its time. Bottlenecks occur in surprising places, so don't try to second guess and put in a speed hack until you've proven that's where the bottleneck is.
>
>  Rule 2. Measure. Don't tune for speed until you've measured, and even then don't unless one part of the code overwhelms the rest.
>
>  Rule 3. Fancy algorithms are slow when n is small, and n is usually small. Fancy algorithms have big constants. Until you know that n is frequently going to be big, don't get fancy. (Even if n does get big, use Rule 2 first.)
>
>  Rule 4. Fancy algorithms are buggier than simple ones, and they're much harder to implement. Use simple algorithms as well as simple data structures.
>
>  Rule 5. Data dominates. If you've chosen the right data structures and organized things well, the algorithms will almost always be self-evident. Data structures, not algorithms, are central to programming.
>
>  Rule 6. There is no Rule 6.

translation with notes
- tell is a nuance of "you can't say with certainty," but writing it that way is muddled, so I've added "you don't understand."
- The nuance of "speed hack" or "tune" is "to rewrite a small part of the source code for the purpose of increasing speed," but since it is muddled, I used "speeding up.
    - The meaning of the word alone would include "making it faster by devising the data structure and design," but we're talking about making it faster without identifying the bottleneck after the source code is done, so there's no misunderstanding.
- And even then" has the nuance of "measure first, don't speed up until you measure, and even then..." However, when translated into Japanese, "measure" in front of "and even then" is far away. Therefore, we decided to cut the sentence and restate "measure".

Related: [[Basics of the Unix Philosophy]].

orthographical variants
    - [[First, measurement]]

---
This page is auto-translated from [/nishio/推測するな、計測せよ](https://scrapbox.io/nishio/推測するな、計測せよ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
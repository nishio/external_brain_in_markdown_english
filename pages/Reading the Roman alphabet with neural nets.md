---
title: "Reading the Roman alphabet with neural nets"
---

I was talking to my wife about how we did [[Embedded Hiragana and Katakana]] yesterday, and she thought it would be fun to teach romaji, so I made one.

It is a multilayer perceptron with 4 alphabetic characters as input (embedded in vector and 16 dimensional), 256 and 128 dimensional intermediate layers, and 37 dimensional output with 10 dimensional*3 embedded vector of kana characters, with OneHot for output length and input consumption.

When they don't learn well, it's usually the teacher's fault.

> nishio → nikio
- Nice try Nikio... I hope you at least answer what I taught you...
    - The learning data included only Kunrei-style romaji, so "si→shi" was taught, but "shi→shi" was not.

>  ni → mi
>  shi → ki
>  si → ki
>  o → Pi
>  nisio → nisipi
- You're starting to sound like a high school girl.
    - I wondered why "mikipi" when used individually becomes "nisipi" when connected, and found that the way the training data was created was wrong.
    - Initially, the training data was entered as "nish" and the first two letters of "ni" were added randomly after "ni" so that "ni" was returned.
    - On the other hand, when testing, if the given string is less than 4 characters long, it is marked "ni$$" with a sentence end marker after it.
    - Since "$" is not included in the training data, the first time "$" is seen at the end of a sentence in the test, it causes confusion.
    - As a result, the nisipi
    - I've also mixed $ into the training data and now I can read nishio properly.

> chopin → Chipin
- I thought it was odd that you could read nishio but not read this as chopin, so I did some research.
    - >  chi → chi
    - >  cha → chichi
    - >  chu → chichi
    - >  cho → chichi
        - In the guess result output section, when outputting more than one kana character at a time, I mistakenly repeated the first character, which was an implementation error on my part.

Check if all questions are answered correctly.
    - >  du -> du (A: zu)
    - >  du -> deux (A: deux)
        - They were bullying the students by asking the same questions with different answers they were looking for.
        - Not sure if it's a "zu" or a "de," so it's interesting to mix them up and make it a "de."


---
This page is auto-translated from [/nishio/ニューラルネットでローマ字を読む](https://scrapbox.io/nishio/ニューラルネットでローマ字を読む) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
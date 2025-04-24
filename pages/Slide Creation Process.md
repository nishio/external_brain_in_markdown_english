---
title: "Slide Creation Process"
---

first half
- ![image](https://gyazo.com/6416fc63963b753fa3db11f6a27ff424/thumb/1000)
What we're doing now.
- ![image](https://gyazo.com/cdd2ca54f3d6ce0f09422ac9e5fb53c0/thumb/1000)
- ![image](https://gyazo.com/a803956ea00e02f1ef3f7afe2c10417a/thumb/1000)
    - Step 5 is done, 8 sheets of paper are created, and the encoding of the first two sheets of it has just been finished.
    - 27 sticky notes and 42 slides.

Relating to Step 6.
    - [[path recommendation]]

Step 6 focuses on one sheet at a time
- This gives them a narrower perspective than when they were thinking about the overall composition.
- Allows you to think more deeply instead of narrowly focused
- There is a tradeoff between breadth and depth because of the limited capacity of the human brain.

Associate the next slide with the most recent slide as input
- ![image](https://gyazo.com/e1b0fddb1e46676a789815732483c8fd/thumb/1000)
- Think about how to make this happen.
    - ![image](https://gyazo.com/9c2052fa9eef90b9e01a588b186456fd/thumb/1000)
    - If we map "slides" to "words", this would be a sentence generation by [[Markov model]], which generates a sentence (word sequence) by selecting the next word from the previous N words #Markov Sentence Generation
    - In a naive Markov sentence generator, the probability of generating the next word is given by the frequency of occurrence in the original data.
        - As N grows, most of the word sequences have zero number of observations.
        - Small N only preserves relations between close words.
    - [[Sequence transformation model]] by [[LSTM]] followed up on this point.
        - [[dimensionality reduction caution]]
        - Initially, we thought it would be a random Dropout.
        - Is it appropriate to think of this type as creating a "vector to ignore" based on t and t+1?
        - With this mechanism, you can only mask against key.
        - I can multiply query and key by a rotation such that the (t - (t-1)) vector is (1, 0, 0, ... , 0), and then multiply by (0, 1, 1, ... , 0). If we apply a rotation to query and key such that the (1, 0, 0, ... , 0) vector is (0, 1, 1, ... , 1), and then apply a mask of (0, 1, 1, ... , 1), we can perform a 1D reduction in a specific direction. 1), then we can reduce one dimension in a specific direction.
            - Is one dimension all you need?
            - This system, which only allows axial reductions, is better because it is easier to create meaning on the axis.
    - I had a feeling that a dimensionality reduction caution on the back end of LSTM would be a good idea.
        - ![image](https://gyazo.com/37fb5976f7c582ac68fbf083bb7963f8/thumb/1000)

One sticky corresponds to multiple slides in the past
- ![image](https://gyazo.com/a7816b9809ad62f069ad9d55907e878d/thumb/1000)
- A human can't pull all the past slides from memory and make them sticky notes.
- Inevitably, a sticky note is created with only keyword X written on it.
- This is the same state as implicitly grouping "past slides" with title X
- One slide can contain multiple stickies, and one sticky can point to multiple slides

---
This page is auto-translated from [/nishio/講演スライド作成プロセス](https://scrapbox.io/nishio/講演スライド作成プロセス) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
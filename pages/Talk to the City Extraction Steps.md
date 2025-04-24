---
title: "Talk to the City Extraction Steps"
---

![image](https://gyazo.com/9a06a82b7d3bdb2c7dc9542d6e09ad7b/thumb/1000)

[[Talk to the City]] about the extraction step
- This is an interesting point that differs significantly from the analytical methods used prior to the advent of LLM.
- Extract 0~n elements using LLM once for raw data obtained by various means
- Progress in LLM is that you can now describe what elements you want extracted in natural language rather than in a program.
    - Conventional methods would be, for example, "divide into words and count the number of words".
    - The "words" were defined in the morphological analysis engine and were not easily controllable.
- If the data is from X (Twitter), etc., where there are many and many not useful, zero elements are extracted from the not useful posts, effectively acting as a "discard [[filter]] for the not useful ones".
- Especially effective for [[Free text questionnaires]] that contain multiple elements
    - This has a similar effect to changing open-ended questions to [multiple choice questions
    - If you strongly constrain them with prompts, you can make them choose from only the options you have chosen, just like a traditional multiple choice question.
    - but in many cases, the feature of "no need to make choices in advance" is useful for [exploratory analysis
        - If you use open-ended questions instead of multiple-choice questions at the stage of creating the questionnaire, it is often because you do not have enough knowledge about the distribution of the target data to design the options in advance.
    - When free-text responses are gathered, people will find it hard to read them all in a certain amount of time.
        - Tolerance is different for everyone, some people have a hard time with 100 cases, some can tolerate a few hundred, but 1000 cases is hard for most people.
        - When things get hard, people try to compress them by adding structure.
                - [[Classification.]] is one form.
            - However, this classification is more difficult than it seems, because it is impossible to determine in advance the appropriate [[classification criteria]] for "a large amount of data that does not [[get the big picture]].
            - Just as it is difficult to create multiple choice questions in advance.
- TTTC will assist in this process
    - The "classification" produced by TTTC will not have a perfect score to start with, but it will help humans design better classification criteria

---
This page is auto-translated from [/nishio/Talk to the Cityの抽出ステップについて](https://scrapbox.io/nishio/Talk to the Cityの抽出ステップについて) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
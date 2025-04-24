---
title: "End Design"
---

Regarding the design of the "end" of the chat with the AI, which I hadn't come up with a solution for many years, I got the idea that it would be a good idea to provide a button that says "end next time".


from [[pKeicho]]
End Design
    - [[Conversations about end design]]
    - [[How to proceed after "I see."]]
    - Create a rules-based end design for now.

---
- [[Conversation log 2021-01-30]]
I think the endgame of this one is probably that after the mode transitions to asking about relationships between symbols because it has a lot of keywords and considers them developed enough, it runs out of high scoring words, but it's still in the asking about relationships mode.
Perhaps judging it from the distribution of keyword scores,
I propose an end.
Propose a new chat.
Return to search mode
I think it would be appropriate to do one of the following
- If [[Internal Condition Observation]] can be implemented, we will do it.

Oh, right, if you're evaluating a question that takes multiple keywords in sum, when one of the keywords is dang high, you'll get a question that takes multiple keywords before you can dig into the newly emerged keywords.
(Maybe that's what it's about, I'll check the data later)

As for this phenomenon.
It's not good that "the degree of development of the keywords" and "how much attention the system is paying to them" are pushed into one real number.
Next, the action "ask the relationship between two developed symbols" is evaluated by sum, which is strange, since the AND condition is that each symbol is developed. If the input is not normalized, the coefficient of the sum should be reduced to min if it seems dangerous.

First, check the data to see if the interpretation "the type of question is biased due to a mismanagement of the design of the evaluation function" is factored in.
:

```
[(1475.3223801756035, 'audio'),,
 (1150.0752824691538, 'Voice input'),.
 (644.0707890658928, 'repeat'),.
 (377.0, 'text'),.
 (320.0, 'log'),.
 (291.0, 'human'),.
 (260.0, 'me'),.
 (250.0, 'moment'),.
 (239.0, 'character'),.
 (217.0, 'opponent')]
```


---
- It's a long time after phase3 to hear the value, because there's no design for the end.
    - I'm only questioning the relationship for new keywords in PHASE 3 as well.
    - I'm glad we ended up with [[use case: importance of grouping#5d22ad1baff09e0000253a0f]] as a response to the objective
    - Because we haven't designed the end, we're repeatedly asking how each keyword relates to the other, and it's getting more and more abstract and big-broth.
        - The keywords newly created in phase3 are becoming abstract concepts because we didn't ask any questions to concretize them.
    - I see," "!" and other emotional expressions are detected. and "What just happened?" by detecting emotional expressions such as "I see" and "! It might be a good idea to include
- End Design
    - Lack of knowledge about when it should end
        - Look at a series of exchanges and ask, "Is this a good place to end?" and consider whether it is natural or unnatural to include
        - timing
- Create an explicit termination
    - (end command) → "Thank you very much" (or some other end greeting)
    - Is this a good place to end?" →Yes" → "End greeting
        - This needs to be judged "just right to end" based on the situation, after more data is gathered.
- Exit with "bye-bye" → done

- [[Use Case: Importance of Grouping]]

---
This page is auto-translated from [/nishio/終わりのデザイン](https://scrapbox.io/nishio/終わりのデザイン) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
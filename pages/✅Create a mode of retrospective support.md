---
title: "✅Create a mode of retrospective support"
---

It would be interesting to combine [[KPT]] and [[PRO Model]] with Keicho Kikidashi Chat System to create a "Reflection Support Bot".
- Now that I have all the parts in [[Create ✅empathy writing mode]], I want to try another [[Template chatbotization]] to get things organized.

- First, decide on a name for the mode.
    - `KPT`
    - ✅Determine the first message in that mode.
        - This is a mode to assist you in looking back. Press the "Good", "Bad", and "Things to try" buttons in the input fields."
        - Is [[Accept only 🤔choice answers]] better?
        - No, See: (A)
- server-side
    - Change the client-side hitting API to the local server
    - `$ flask run --host=0.0.0.0`
    - `$ ptw -- tests/test_chat.py`
- Implement questions, actions, and state transitions
    - Determine the range of state IDs to assign.
        - I'll make it the 300s.
        - No need to save IDs, so state IDs and question IDs should be in the same range
    - Added setting by mode to initialize environment
    - Ahhh, [[I can't give you a choice on the 🤔first question.]]
        - The first answer should be "What would you like to reflect on?" because it could be the title of the export to Scrapbox or something like that. (A)
    - A clean language approach to KPT.
        - Keep
            - What good things have happened?
            - +2 basic questions
        - Problem
            - What bad things have happened?
            - What do you hope will happen to you in such a situation?
        - Try
            - What would you like to try?
            - If you do that, what happens next?
            - What is it that you value?
            - Question of necessity
                - Or, can we just relay it to Phase 3?

- If I need to adjust the score calculation, I'll do it.
    - →Not necessary.

Motion.
    - [[Reflect on the addition of a purpose-specific mode]]
- Create ✅ expansion mode mediator

schematic
![image](https://gyazo.com/492c78d7ed4f16b6b35c5b457f3a0594/thumb/1000)


---
This page is auto-translated from [/nishio/✅振り返り支援モードを作る](https://scrapbox.io/nishio/✅振り返り支援モードを作る) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
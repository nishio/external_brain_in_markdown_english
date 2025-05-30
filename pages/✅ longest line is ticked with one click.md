---
title: "✅ longest line is ticked with one click"
---

2021-01-19
![image](https://gyazo.com/709f98222e39d13bfa18892117590f70/thumb/1000)
- Implementation of [Assistance in dividing long sentences into stickies

As long as the success rate of sticky splitting is not 100%, I'm wondering if there are times when you see the converted result and want to go back.
- I can't think of a better way (2021-01-19)
    - Undo？
        - [javascript - How to make undo work in an HTML textarea after setting the value? - Stack Overflow](https://stackoverflow.com/questions/44471699/how-to-make-undo-work-in-an-html-textarea-after-setting-the-value)
    - → [[Make the full chat log a sticky]] (2021-03-29)
- In the video above, the text before conversion remains on the right.
    - Worst case scenario, I can copy and paste from here.
    - But I fixed this one.
        - If this is not updated, the "next longest line" will not be known and cannot be split.
    - Do you want to show the last split separately?
        - Copy and paste from there?
            - I want it back in one click, not copy and paste.
            - → That's an undo!
        - With this style, you can not only "revert all" but also "revert some" or "edit with reference to the original text".
- > Okubo Kohei I know it's boring, but maybe instead of immediately reflecting the result, you can check it in modal and ok/cancel it?
    - I'm struggling with that, but I can't think of a good way to do it, so I think it would be better to do it the simple way for now, and then make it more clear how it would make me happy when I use it, in the YAGNI sense.
    - I'm currently hitting the API by pressing a button for each line, but I'm starting to think that as a user, you don't want one line to be split, you want all lines that are over 20 characters long to be split with the click of a button. I'm starting to think that's the case.

done
- Return focus to text area when button is pressed
- You should also change the cursor position appropriately.
    - Moved to the end of the replaced section.

---
This page is auto-translated from [/nishio/✅最長行をワンクリックで刻む](https://scrapbox.io/nishio/✅最長行をワンクリックで刻む) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "Improve the appearance of the ✅Talk List Dialog"
---

from  [[Improve the appearance of the ✅ dialog]]
Improve the appearance of the Talk List Dialog

after
- ![image](https://gyazo.com/de44ba66120e18f25139076911555b8e/thumb/1000)

before
- ![image](https://gyazo.com/6047f8b775caaac14548d4269dbbd426/thumb/1000)
    - Thoughts.
        - Margins at the beginning of the list are useless.
        - If the title is a link, is the ShowLog button unnecessary?
            - But is explicit manipulation easier to understand than implicit manipulation?
        - It would be easier to see if the head is aligned if the line breaks before the title.
        - Margin between items
- [React List component - Material-UI](https://material-ui.com/components/lists/)
    - ![image](https://gyazo.com/03b898f38898492d41187a402811254e/thumb/1000)
        - I'm not using it on my development PC, so the data is crappy.
    - ![image](https://gyazo.com/e75003e48602dd888f884998222b72ce/thumb/1000)
        - I tried to temporarily display a title that looks like that.
- Try iPhone X size
    - ![image](https://gyazo.com/7a9ed73db37187fa97135422b7c8468f/thumb/1000)
        - Hmmm, the button shrinking and the text sticking out is subtle.
    - Pattern with buttons enclosed in divs
        - ![image](https://gyazo.com/1d2e04258b1debdabaf7600c787dad62/thumb/1000)
    - Patterns out of ListItem
        - ![image](https://gyazo.com/7ef8149fcd704898eb5abafb14994b6a/thumb/1000)
    - I prefer the former.
- The button shrinks because the parent has flex on it.
- buttons with align-items: flex-end; and aligned at the bottom
- ![image](https://gyazo.com/ae01e39e383ecb4621a638308abf68e2/thumb/1000)

- Confirmation with actual equipment
    - ![image](https://gyazo.com/0771827811547cdaf231128ea8e29856/thumb/1000)
        - Ah, that's what happens when the length of the text is mixed.
- I'd like to bring the talk list stored on my phone's local storage to the development PC to try it out.
    - [[Export/Import ✅ talk list]]
- I was able to reproduce it on a development PC.
    - ![image](https://gyazo.com/3f100bfa6f94e76c94c4a94872e931c2/thumb/1000)
- I was thinking that if I could have a row of buttons to save space, I'd prefer to have a row of buttons, but that's not so good.
    - ![image](https://gyazo.com/9be9d3c4d133665f3631747ba425bbce/thumb/1000)
- `flex-basis: 110px;` to make the base size the width of the larger button, so the base will wrap around.
- Add `flex-grow: 1;` to both the text and button divs, so that when the text is short, the button div is also stretched, and when it is stretched enough, it becomes a single row.
- Use `text-align: right;` to right-align the button. The right edge of the button will be aligned no matter what the div of the button is.
- Buttons sticking out above text is tacky.
    - ![image](https://gyazo.com/6275055b1929fe2c402324a572658b9e/thumb/1000)
    - `align-self: flex-start;` and `align-self: flex-end;` to make text above and buttons below
- Lightly ink the list area and add a shadow similar to that of a button.
    - `background: #eee;`
    - `box-shadow: 0px 3px 1px -2px rgb(0 0 0 / 20%), 0px 2px 2px 0px rgb(0 0 0 / 14%), 0px 1px 5px 0px rgb(0 0 0 / 12%);`
- It's done.
    - ![image](https://gyazo.com/de44ba66120e18f25139076911555b8e/thumb/1000)

State of div.
![image](https://gyazo.com/af8183485a244dd14a681f7903fca9b2/thumb/1000)![image](https://gyazo.com/ff97de0ed8a2b17a144622b1f7179974/thumb/1000)


---
This page is auto-translated from [/nishio/✅Talk List Dialogの見た目を改善する](https://scrapbox.io/nishio/✅Talk List Dialogの見た目を改善する) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
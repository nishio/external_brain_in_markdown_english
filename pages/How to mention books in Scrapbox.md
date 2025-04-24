---
title: "How to mention books in Scrapbox"
---

- 1: Just a URL
    - [http://amzn.to/2sjPTJV](http://amzn.to/2sjPTJV)
- 2: Write in link notation
    - [technology-supporting-coding](http://amzn.to/2sjPTJV)
- 3: I want to use a cover image
    - If I put a cover image, when I click on it, it takes me to Gyazo.
    - Is this unexpected behavior for the user?
    - ![image](https://gyazo.com/10a71acdc7c3ca43913f013be2d7e667/thumb/1000)
        - It doesn't have to be this big...
        - I can't jump to the key book page, so I end up writing a link.
- 4: Create a book page
        - [[Technology Supporting Coding]]
    - The image appears in the Links below, but not here.
    - That would be fine in many cases.
    - You could also put your reading notes for the book on that page.
    - Looks good, but cost to make is high (a pain in the ass).
        - It must be a pain in the ass to put up images when you get right down to it.
        - Should I just give up on the cover image?
- What do you suggest?
    - Someone could make a Chrome extension or something.
        - Activate bookmarklet on Amazon's mobile version [http://hokoxjouhou.blog105.fc2.com/blog-entry-844.html?sp](http://hokoxjouhou.blog105.fc2.com/blog-entry-844.html?sp)
        - I tried it, but it doesn't work as described.
        - ![image](https://images-fe.ssl-images-amazon.com/images/I/51nXP3TKXVL._SL160_.jpg)
            - Good size
        - The mobile version is weird because katakana is half-width.
        - It's uncomfortable to have a link to the mobile version when you're looking at it from a PC in the first place.
    - At any rate, if you put in the Amazon Associates bar.
        - $("#amzn-ss-text-shortlink-textarea").value
        - "[http://amzn.to/2skOmD9"](http://amzn.to/2skOmD9")
        - $("#imgBlkFront").src
        - [https://images-na.ssl-images-amazon.com/images/I/51nXP3TKXVL._SX351_BO1,204,203,200_.jpg](https://images-na.ssl-images-amazon.com/images/I/51nXP3TKXVL._SX351_BO1,204,203,200_.jpg)
        - It seems to be possible to link with an image if the image URL is placed in the order of the URL to be linked to.

---
This page is auto-translated from [/nishio/Scrapboxで書籍に言及する方法](https://scrapbox.io/nishio/Scrapboxで書籍に言及する方法) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
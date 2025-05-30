---
title: "pIntEn formatting starts"
---

from  [[Project for English-language intellectual production techniques for engineers (-20190522)]]
pIntEn formatting starts
2019-02-01
- 1 month progress = 75 pages
- Pace to be finished by the end of March, if only for translation.
- However, man-hours of work for "e-book release" are not estimated.
- We plan to make a separate book to measure up to that point at the end of the chapter we are translating now.

2019-02-04
- 3rd: Translation of the first two chapters is finished.
    - I kept it in chapter 3 for "[It doesn't end at the end of the line.
- The plan was to start working on the annex after two chapters were done.
    - I have finished translating the first two chapters, and my plan is to convert the book into an e-book and measure the time required, but I feel that the process of "translation," which has become a repetitive and routine task, and the task of "e-book conversion," for which it is unclear what to do, should be mixed together (what?).
    - I'm thinking that tomorrow I will try to digitize in the time I have left because I have meetings and experiments to do at night, but I'm not sure if I will be able to do tasks with unclear "things to do" in the time I have left.
- →
    - I thought about it.
    - Now translations are logged on a "daily basis" and worked on a pomodoro basis.
    - How about performing typesetting work in a fraction of the time?
    - A chunk of time is allocated for translation, and the shredded time is used to keep up appearances.
    - Typesetting for relaxation in a state of writing fatigue.
    - We don't want to have translation and typesetting competing for resources and losing motivation over "which should we do?
    - Basically, if there's time for one pomodoro, we'll move forward on the translation side.

- work memo
    - Dropbox:/intellitech-howtoboostyourcreativity has the manuscript
    - I put the image in images.
    - Start [[Typora]] （I only use it for this so I can see it in Recent)
    - online time
        - Follow each page in Scrapbox, convert it to markdown, and paste it into Typora.
    - Offline
        - Fixing what was put on Typora.

- Author→Books→Title→Preview→Create Preview
    - Permalink Found: [https://leanpub.com/intellitech-howtoboostyourcreativity/preview](https://leanpub.com/intellitech-howtoboostyourcreativity/preview)

2019-02-08
- Drag-dropped images are in full path.
    - It should be something like `images/tmp.png` to be correct.
- Footnotes `[^1]` and `[^1]:` are recognized and previewed on Typola, but they do not work well in LeanPub
- Current Design
    - Chapter numbering in the Japanese version is expressed by a combination of chapter numbers, section numbers, etc.
    - Added clauses, etc. are numbered with branch numbers, just like articles of law.
    - Columns are not tied to chapters.
    - The keyword links on the page are the equivalent of an "index" in a book, so the link xxx jumps to the xxx item at the end of the content, and links to all occurrences of xxx are placed in that item.
    - In the case of Scrapbox, the links are divided into red links and blue links, so that you can see the unconnected links even if you don't step on them. In the case of Scrapbox, the links are divided into red links and blue links. In the case of e-books, should the unconnected links just be displayed as keywords or something? I'm currently using one-bus processing, but I'll need to use two-pass.
    - Markua only allows alphanumeric hyphens as IDs, so I'm using the first 7 characters of the md5 hash as my ID.

2019-02-11
- daiiz is trying Scrapbox -> Re:VIEW -> e-book, and
    - [Saturday - #daiiz memo](https://daiiz.hatenablog.com/entry/2019/02/09/235500)
    - [/daiiz/sb2re development book](https://scrapbox.io/daiiz/sb2re development book).
- I went from Scrapbox to [[LeanPub]] Markdown to e-books.

2019-02-14
- There's a teaser site in the process of creating the project.
    - [https://leanpub.com/intellitech-howtoboostyourcreativity](https://leanpub.com/intellitech-howtoboostyourcreativity)
    - ![image](https://gyazo.com/a1332e760a88e50e3e7c4002771f1566/thumb/1000)
- I left it at 10% because it can indicate completion.
    - If you increase it by 10% for each completed chapter, you'll be at 80% when you're all done, and we'll review the whole thing from there.
- I pressed the release button as it is recommended to release frequently.
- Minimum amount cannot be lower than 4.99$.
- ![image](https://gyazo.com/33fd428ec32ca6bbd260ba1f89902ef4/thumb/1000)
- Page and word counts are now displayed. It automatically counts and displays: 30 pages, 3645 words.
- If you wonder what the scroll bar for the amount is, you can drag it to decide how much you want to pay.
    - I could raise it up to 25$, but I'm not sure if this is me setting the limit somewhere.
- Hoho, is there an option to make it a Creative Commons?
    - ![image](https://gyazo.com/2c8b29bf5794f77948e0eb260bb141d2/thumb/1000)
- I was able to Enable the Forum.
    - [https://community.leanpub.com/c/intellitech-how](https://community.leanpub.com/c/intellitech-how)

- work
    - Footnotes displayed correctly on Typola but broken in epub
        - Markua footnote definitions require a preceding blank line
        - In epub, they were grouped together at the end of the book. Personally, I don't like footnotes because "you don't have to read it to see it" is the beauty of footnotes, but I guess it's not a priority.
    - Problem of Japanese garbled in PDF version
        - For now, just enclose all Japanese words in {japanesefont}{latinfont}.
        - I was going to automate it with a script.
        - `[{japanesefont}Japanese {latinfont}](...) `
        - And that's a hassle.
    - I fixed it by hand for now.
    - I tried to put the English part together and put it in Japanese, but the font was lame.
    - Maybe we should think about outsourcing this one.

- On Typola, a figure alt is just an alt, but in Markua it is a figure caption
    - I was a bit surprised that the caption didn't show up on Typola.
        - It's a long iteration to learn the right markup.

- A bug caused the text between links to disappear when there were multiple links on a single line.
        - [[Recovery when working from buggy output]]

- At any rate, I have released a new version 2 based on the revision work done so far.
    - They say that readers will be notified when a new version is released.
    - You could have done a review during the writing process or something with this.
    - ![image](https://gyazo.com/311dee8055e2f649a7e2528f093a8321/thumb/1000)

- I thought, how could there not be a way to give them away for free, and they call them "coupons"?
    - ![image](https://gyazo.com/c2bfb96f203a6a91defbb5577c8b58e8/thumb/1000)
    - In addition, I CREATE in this state and discount $4.99 to $4.99? I've got a coupon to do that.
    - Can be edited so you don't have to worry
- If you got the link, you can get it at a discounted price like this... discounted to $0.
    - ![image](https://gyazo.com/689fc199ad13e47cf2131b9b18494852/thumb/1000)

- The books you buy go into the library like this
    - ![image](https://gyazo.com/cb5843c296d42db833ef00d2bdbeac4e/thumb/1000)

- I've been writing contacts, etc. on Scrapbox, but this is how it appeared on LeanPub in the first place.
    - ![image](https://gyazo.com/8807266e7015c798bb7c1d657c56aeac/thumb/1000)

- Here's what I see when I look at the books in my library
    - ![image](https://gyazo.com/d0938b60646a9698299435cafd540911/thumb/1000)
    - Oh, so email notification of updates is off by default?

- Scrapbox parser, I'm starting to think that since I'm going to need it for a project later this year anyway, I might as well make my own. Links, bullet points, images, and external links are enough for my purposes.
    - Miscellaneous [[Scrapbox Parser]] was created.

- Create a tree from a list of pages
    - This time, we get the list of pages sorted alphabetically, and manually make a tree
    - Since this is a book-derived project, the chapter numbers are attached to the title of the book.
    - How would you line it up for a normal project?
        - Proposal to throw the whole thing to humans.
        - Proposal to make some kind of suggestion

- I was able to get to the point where I could hit Scrapbox's API and get the contents of multiple pages and connect them together to make a markdown. I was a little worried about whether or not to go as far as filling in the id's for cross-linking books, but now I'm thinking it's better to keep it separate since that's going to be a two-pass in the future and it has nothing to do with Scrapbox at all.

![image](https://gyazo.com/072bdf330761fbf37fcb5c78488ee526/thumb/1000)

- Some images are only available in Scrapbox (in Gyazo)
    - Automatically download when crawling Scrapbox or
    - Is that smooth enough, given that images can be updated and added?
    - It is a rather special use case to have the images locally in advance this time.


2019-02-19
- Implemented a script to discover links to images (Gyazo) from JSON files downloaded via Scrapbox's API and save them all locally.
- Unlike our initial expectations, the "e-book creation work" was not a monotonous task, but rather more like programming.
- There is a debugging process that says, "If I do this, it will output this way," or "It didn't, what's wrong with it?

- When previewing a whole chapter of a book with typola, mysterious misalignment occurs when switching between code mode and preview mode, making it unusable.
    - I thought about it, but it's a pain to automatically convert the page title to a valid string as a file name.

---
This page is auto-translated from [/nishio/pIntEn 組版開始](https://scrapbox.io/nishio/pIntEn 組版開始) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
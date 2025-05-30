---
title: "Write in Scrapbox and share via link"
---

- Formerly titled "Scrapbox and GoogleDocs
    - I thought, "This is useful, I'll summarize it" after a lively discussion in the chat room.
        - I put it together in Scrapbox.
        - When I want to share it with the people who participated in the chat, Scrapbox doesn't allow me to "share by link".
    - I can't put the story on my public because I can't disclose it.
    - Even if you create a new PRIVATE project...
        - Invite links cannot be placed on individual pages.
        - It's a two-step process: "Enter the group through this link, and then look at this page."
    - Use case: "I want to put a link and say, 'Here's the summary.
    - I wonder if I'll be able to port what I'm putting together now to Google Docs and "[[Share by Link]]" it later.

- I slept through the night and woke up and came up with a solution.
    - After summarizing in Scrapbox, convert to Markdown with bookmarklet
        - [I wrote a Bookmarklet that converts text from Scrapbox pages to Markdown using](http://daiiz.hatenablog.com/entry/2017/02/17/074508)
    - Just paste that Markdown into [HackMD - a collaborative editable Markdown notebook [https://hackmd.io/](https://hackmd.io/)
        - Only those who know the link can [joint editing
    - However, the above bookmarklet does not convert nested bullets correctly at this time.
        - OK if the output after conversion is `s/^( +)/\1\1/`.
            - Feedback has been provided to the author.
    - Hopefully Markdown export will be officially supported in the future.

- Scrapbox's strength is its page-to-page linking, so for the purpose of sharing a single page, it's honestly not much different from other services.
    - Conversely, I have no problem writing in Scrapbox, I just need to be able to export one page in Markdown without stress.
    - Is the advantage of having a full set of shortcuts regarding bullet organization?
        - [/help/outline editing](https://scrapbox.io/help/outline editing).

- GoogleDocs has the advantage that it has a full range of "comment" and "edit diff" functions, although it was concluded that GoogleDocs will not be used this time.
    - However, for the use case of "I summarized the discussion in the chat room", the highlighting of the edited differences is not necessary.
    - It seems that Dropbox is creating a culture of using bullet points as a tree board for commenting.
        - There is a problem with the lack of separation between the text and comments.
    - Useful for correcting web articles and such.

- [Dropbox Paper](https://www.dropbox.com/paper) is also used for one of my jobs
    - The main difference when compared to the other three methods is...
        - Is it just the Dropbox icon in the task tray by default that notifies me of updates?
        - [How to notify that it has been updated, which is an important element to encourage users to continue using the system.
        - Another time.

- Another issue is if you share it on HackMD and then edit it, how do you get it back into Scrapbox?
    - If you were editing only on HackMD, you can convert it back to Scrapbox and overwrite it.
    - If you were also editing in Scrapbox, how would you merge the two, which raises the question.
    - Merge both as Markdown?
---
This page is auto-translated from [/nishio/Scrapboxで書いてリンクで共有](https://scrapbox.io/nishio/Scrapboxで書いてリンクで共有) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "Bat Design Patterns for Communication Tools"
---

- All submissions are notified to all participants.
    - It is okay while the number of participants is low, but when the number increases, notification overflow occurs.
    - solution
            - [[Mention.]] : Separate notifications for specific individuals from those not addressed to others (Twitter, Slack, kintone, etc.)

- Asks for information other than body text when submitting
    - Email culture asking for title
    - An approach that encourages organization by pre-assigning attribute information.
    - demerit
        - Raising the bar for submissions

- When a child comment is added to a parent comment on a tree-like bulletin board, only the latest post in the entire tree is [[notice]].
    - Notification of the parent comment itself is hidden by notification of the child comment.

- No way to say "[[I want you to see this.]]" to a specific person
    - Manual notification occurs in a separate tool.
    - The information is fragmented as the exchange proceeds on that tool.

    - There is no way to distinguish between [I don't mind seeing it." and "I want you to see it."
    - For example, e-mail
    - Blurred distinction between "I'll share information with you so you can look at it" and "I want you to look at it and respond back.

- You will be notified of readings.
    - Mr. A is notified if Mr. B has seen Mr. A's post.
    - At first glance, the advantage appears to be that the sender can know "if the recipient has seen it or not".
    - On the other hand, it created concepts such as "read-through
    - Receivers get tired when the sender has a "if you saw it, you should reply" culture.
    - Generate behaviors such as "I noticed the notification, but I don't want to open it because I don't want to be notified that it has been read.
    - In tools that have "likes," "liking" can be used as a positive read notification

- character limit
    - Even if you limit the number of characters, users who want to write long sentences will just throw them in a row.
    - The system will lose track of whether it's a continuous topic or simply posted at short intervals.

- Character limit 2: There is no limit to the number of characters of content, but there is a limit to the amount that can be pasted at one time.
    - Users are forced to paste, get rejected, split and paste again.

    - [[off-line]] behavior (this is a difficult problem...)
    - Tools that do not allow offline input force the human [[living brain]] to remember, "I'll type it in later when I'm online.
        - forget
        - Or write in another tool.
            - Write in another tool and forget to post it.

    - [[DM prohibition]]
    - Prohibits one-on-one communication
    - If you leave the need for "one-to-one communication" unattended and ban only the means, users will use other methods of one-to-one communication.

- No permalinks for posts
    - Cannot point to it with a link when referring to it later

- No way to see read notifications.
    - When a notification is read, there is no way to see that read.
    - Once you see the notification and think "I'll take a closer look at this later" or "I'll take action later", you need to re-post that link somewhere, or else "Where was that?" becomes

bad culture
- Forced to Like
    - When combined with people who have a high need for control over others, they start thinking that all their subordinates should like their posts.
    - When you see how many total likes you have, you'll know right away that you're missing one.
    - If you can see who has liked it, you can also see who hasn't.
    - The like mechanism itself is not bad, but there are organizational cultures that are incompatible.

- [[bad pattern]]

---
This page is auto-translated from [/nishio/コミュニケーションツールのバットデザインパターン](https://scrapbox.io/nishio/コミュニケーションツールのバットデザインパターン) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
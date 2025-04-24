---
title: "Doing a width-priority Keicho with Scrapbox"
---

- Wouldn't it be better to do [[Width Preferred Keicho]] in Scrapbox?

- I saw [[Extension to use Keicho with Scrapbox]] and thought

Now Keicho assumes the chat.
- In chat, when you dig into keywords that appeared in an earlier conversation, but not immediately before, you regurgitate them in the form of "quotes" because people can't remember which ones you're talking about.
- The early implementation was not comfortable as a chat due to frequent quoting, so the emphasis was shifted to the immediately preceding statement.
- As a result, the behavior became "depth-first search" like.
- I'm getting off track.
- Need "breadth-first search" to stay around the "first question"
- Tree bulletin board format
    - Expression in the form of hanging rather than quoting
    - I was thinking of having that "depth to the first question" as an internal state, but maybe we could have it visible to the user in bulleted depth?

But do you need to be able to add a line anywhere on a given page in Scrapbox?
Hard to do because Scrapbox doesn't have an API.
Why not Scrapbox instead?
You don't need all the decorations and other tags, just text bullets.
I'd like to see a bracket completion feature, though.

Should it be turn-based?
- Comments are made where they are not written by me.
- A sense of being pushed around
- Instead of using a turn-based system, we can ask questions until the number of unanswered questions reaches a limit, or something like that.
    - One case would be a turnstile.
    - It would be interesting to have three or so.


---
This page is auto-translated from [/nishio/幅優先KeichoをScrapboxでやる](https://scrapbox.io/nishio/幅優先KeichoをScrapboxでやる) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "Support for combining your past writing with your current thinking"
---

- Written on 2015-07-13, discussing how to help my writing in the past combine with my current thinking.
    - There is talk of [[Similar document search]] by [[word vector]] and a [[Wiki]] system that would later be called [[Scrapbox]].
#warming up

-----
- When I reread my past writings for some reason, I sometimes find myself thinking, "Oh, this is what I wrote, this can be applied to what I am thinking about now," and I wonder if this process can be enhanced by software or methodology.
- There is a similar but different "Oh, I think I've written about this before, but where?".
- We know it exists, we know where it exists, we know where it is.
- I can see that it might be relevant, I can see that it is relevant, I can see the content.
- Search engines will tell you where to find documents that may be relevant by searching for keywords that may be relevant.
- What do you do when you don't realize that "if you search, you'll find something that might be relevant?" What if you don't know the keywords?
        - [[Hideki Kondo]] It is convenient to always talk to people and they will associate themselves with it!
    - How does the person make the association? If we can find that out, a computer might be able to read everything and make the associations for us.
    - [[Tatsuo Yamashita]] [[Similar document search]] is good, isn't it?
        - To put it in detail, the documents are term-vectored in advance, and the similarity of all combinations is calculated. When a document is presented, several documents with high similarity to it are also presented.
    - In the "when I present a document, I present a document that is highly similar to it" approach, you need to input a new verbalization of "what I am thinking about" in order to realize that it is useful for what I am thinking about right now. I was thinking "chicken and egg if that verbalization is what you want to support..." but when I think about it, you could just raise a few keywords. Maybe that's the right approach....
    - Tatsuo Yamashita Yes, yes. As for input, just make your thoughts into word vectors (i.e., multiple keywords) instead of sentences!
        - If you are Mr. Nishio, why don't you say something along the lines of "intellectual production techniques by [[word2vec]]" or "idea support by word2vec" or something along those lines?
    - I thought about something like that, but I was bothered by the similarity between "Bag of Vectors" when the words are vectors...
    - Tatsuo Yamashita Why don't you just do it all?
        - There are some papers on word2vec to doc2vec, so I was wondering if there is a way to make it work. Well, maybe it will work in a wild way, such as averaging all the words in a document and making it the vector of the document.

    - [[Toshiyuki Masui]] Why not Wiki?
    - [http://Gyazz.com/UIPedia](http://Gyazz.com/UIPedia)
- How can we use the Wiki to enhance the "process of realizing that what we were thinking about in the past is useful for what we are thinking about now"?
- Toshiyuki Masui [[Gyazz]], you will see pages that use the same keywords, which may remind you of old ideas.
- I see, same keywords. Are those keywords extracted by morphological analysis or something? Are they added by humans?
- Toshiyuki Masui A human being will put it on.
    - It's not so much the keywords as the page name. Since there is no distinction between page name and keywords.
- I see. What I was envisioning now was a blog post or a post to Facebook, but even now, porting it to a wiki might be effective in strengthening future recall.
- Toshiyuki Masui I have several thousand pages of my own, so I am warming to the idea.
- By the way, what is this graphical thing?

    - [[Kohei Okubo]] How about evernote's function to suggest past related articles?

[Facebook 2015-07-13](https://www.facebook.com/nishiohirokazu/posts/10206422116088253)

---
This page is auto-translated from [/nishio/過去の自分の書き物と今の思考の結合支援](https://scrapbox.io/nishio/過去の自分の書き物と今の思考の結合支援) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
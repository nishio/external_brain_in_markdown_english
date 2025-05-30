---
title: "Where is full-text search headed?"
---

> [voluntas](https://twitter.com/voluntas/status/1639113470326214656) I'm seriously wondering where [[full-text search]] is headed. I have a feeling that the current trend will result in infinitely less demand.
- > [voluntas](https://twitter.com/voluntas/status/1639115301156700161) For our own documentation (Sphinx), of course, interactive search like ChatGPT is much better than full-text search. I can also see a future where we can generate a lot of sample code to learn. It would also be nice to be able to provide reference links. In this case, I wonder if full-text search is necessary. I'm not so sure.
- > [voluntas](https://twitter.com/voluntas/status/1639116346616352768) Search is not interactive, and it is too cunning to say that it is interactive.
- > [voluntas](https://twitter.com/voluntas/status/1639116738569859072) Documentation is seriously important for closed source products like ours, so we have to think a lot about it.


> [tokoroten](https://twitter.com/tokoroten/status/1639117102698360832) I think that only legal documents, contracts and receipts have lost the meaning of holding the full text anymore.
- >  Other content can be genned as needed.
- > [voluntas](https://twitter.com/voluntas/status/1639117283938435074) Ah, in my case, it is an "official document", so I think it is of great value in itself. Only the base information cannot be generated automatically.
- > [voluntas](https://twitter.com/voluntas/status/1639117338749599746) Is this correct?
- > [tokoroten](https://twitter.com/tokoroten/status/1639117942368669698) I don't think it even needs to be an official document unless the official document has a legal basis.
- >  Ultimately, a future where documentation can be genned from time to time from the language specification and numerous examples.
- > [voluntas](https://twitter.com/voluntas/status/1639118368098893824) Ah, I see what you mean. However, in the case of my own products, there is a "range of what can be made public" (I don't want dynamic generation from the source), and I feel that a human being should do his/her best in that area. It's like a borderline.
- > [moriwaka](https://twitter.com/moriwaka/status/1639120200661618688) It is important to write documentation to clear up the distinction between what is behavior that you can promise the user that you intend to maintain in the future, and what is implementation-dependent behavior that is currently the case but you don't know if it will change in the future. It is important to write a document to clarify the distinction between what is implementation-dependent behavior and what is implementation-dependent behavior. ......
- > [voluntas](https://twitter.com/voluntas/status/1639120679974080512) I agree. I think it will be very important to have an authorization to "release information to whom and to what extent".
- > [nishio](https://twitter.com/nishio/status/1639129935095926788) tokoroten's point of view is interesting, but it seems to me that V's focus is different from what he was concerned about in his first tweet, and V's point of view is interesting too, so I'd like to elaborate. I'm inclined to ask.


> [moriwaka](https://twitter.com/moriwaka/status/1639138661999718401) Considering the old and new versions of the documentation, "When did the XX feature come from? How did it change? In the future, full-text search will be used as a backend for front-end AI to obtain necessary documents when dealing with queries such as "When did the XX feature come out of the old version?


> [johtani](https://twitter.com/johtani/status/1639124163679129600) I guess by full text search here you mean keyword search, which may change how it will look in the future as a UI. I'm not sure if it's easier to ask in natural language or not, so things may change. I wonder how the UI will be changed in the future. As for how to hold the data, a system to search by vector rather than inverted index is emerging, and I think that's what will be used.
- > [johtani](https://twitter.com/johtani/status/1639124628986789889) And then there are searches for things that are not full text (is this off topic?). And I'm talking about "full-text search."
- > [voluntas](https://twitter.com/voluntas/status/1639124652525260800) Will the full-text search mechanism itself be superseded? I think so. I think that the search itself is to check the "pointer to the original text".

> [nishio](https://twitter.com/nishio/status/1639154988789403650) I put it together.
>   [[Where is full-text search headed?]]
>  My opinion: LLM will do full text search
>  [[Toolformer]]
- > [nishio](https://twitter.com/nishio/status/1639155863083712513) Humans create documents for LLMs to refer to, and at first the LLMs will approach the documents as if they were written for humans to read, and eventually the knowledge that "this format is better for LLMs to read" will build up, and they will write in that format. Eventually, the knowledge that "LLMs can read better if it is formatted in this way" accumulates, and they start to write in such a format.
- > [nishio](https://twitter.com/nishio/status/1639156497258287104) Readers can explicitly ask questions and get answers, or they can ask "show me a tutorial" and get a generated tutorial. If you design the information well, you can tell them "I have experience with A, I don't have experience with B" and generate it for that individual, or you can read what comes up and "learn more" when you don't understand.

> [dmikurube](https://twitter.com/dmikurube/status/1639153612113997824) So-called "documented" functions imply "you may use". So, a function that is implemented as a function but not to be used without permission is called "undocumented". If the undocumented feature is made documented without permission, dependency on it will occur, and it will be a problem later.
- > [dmikurube](https://twitter.com/dmikurube/status/1639154106257506305) Just because the code is implemented and works, there is still a bit of a gap between that and an official "feature you can use". If they look at the code and decide it's OK to use without permission, it's going to be extremely difficult to maintain later on.
- > [dmikurube](https://twitter.com/dmikurube/status/1639154643765968898) Don't think the existence of "original text" will ever go away, including in that regard.
- > [dmikurube](https://twitter.com/dmikurube/status/1639155857790496768) It's going to happen normally that full-text search for documents will be replaced by queries against the language model, but don't think that the document, the I don't think that the existence of the original document will disappear, but it will go in the opposite direction. The query itself will be analyzed to expand the documentation based on the knowledge of "Oh, so this is what you want to know.
    - > [nishio](https://twitter.com/nishio/status/1639156967905312768) This pathway is important, a future where the LLM summarizes the query the reader is throwing and suggests "you should write more about ~"!
- > [dmikurube](https://twitter.com/dmikurube/status/1639159506063233024) If something works, there will certainly be people who start using it without permission, and people get angry when the behavior there changes because they were just using it without permission. Documentation is a line of defense to talk back when people get angry there!


> [hrjn](https://twitter.com/hrjn/status/1639163467327504384) Sometimes the original text is important, sometimes it's not, and if the original text isn't important, I feel like it's a good thing that ChatGPT answered the question in the right way.
>  On the other hand, in most cases, the origin of information is important in determining the reliability of information, so I don't think the act of searching for documents will eventually disappear.
- > [hrjn](https://twitter.com/hrjn/status/1639163865807351808) For example, when I look at StackOverflow, I judge the reliability of ChatGPT by looking at the upvotes and comments to some extent. I don't read that much air, so I have to look at the original text.
- > [hrjn](https://twitter.com/hrjn/status/1639165007035531266) At least at present, ChatGPT does not guarantee the quality of information, and if anything, the quality is on the low side.
- >  To begin with, what is the quality of information is a deep issue, and it is not easily solved, as evidenced by Google's preference for "How was it?" articles...
- > [nishio](https://twitter.com/nishio/status/1639164292829446148) Isn't it subtle whether a "human" would search "with a keyword exact match full-text search" that the LLM points to a link and reads the original text, since "humans Since "no".
- > hrjn: Well, I kind of understand what you mean, but I think that "full-text search with exact keyword matches" hardly exists nowadays, or at least token-level normalization is done by any full-text search engine, or at least synonym definition or query expansion is done by default. I think that synonym definition and query expansion can be done by default.
- >  > People who are a bit richer have been doing as much as vector searching of distributed documents > > since before LLM, so nothing has changed.
> [voluntas](https://twitter.com/voluntas/status/1639164445170761729) I'm not sure if I'm making a good premise here, and it's not ChatGPT or anything, but rather "isn't full-text search for a particular document switching to interactive search? I think it's a good idea to make it interactive. I'm not sure if it's ChatGPT or something else.
>  >hrjn: I feel that the original text may or may not be important, and if the original text is not important, then it's a good thing that ChatGPT answered the question in the right way.
- > [hrjn](https://twitter.com/hrjn/status/1639169281542995968) I think it would certainly change in terms of searching within a document.
- >  I've been using EDGE lately to search for information on pages by doing things like "what's the conclusion" or "specific examples", but I think that's what I want to know.
- > [hrjn](https://twitter.com/hrjn/status/1639169667171491841) This is also rarely a lie, but I think it's helpful because it's much easier to confirm if you read the worst of it and find it after you know.


---
This page is auto-translated from [/nishio/全文検索がどこに向かうのか](https://scrapbox.io/nishio/全文検索がどこに向かうのか) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
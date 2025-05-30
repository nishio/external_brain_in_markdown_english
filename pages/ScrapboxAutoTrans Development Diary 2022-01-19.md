---
title: "ScrapboxAutoTrans Development Diary 2022-01-19"
---

prev  [[ScrapboxAutoTrans Development Diary 2022-01-17]]

How would you translate it?
- If it's not already translated when you access it, we'll translate it.
- Translate the title only
- translate all first

After all, we need at least a translation of the title for the link to connect, and we need a translation of the whole thing for the search, so why not just translate the whole thing? I feel like...

I guess this is how it goes.
- Partial translation
    - Observation.
- Export in JSON
- Translate all
    - Operate and observe for a while
- Detect updates and automatically retranslate them

Partial translation
- [[DeepL REST API]] #DeepL
- [DeepL Pro | Translate Text, Word Docs & Other Docs Securely](https://www.deepl.com/pro#developer)
    - ![image](https://gyazo.com/2ebfb7ef54b85892f8c9741e74b238fd/thumb/1000)
- [https://www.deepl.com/docs-api/accessing-the-api/](https://www.deepl.com/docs-api/accessing-the-api/)
    - There's an official Python library, but in the future I'll be hitting the API with TypeScript on Vercel.
    - I'm just going to hit them with REST anyway.
- source_lang: "JA"
- target_lang: "EN-US"

split_sentences	Optional	Sets whether the translation engine should first split the input into sentences. This is enabled by default. Possible values are:
- "0" - no splitting at all, whole input is treated as one sentence
- "1" (default) - splits on punctuation and on newlines
- "nonewlines" - splits on punctuation only, ignoring newlines
- For applications that send one sentence per text parameter, it is advisable to set split_sentences=0, in order to prevent the engine from splitting the sentence unintentionally.
Oh, I see. When I used the web interface, I thought that documents with fixed-character line breaks would not translate well unless I erased the line breaks, but I guess this is how it works.

preserve_formatting	Optional	Sets whether the translation engine should respect the original formatting, even if it would usually correct some aspects. Possible values are:
"0" (default)
"1"
The formatting aspects affected by this setting include:
Punctuation at the beginning and end of the sentence
Upper/lower case at the beginning of the sentence
Need to experiment to see if this affects Scrapbox translations.

glossary_id	Optional	Specify the glossary to use for the translation. Important: This requires the source_lang parameter to be set and the language pair of the glossary has to match the language pair of the request.
Oh, I guess I could specify the translation.

XML handling is officially supported, so if you want to translate without breaking the structure, you can convert it to XML at hand

---
It's done.
![image](https://gyazo.com/a80b6ef2e227460f5c8d2d06bf20b7d1/thumb/1000)

ts

```typescript
const data = {
  auth_key: secret,
  text: text,
  source_lang: 'JA',
  target_lang: 'EN-US',
}
const trans = await fetch('https://api-free.deepl.com/v2/translate', {
  method: 'POST',
  headers: {
    'Content-type': 'application/x-www-form-urlencoded;charset=UTF-8',
  },
  body: new URLSearchParams(data),
})
const transJson = await trans.json()
```


![image](https://gyazo.com/629af2874dc7894f8c9008253c621d46/thumb/1000)
- This trial and error alone consumes 1% of the free slots.

I could translate via API.
- However, right now I'm translating per request, so if I publish it as is, I'll have a hard time charging for it. w
- We need to create a caching mechanism.

I'm getting confused trying to figure out how to cache the translation results...

The design of the beta base to be cached depends on how it will be used.
- Indexing by Japanese title or by English title after translation?
    - Cases where the translation results in the same string
    - Cases of translation changes
- Still unclear "how it will be used."
    - A: I want to be able to read the content written in the Japanese project by English speakers with about a day's delay in English machine translation.
        - I want to be able to get hits when searching in English.
        - Social Triggers
    - B: Help Nishio personally continue the translation of "The Intellectual Production of Engineers" which is halfway through the translation into English.
        - Unclear what would help.
        - It's important to think, "If I do this, people will read it."
    - C: Allow English speakers to read the English translation of The Engineer's Guide to Intellectual Production as if it were a book.
        - This isn't a machine translation, it's a reproduction of the table of contents in the Scrapbox Reader.
    - D: Allow non-English speakers to read The Engineer's Art of Intellectual Production by machine translation from the English version.
        - I think this can be done from Scrapbox Reader.
    - E: Writing an expanded edition of The Engineer's Guide to Intellectual Production
        - Talk about Scrapbox, Regroup and Kozaneba, Keichobot
        - I want to connect with past articles
        - I would especially like to write Kozaneba's description in English.
        - Maybe write it in Scrapbox in Japanese, and then translate it into English if the quality is unsatisfactory in machine translation.

What's that? Should we do "book-like navigation with contents in Scrapbox" before machine translation?

![image](https://gyazo.com/f0c5e7b6460222ce91e0d6d661234beb/thumb/1000)


next  [[ScrapboxAutoTrans Development Diary 2022-01-20]]

---
This page is auto-translated from [/nishio/ScrapboxAutoTrans開発日記2022-01-19](https://scrapbox.io/nishio/ScrapboxAutoTrans開発日記2022-01-19) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "CybozuHackathon2019"
---

    - [[Search Technologies of the Future]]
    - [[The difference between "looks like" and "will be next."]]
-----
- This time I made the equivalent of [[view of addition]].
    - What happens if this is changed to [[internal volume caution]]?
        - I want to experiment to see if [[dimensionality reduction caution]] is useful.
    - Network as originally conceived
        - ![image](https://gyazo.com/6648bda7b702085a3c212337ec2041e3/thumb/1000)
    - But this [[degree of similarity]] ("[[Looks like.]]") based structure
            - As I wrote in [[The difference between "looks like" and "will be next."]], it may be beneficial not to base similarity
        - ![image](https://gyazo.com/c31f5e77f82db619a38593bfb2a8f561/thumb/1000)
        - If rewritten so that it is not similarity-based, it would look like this
            - The layer for creating a Key and the "layer for creating a query from the most recent slide to the next slide" are completely different
            - This was confusing because it's a similar form since it currently happens to receive one page of slides as input.
            - There's no necessity for the "most recent page" to represent the context.
            - I guess if you're taking a "page" of indefinite length and converting it to a vector of fixed length, then it's self explanatory.
                - ![image](https://gyazo.com/7c3137f1749202cbd5b200c5de14adca/thumb/1000)

Inconveniences of the created system
- PDFs must first be processed in CUI.
    - `$ ruby pdfs_to_onepage_json.rb in/future_search_technology.pdf > hackathon.json`
- Implemented in Ruby because it was forked from Dr. Masui's code that uses Ruby's Gyazo client even though he is better at Python.
- It's converted from PDF to JPEG with pdftocairo, so even things that inherently contain textual information, like a PDF created from Keynote, are converted to images.
    - In fact, PDFs that have textual information should be able to use that as well.
- Stringed by Gyazo's (internally hitting Google Vision API) OCR
    - Surprisingly, large characters are not OCR'd (probably due to window size limits that look for possible character matches).
    - In cases where a screenshot of a graph or table is pasted in, OCR's advantage is that the text in the image can also be treated as data.
    - However, all numbers in graphs and tables are included in the input data.
    - Humans naturally judge large letters to be important and small letters to be unimportant, but this information is lost when OCR is used.
- Uploading to Gyazo, depending on the Gyazo side and network conditions, may fail, uploading at a rate of one piece per second, so there is a relatively long wait time.
- OCR is running asynchronously on the Gyazo server side, so completion timing is unreadable.
- The resulting JSON file must be imported manually.
    - This can be automated, but my login information needs to be retrieved from the cookie and loaded into the request.
- JSON without OCR information is output when OCR fails because it is not retried when OCR is not taken.
    - I notice after manually importing into Scrapbox that there is no OCR information on it.

how it should be
- If you're on a Mac, you can kick CUI scripts in Automator, and you can put them in the Finder's "Frequently Used Items".
    - Can be activated by dragging and dropping PDFs
- Images containing large text, will they be OCR'd if they are reduced in size?
    - If this is the case, then OCR the slide image after reducing the size of the image, so that letters that are too small will be properly squashed and large letters will be recognized.
- Work hard in Ruby or port it to Python and work hard and retry on errors.
- Create a personal, private project in Scrapbox and import it into Scrapbox automatically.
- Notify when everything is done (so that people don't have to watch the process).

---
This page is auto-translated from [/nishio/CybozuHackathon2019](https://scrapbox.io/nishio/CybozuHackathon2019) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
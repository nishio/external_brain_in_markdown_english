---
title: "pScaffoldNetwork 2022-05-09"
---

- [[Scaffolding Network]] 2022-05-09 #pScaffoldNetwork
MeCab Constrained Parsing
- being hard put to it
- Out-of-range access occurs.
    - Trying to read beyond the end of the suffix sequence
- Cause again unknown.
- In the meantime, if you workaround the program so that it doesn't die, run it all the way to the end.
- However, the notation shaking link is strange.
    - Opening words are indeed common
    - The ending word should also be common, but it's not.
- I took a quick look at the output results, and it doesn't look like the text is corrupted without being restored, so we're making progress.
- Possible common cause of "out-of-range access" and "shaky links"
    - I hear the end is off by one.
        - It makes the out-of-range access and also the end of the notation shake wrong.
    - It doesn't seem to be simply that the last word is missing, the next word is not equal.

For data with large duplicate sentences
- For example, there are several different versions of a sentence after polishing it.
- There's a long common string that spans multiple documents, so I'm assuming that's the keyword.
- solution
    - A large number of common string links will be found between specific sets of documents
    - A: Detect it and reduce the score
    - B: After extracting one page, skip the pages that "the set of pages to be connected" is covered by it so that it is not extracted.
        - I think this will filter out the very long keywords that occur only between cloned sentences, because they won't appear in other documents.
    - C: Change the score calculation formula so that this kind of thing naturally gets a lower score
- To begin with.
    - The keyword scoring is done without distinguishing whether it is an exact match substring or an ambiguous match, but there is a proposal to change that.
        - Now that we don't distinguish between the two, if you get an oddly notated shaky keyword, that's usually a long one, so you'll get a higher score.
            - It's not right to behave better when things get weird, it should not get weird.
        - Even if you do that, the same long string matches will occur in "data that contains repeatedly edited and mis-versioned sentences".
- Test the operation of the "MeCab Constrained Analysis" part using another data set that would have no duplicates.
    - This place is still not working right.

What links to choose?
- Simply score top N proposal on each page.
    - Proposal to exclude the same set of pages linked by the top keywords
    - Proposal to have "already linked pages" and skip if included.
        - Similar to Scrapbox behavior
    - ✅Exclude overlap on strings with top-level keywords
- Add links one at a time, starting with the highest scoring link.
    - Spanning Tree Idea

experimental data proposal
- Imported and published from Kitaro Nishida PDF
    - Introduction to Philosophy
- Import one book from Drucker books
    - This is private.
    - Possibility of not working because of OCR
- Conversion from Scrapbox
    - Conversion candidates in dry-run, check them, and then convert based on them.
        - Put the candidates on file so they can be edited?
- Proposal to crawl through a collection of online columns, etc.

---
This page is auto-translated from [/nishio/pScaffoldNetwork 2022-05-09](https://scrapbox.io/nishio/pScaffoldNetwork 2022-05-09) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
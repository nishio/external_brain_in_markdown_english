---
title: "pScaffoldNetwork"
---

- Experiments in building a [Scaffolding Network
- In [[pLinkSuggest]] we did find common substrings between a "given sentence" and a "large number of pre-parsed documents"
    - This means that in Scrapbox, given a new page, it is equivalent to finding links between that page and other pages
    - On the other hand, it could also be used as a fuzzy cross search within the collection, and I left it wondering which way to go.
- The hypothesis is that it is better to create a "scaffolding network" for "a set of pages that do not yet have links" rather than to find "links between one page and a set of other pages".

pScaffoldNetwork 2022-04-01
- A prototype was created.
    - Import an average of 1000 characters and 300 articles as plain text input.
        - does not look bad
    - I tried to make something publicly available[/nishida-kitaro](https://scrapbox.io/nishida-kitaro) as input.
        - This is not good.
        - Because they don't understand "links that already exist."
        - Chapter headings, etc., added by hand for navigation, are naturally substrings of the carryout, making them links within links.
        - Need process to combine link notation into one token

[[pScaffoldNetwork 2022-04-06]]
- > Creating a scaffolding network from books, done!

2022-04-25
- Using MeCab's Constrained Analysis
    - Created a development environment for Deno.
    - I was able to parse the Scrapbox notation and output the format for MeCab's constrained analysis
    - Scrapbox notation combined into one token
- Flagged not to include in keywords.

- The original data contains nearly identical sentences in different versions, and the long matches are treated as keywords.

- Ability to show what will be updated in a dry-run instead of a sudden destructive update (in progress).
- TODO Support for block notation currently ignored
- TODO notation sway absorption is quite intense and identical, so it would be more satisfactory to loosen it a little more.


memo


- [[pdf2txt]]




---
This page is auto-translated from [/nishio/pScaffoldNetwork](https://scrapbox.io/nishio/pScaffoldNetwork) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
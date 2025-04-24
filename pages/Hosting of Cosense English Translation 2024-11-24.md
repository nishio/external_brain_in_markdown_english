---
title: "Hosting of Cosense English Translation 2024-11-24"
---

from  [[Diary 2024-11-24]]
- [[Hosting of Cosense English translations]]
- [[Quartz]] tried it last time and I don't know why he didn't do it.
    - Maybe the default made too many links in the sidebar?
        - Yes: 2023-11-30  [[Static generation in Quartz from Markdown and serve in Github Pages]]
    - And the hosting is ready.
        - I don't know why I'm not doing this on an ongoing basis.
            - I wonder if the English translation system was in the process of being created after testing it with Japanese data to make sure it would work.
            - It would be nice to have a "list of pages created during this period" view for this kind of thing.

[/villagepump/workroom2024-11-24](https://scrapbox.io/villagepump/workroom2024-11-24)→ [[Machine Translated Scrapbox Published in Quartz on 2024-11-24]]
<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>
Summary: The
- Issue:.
    - The automatic import of data after English translation from Scrapbox sometimes fails, making Scrapbox importing a hassle.
    - The process of publishing Scrapbox data via Markdown using Quartz is under consideration.
    - GitHub Actions and repository management is becoming more complex.
- Attempts:.
    - Scrapbox → JSON → English translation JSON → Markdown → publish on Quartz.
    - Performed Quartz setup and error handling.
    - The quality of English translations needs to be improved and error handling needs to be automated.
- Conclusion:.
    - Basic publishing process works, but needs further improvement, including translation quality and error handling.

2024-11-25

2024-12-08
<img src='https://scrapbox.io/api/pages/nishio-en/o1 Pro/icon' alt='o1 Pro.icon' height="19.5"/>Summary: The
Initially, a Markdown→Quartz→GitHub Pages pipeline will be established in a small-scale test environment, aiming for stable operation of translation and UI improvements. After that, we will start working on individual issues such as translation, link processing, and Quartz settings improvement.

Specific next steps: 1.
- Small Test Setup:.
    - Limited to the target Scrapbox pages, the series of steps from Markdown conversion to Quartz build to GitHub Pages deployment is performed.
    - Find and record import failures, translation errors, and UI problems.

- Translation pipeline stabilization
    - Reviewed GitHub Actions jobs and improved error handling and retry conditions to ensure that the automatic English translation portion works stably.
    - Consider a mechanism to add meta-information when generating Markdown so that the UI can reflect that the translated text is a machine translation.

- Quartz UI and link setting improvements:.
    - Customize the Quartz side of the site to support Wikilinks and reduce the number of internal links.
    - Optimize settings so that unnecessary links and huge link lists are not generated.

- Build Size/Performance Measures:.
    - Consideration was given to eliminating unnecessary pages and discarding links so that the generated material would not become too large.
    - Organized Markdown generation rules and file structure to keep build time and size small.

- Phased Expansion & Evaluation:.
    - Once problems are cleared in small-scale testing, increase the number of pages covered and expand the functionality and page structure.
    - Scale up step by step while regularly checking deliverables and evaluating translation quality and UI improvement effects.

These steps will gradually improve stability, readability, and convenience, and ultimately create a multilingual publishing environment that freely utilizes Scrapbox data.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
What is the relationship with [/villagepump/post-translation-improvement-issues](https://scrapbox.io/villagepump/post-translation-improvement-issues)?

---
This page is auto-translated from [/nishio/Cosense英訳のホスティング2024-11-24](https://scrapbox.io/nishio/Cosense英訳のホスティング2024-11-24) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
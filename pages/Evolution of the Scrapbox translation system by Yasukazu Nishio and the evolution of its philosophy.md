---
title: "Evolution of the Scrapbox translation system by Yasukazu Nishio and the evolution of its philosophy"
---

- [[Cosense updates are converted to Markdown daily and entered into GitHub]] ようになったので、それをgit cloneすれば当然[[Devin.ai]]はそれを読めるよね、ということでまとめてもらった<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>

prompt

```
Clone https://github.com/nishio/external_brain_in_markdown
This is a note from the author
From these many files
pUnnamed, pContinuousTranslation, pScrapboxAutoTrans, pEnglish, nishio-en, automatic translation, Quartz, mem.nhiro.org, Obsidian, machine translation
Search for keywords such as "search" and read the hits, then create a summary report in Markdown.

This will be a summary of the author's activities over several years, so it will be of reasonable length.
The summary should include a chronological "transition of ideas and implementations made at each point in time" and an overall summary that is not based on a time line.
It might be a good idea to make a detailed summary and then put that overview on your mind.

`[link]` is a link to a page titled `link`. In the summary, use the `[link]` notation to describe the page you referred to, if necessary.
```


ver. 1

# Overview
.

For several years, Yasukazu Nishio has been developing and refining a system for multilingualizing his Scrapbox content (mainly into English). In this report, we will organize the evolution of the system and the evolution of its ideology in chronological order, aiming to provide an overall picture of the project.

Nishio's translation system has evolved from a simple machine translation tool to a continuously updated knowledge-based multilingualization system. In the process, he has addressed a variety of technical and conceptual issues, such as moving from DeepL to GPT-based translation, maintaining link structures, and how to manage multilingual content.

This project has evolved through name changes from "pUnnamed" to "pScrapboxAutoTrans" to "pContinuousTranslation" to "pEnglish" to "nishio-en" and ultimately aims to make Nishio's "external brain" multilingual The name "nishio-en" has evolved over the years.

# Changes in Philosophy and Implementation over Time
.

## Initial conceptual phase (first half of 2021)

This is the period in which the initial conception of the English-language adaptation of Scrapbox content was formed.

- Thought: Desire to bring Scrapbox content written in Japanese to English-speaking readers
- Implementation: No concrete implementation yet, still in the conceptual stage.
- Reference: [[Scrapbox Englishization Plan]], [[English Transmission Support]].

## Experimental period (August-December 2021): pUnnamed/pScrapboxAutoTrans

During this period, experiments with translating Scrapbox content using actual machine translation began.

- Thought:.
    - Efficiently convert Japanese content into English using machine translation
    - Expanding the perspective from "I am the reader" to "global reader
    - Exploring the possibility of permanent archiving through static site generation
- Implementation:.
    - DeepL Building a translation system using API
    - Experimenting with automation using GitHub Actions
    - Implementation of translation cache for greater efficiency
- Reference: [[ScrapboxAutoTrans Development Diary 2021-10-30]], [[ScrapboxAutoTrans Development Diary 2021-12-28]].

## Development Phase (January 2022 - March 2023): pScrapboxAutoTrans
.

This period saw the full-scale development and refinement of the translation system.

- Thought:.
    - Explore ways to view translated content
    - Concept of a browsing system at mem.nhiro.org
    - Consideration of the balance between translation cost and effectiveness
- Implementation:.
    - Stabilization of the translation system
    - Added language judgment function (lines not in Japanese are not translated)
    - Improved error handling
- Reference: [[ScrapboxAutoTrans Development Diary 2022-01-12]], [[ScrapboxAutoTrans Development Diary 2022-01-17]], [[pScrapboxAutoTrans2023-03-25]].

## Continuous Translation Period (April-May 2023): pContinuousTranslation

It was during this period that the concept of "Continuous Translation" was clarified and the system began to stabilize.

- Thought:.
    - Applying Continuous Integration/Delivery (CI/CD) concepts to translation
    - Emphasis on automation, frequent updates, rapid feedback, and quality assurance
    - Explore ways to manage multilingual content (introduction of en/en/jaen icons)
- Implementation:.
    - Stable operation of automated translation once a day by GitHub Actions
    - Significant improvement in translation speed through parallel processing (concurrent.futures)
    - Implement pre-translation processing to preserve link structure
- Reference: [[pContinuousTranslation2023-04-27]], [[pContinuousTranslation2023-05-06]], [[jaen]].

## Translation Methodological Transition (June-November 2023): pContinuousTranslation→pEnglish

During this period, the transition from DeepL to GPT-based translation was considered and implemented.

- Thought:.
    - Expansion of the concept from "translation" to "AI-assisted multilingual content generation
    - Exploration of the possibility of LLMs understanding the content and rewriting it in English, rather than just translating it.
    - Rethinking the Balance between Translation Quality and Efficiency
- Implementation:.
    - Transition from DeepL to GPT-3.5
    - Experiments with translation chains using LangChain
    - Seek linkage with vector search
- Reference: [[pContinuousTranslation2023-06-01]], [[Change Scrapbox auto-translation from DeepL to GPT]]

## Integration and development period (Dec 2023-present): pEnglish→nishio-en

During this period, the translation system stabilized as "nishio-en" and further development was sought.

- Thought:.
    - Expansion of the concept from "Yasukazu Nishio's Scrapbox" to "Yasukazu Nishio's External Brain
    - Introducing the perspective of blog text generation rather than translation
    - Explore new browsing systems utilizing Quartz, Obsidian, etc.
- Implementation:.
    - Stable operation of nishio-en projects
    - Reading and impression generation of English content by a virtual persona (Kai Harada)
    - Experimentation with static site generation using Quartz
- Reference: [[pEnglish]], [[pEnglish2023-12-12]], [[pEnglish2023-12-13]], [[For visiter of /nishio-en]].

# Overall summary not based on time frame
.

## Key Technical Issues and Solutions
.

1.### Preserve link structure
.
    - Challenge: Need to retain Scrapbox's unique link structure after translation
        - Solution.
            - Create mapping table by translating link titles first
        - Extract link notation and replace before translation
            - Detection of similar links by vector search

- 2.Managing Multilingual Content.
        - Challenge: Managing mixed Japanese/English/Translated English content
    - Solution.
        - Language indication by en/en/jaen icons
            - Translation control with indicators such as enjabelow

- 3.Balance between translation quality and efficiency.
        - Challenge: Need to translate large amounts of content to high quality
    - Solution.
        - Cache system to avoid duplicate translations
            - Increased translation speed through parallel processing
        - Quality Improvements from DeepL to GPT

4.### Build a browsing system
.
    - Challenge: Need an effective system for viewing translated content
        - Solution.
            - Building mem.nhiro.org
        - Consider static site generation using Quartz, GitHub Pages, etc.

## Project's ideological evolution
.

1.### Change in the image of the reader
.
    - Expansion from "I am the reader" to "global audience
        - Emphasis on knowledge sharing with non-Japanese speakers

2.### Extension of translation concept
.
    - Development of the concept from simple "machine translation" to "continuous translation (CT)
        - Further expansion to "AI-assisted multilingual content generation

3.### Evolution of Knowledge Management Systems
.
    - Extending the concept from "Scrapbox" to "external brain"
        - Emphasis on access to knowledge in multiple languages and perspectives

4.### Technology Selection Philosophy
.
    - Comparison and selection of "DeepL's terminology control" vs. "GPT's natural translation"
        - The metaphor of "driving the right way on a set path" vs. "driving on a path you don't quite understand yet."

## Future Prospects
.

1.### Development of GPT-based translation
.
    - Realize more natural and contextualized translations
        - Direction of "AI writes about its contents in English" instead of translation.

2.### Diversification of browsing systems
.
    - Providing a new browsing experience with Quartz, Obsidian, and others
        - GitHub Pages for persistent archiving

3.### Interacting with AI readers
.
    - AI reads translated content and generates questions and feedback
        - Exploring new forms of dialogue between author and reader (human and AI)

4.### Multilingualization of the external brain
.
    - Building a knowledge sharing system that transcends language barriers
        - Integrate thinking and knowledge production in multiple languages

# Conclusion
.

The evolution of Yasukazu Nishio's Scrapbox translation system has been more than just a technological development; it has involved deep contemplation of knowledge sharing and multilingual communication. The journey that began with "pUnnamed" and ended with "nishio-en" was also a process of exploring new forms of knowledge production through collaboration between AI and humans.

This project continues to evolve toward a larger vision of multilingualization and globalization of the "external brain" concept, in addition to solving technical issues. It is expected that this system will continue to evolve further along with the development of AI technology, showing a new form of knowledge sharing that transcends language barriers.

---

prompt

```
 [Multilingual development based on machine-friendly English] and [pIntEn] are the sources. Also, the migration to GPT3.5 should not have been done yet after all. nishio-en still has a working migration at DeepL. After that, they should be looking for a different form of dissemination, with mem.nhiro.org and Quartz, due to the limitations of what they do with Scrapbox. Find out more.
```


ver. 2

# Overview
.

For several years, Yasukazu Nishio has been developing and refining a system for multilingualizing his Scrapbox content (mainly into English). In this report, we will organize the evolution of the system and the evolution of its ideology in chronological order, aiming to provide an overall picture of the project.

Nishio's translation system has evolved from a simple machine translation tool to a continuously updated knowledge-based multilingualization system. In the process, he has addressed a variety of technical and conceptual issues, such as moving from DeepL to GPT-based translation, maintaining link structures, and how to manage multilingual content.

This project has its origins in the 2019 concept of "multilingual development based on machine-friendly English" and the "pIntEn" (Project for the Englishization of Engineers' Intellectual Production Techniques), and has evolved through the transition from "pUnnamed", "pScrapboxAutoTrans", to " pContinuousTranslation", "pEnglish", and "nishio-en", and ultimately aims to make Nishio's "external brain" multilingual.

# Project Origins
.

The origins of Nishio's translation system can be traced back to the concept of "multilingual deployment based on machine-friendly English" conceived in 2019. The concept proposed the following process:

1. Japanese text → Machine translation → English text
2. proofreading of English texts → machine-friendly English texts
3. machine-friendly English text → machine translation → various languages

Behind this concept was the insight that "when machine translation from Japanese to English fails to make sense, it is often the original Japanese text that is at fault. The idea is to improve the quality of machine translation by converting Japanese sentences with long or complex engagements into simple English sentences.

Another source is "pIntEn" (Project for English Translation of Engineers' Intellectual Production Techniques). This was a project to translate Nishio's book "The Art of Intellectual Production of Engineers" into English, in which a combination of machine translation and human proofreading was actually tested. The experience gained from this project was later used in the development of a large-scale automated translation system.

From these initial efforts, Nishio went on to develop a more systematic translation system through the "Scrapbox Englishization Plan.

# Changes in Philosophy and Implementation over Time
.

## Initial conceptual phase (first half of 2021)

This is the period in which the initial conception of the English-language adaptation of Scrapbox content was formed.

- Thought: Desire to bring Scrapbox content written in Japanese to English-speaking readers
- Implementation: No concrete implementation yet, still in the conceptual stage.
- Reference: [[Scrapbox Englishization Plan]], [[English Transmission Support]].

## Experimental period (August-December 2021): pUnnamed/pScrapboxAutoTrans

During this period, experiments with translating Scrapbox content using actual machine translation began.

- Thought:.
    - Efficiently convert Japanese content into English using machine translation
    - Expanding the perspective from "I am the reader" to "global reader
    - Exploring the possibility of permanent archiving through static site generation
- Implementation:.
    - DeepL Building a translation system using API
    - Experimenting with automation using GitHub Actions
    - Implementation of translation cache for greater efficiency
- Reference: [[ScrapboxAutoTrans Development Diary 2021-10-30]], [[ScrapboxAutoTrans Development Diary 2021-12-28]].

## Development Phase (January 2022 - March 2023): pScrapboxAutoTrans
.

This period saw the full-scale development and refinement of the translation system.

- Thought:.
    - Explore ways to view translated content
    - Concept of a browsing system at mem.nhiro.org
    - Consideration of the balance between translation cost and effectiveness
- Implementation:.
    - Stabilization of the translation system
    - Added language judgment function (lines not in Japanese are not translated)
    - Improved error handling
- Reference: [[ScrapboxAutoTrans Development Diary 2022-01-12]], [[ScrapboxAutoTrans Development Diary 2022-01-17]], [[pScrapboxAutoTrans2023-03-25]].

## Continuous Translation Period (April-May 2023): pContinuousTranslation

It was during this period that the concept of "Continuous Translation" was clarified and the system began to stabilize.

- Thought:.
    - Applying Continuous Integration/Delivery (CI/CD) concepts to translation
    - Emphasis on automation, frequent updates, rapid feedback, and quality assurance
    - Explore ways to manage multilingual content (introduction of en/en/jaen icons)
- Implementation:.
    - Stable operation of automated translation once a day by GitHub Actions
    - Significant improvement in translation speed through parallel processing (concurrent.futures)
    - Implement pre-translation processing to preserve link structure
- Reference: [[pContinuousTranslation2023-04-27]], [[pContinuousTranslation2023-05-06]], [[jaen]].

### Note
: Although the decision to migrate from DeepL to GPT3.5 was made on June 17, 2023, the Nishio-en project is still running a DeepL-based translation system (as of March 2025).

## Translation Methodological Transition (June-November 2023): pContinuousTranslation→pEnglish

During this period, the transition from DeepL to GPT-based translation was considered and experimented with. However, a complete transition has not been achieved.

- Thought:.
    - Expansion of the concept from "translation" to "AI-assisted multilingual content generation
    - Exploration of the possibility of LLMs understanding the content and rewriting it in English, rather than just translating it.
    - Rethinking the Balance between Translation Quality and Efficiency
- Implementation:.
    - Study and experiment with migration from DeepL to GPT-3.5
    - Experiments with translation chains using LangChain
    - Seek linkage with vector search
- Assignment:.
    - Consideration of alternatives to the terminology control feature of DeepL (controlling for specific words to have specific translations)
    - Ensure stability and consistency of GPT-based translations
- Reference: [[pContinuousTranslation2023-06-01]], [[Change Scrapbox auto-translation from DeepL to GPT]]

## Integration and development period (Dec 2023-present): pEnglish→nishio-en

During this period, the translation system has stabilized as "nishio-en" and further development is being explored. Also, feeling the limitations of Scrapbox, we are considering transmitting on new platforms such as mem.nhiro.org and Quartz.

- Thought:.
    - Expansion of the concept from "Yasukazu Nishio's Scrapbox" to "Yasukazu Nishio's External Brain
    - Introducing the perspective of blog text generation rather than translation
    - Exploring new platforms to push the boundaries of Scrapbox expression
- Implementation:.
    - Stable operation of nishio-en project (still using DeepL based translation)
    - Reading and impression generation of English content by a virtual persona (Kai Harada)
    - Static hosting by mem.nhiro.org
    - Experimentation with static site generation using Quartz (temporarily pending)
- Assignment:.
    - Addressing limitations of Scrapbox representation (e.g., lack of breadcrumbing)
    - Prevent blurred focus with Quartz's infinite customizability
    - Burden of parallel operation of multiple platforms
- Reference: [[pEnglish]], [[pEnglish2023-12-12]], [[pEnglish2023-12-13]], [[For visiter of /nishio-en]], [[mem.nhiro.org]].

# Overall summary not based on time frame
.

## Key Technical Issues and Solutions
.

1.### Preserve link structure
.
    - Challenge: Need to retain Scrapbox's unique link structure after translation
        - Solution.
            - Create mapping table by translating link titles first
        - Extract link notation and replace before translation
            - Detection of similar links by vector search

- 2.Managing Multilingual Content.
        - Challenge: Managing mixed Japanese/English/Translated English content
    - Solution.
        - Language indication by en/en/jaen icons
            - Translation control with indicators such as enjabelow

- 3.Balance between translation quality and efficiency.
        - Challenge: Need to translate large amounts of content to high quality
    - Solution.
        - Cache system to avoid duplicate translations
            - Increased translation speed through parallel processing
        - Quality Improvements from DeepL to GPT

4.### Build a browsing system
.
    - Challenge: Need an effective system for viewing translated content
        - Solution.
            - Building mem.nhiro.org
        - Consider static site generation using Quartz, GitHub Pages, etc.

## Project's ideological evolution
.

1.### Change in the image of the reader
.
    - Expansion from "I am the reader" to "global audience
        - Emphasis on knowledge sharing with non-Japanese speakers

2.### Extension of translation concept
.
    - Development of the concept from simple "machine translation" to "continuous translation (CT)
        - Further expansion to "AI-assisted multilingual content generation

3.### Evolution of Knowledge Management Systems
.
    - Extending the concept from "Scrapbox" to "external brain"
        - Emphasis on access to knowledge in multiple languages and perspectives

4.### Technology Selection Philosophy
.
    - Comparison and selection of "DeepL's terminology control" vs. "GPT's natural translation"
        - The metaphor of "driving the right way on a set path" vs. "driving on a path you don't quite understand yet."

## Platform Evolution
.

1.### Limitations of Scrapbox and the search for a new platform
.
    - Issue: Limitations of Scrapbox representation (e.g. lack of breadcrumbing)
        - Solution.
            - Static hosting by mem.nhiro.org
        - Experimentation with static site generation using Quartz
            - GitHub Pages for persistent archiving

- 2.Multi-platform integration.
        - Challenge: Burden of managing and updating information on multiple platforms
    - Solution.
        - Scrapbox → JSON → English translation of JSON → Markdown → Quartz publication
            - Phased transition through parallel operations
        - Reduce update burden through automation

## Future Prospects
.

1.### Development of GPT-based translation
.
    - Realize more natural and contextualized translations
        - Direction of "AI writes about its contents in English" instead of translation.
    - Realization of full migration from DeepL to GPT-3.5

2.### Diversification of browsing systems
.
    - Providing a new browsing experience with Quartz, Obsidian, and others
        - GitHub Pages for persistent archiving
    - Seeking ways of expression beyond the limits of Scrapbox

3.### Interacting with AI readers
.
    - AI reads translated content and generates questions and feedback
        - Exploring new forms of dialogue between author and reader (human and AI)

4.### Multilingualization of the external brain
.
    - Building a knowledge sharing system that transcends language barriers
        - Integrate thinking and knowledge production in multiple languages

# Conclusion
.

The evolution of Yasukazu Nishio's Scrapbox translation system, which originated in 2019 with the concept of "multilingual deployment based on machine-friendly English" and the "pIntEn" project, was not merely a technological development, but involved deep thought about knowledge sharing and multilingual communication. This journey, starting with "pUnnamed" and ending with "nishio-en," was also a process of exploring new forms of knowledge production through collaboration between AI and humans.

Currently, the full transition from DeepL to GPT-3.5 has not yet been achieved, but the concept of translation itself is being extended from "machine translation" to "AI-assisted multilingual content generation". In addition, the limitations of Scrapbox are being felt, and new platforms such as mem.nhiro.org and Quartz are being explored for dissemination.

This project continues to evolve toward a larger vision of multilingualization and globalization of the "external brain" concept, in addition to solving technical issues. It is expected that this system will continue to evolve further along with the development of AI technology, showing a new form of knowledge sharing that transcends language barriers.


---
This page is auto-translated from [/nishio/西尾泰和氏のScrapbox翻訳システムの進化と思想の変遷](https://scrapbox.io/nishio/西尾泰和氏のScrapbox翻訳システムの進化と思想の変遷) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
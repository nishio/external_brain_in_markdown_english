---
title: "Consideration of Englishization by AI"
---

from  [[Diary 2023-09-18]]
Consideration of Englishization by AI
2023-09-19
![image](https://gyazo.com/f0eea737593e99625997a471e39d9221/thumb/1000)
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I write daily sentences on a Japanese wiki, which are automatically machine-translated into English. Sometimes I am not satisfied with its quality. Now, the hurdle of resolving that dissatisfaction is high. I realized that it is because the automatic machine translation causes the English version to be overwritten the next time I revise the Japanese version. What should we do?
<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>The following suggestions are made to address the quality issues that have arisen in translating the Japanese wiki content into English:
- Stop synchronization: Consider temporarily stopping the automatic synchronization of the Japanese and English versions. This will ensure that updating the Japanese version will not overwrite the English version.
- Manual translation improvement: Once the translation is done automatically, it is a good idea to have a native English speaker or expert check and correct the translation.
- Review translation software: Consider reviewing the machine translation tools and services you are using. There have been many advancements in recent years, and there may be tools that produce higher quality translations.
- Version control: It is recommended to implement a system that manages the Japanese and English versions of the content separately, so that each can be updated independently.
- Implement a notification system: By setting up a system to notify the person in charge of the English version and the translator when changes are made to the Japanese version, the English version can be updated and re-translated as necessary.
Ultimately, it is important to find a balance between the convenience of automated translation and the quality of the translation.

## righteous argument of righteous argument!

- Stop targeting all pages for translation now.
- Take the mechanism of "Make the page indicated by the link the target of AI writing" by [[Pioneer mode]] and make "Make the page indicated by the link the target of translation".
- Record the time of conversion as you do now with the AI-generated page?
    - The conversion time of the original Japanese, the start time of conversion to English, the end time of conversion to the English version, and the writing time to the English version, all different
    - To detect if any modifications have been made in the English version after the translation is written, the English version writing time must be used as a basis.
- Information on what kind of modifications you might want to make is not accumulated at this time.
    - That's because I created the word-substitution modification mechanism first.
        - What can be achieved with it will be written there, but what can't be achieved won't be written.
    - Maybe a bunch of superficial "I want this word to be this" or "this is how I want it to be sometimes translated, but this is how I want it to be", and then the deeper semantic stuff that can't be expressed in that way becomes clear.
        - Example of surface layer
            - Don't change "Yasukazu Nishio" to "Yasukazu Nishio. Make it "NISHIO Hirokazu.
                - Don't do A to B, do C." Structure
                    - There are two ways to translate the Japanese side: A to C and then B to C on the translated English text.
                    - [[create /villagepump/ScrapboxTranslator v2]].
                    - I translate the title before I give it to you.
        - Example of deep layer
                - [[Reflections on "The Reader is Me]]

Additions 9/19
- A concept that is translated and "not good in that translation" is a meaningful chunk of a concept, so is it correct that it is a page title?
    - may

The expression "[[Anglicized]]" has the nuance of "not necessarily a translation."

Fine-tuning GPT3.5 to generate English?
- [[Fine-tuning is done after enough Prompt Engineering]].

9/20
There's also a way to do GPT 3.5 fine tuning.
- [[Translation Examples]]
---
This page is auto-translated from [/nishio/AIによる英語化の考察](https://scrapbox.io/nishio/AIによる英語化の考察) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "pContinuousTranslation2023-04-27"
---

prev [[pScrapboxAutoTrans2023-04-18]]
- 2023-04-27
    - At the end of the last issue, we confirmed that the once-a-day automatic translation is working stably.
    - Previously, we felt it would be better to change the name and tentatively titled it [[pUnnamed]], but we have reverted to the traditional [[pScrapboxAutoTrans]].
    - I thought that the point at which this "[[continuous translation]]" was achieved was a break in the times.
    - [[pContinuousTranslation]]

from  [[Continuous translation]]
(DeepL) [[Continuous Integration]] and [[Continuous Delivery]] share common patterns of automation, frequent updates, rapid feedback, and quality assurance. By applying these patterns to the domain of translation and international communication, we can propose a new concept of "continuous translation.
- Continuous Translation (CT), like CI/CD, is a system in which translation and cross-cultural communication are constantly updated, improved, and refined using automated processes. the main components of Continuous Translation are
        - Automation: Utilizes machine learning and AI-powered translation tools to automatically translate content as it is created and updated, minimizing manual intervention.
            - done<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
        - Frequent updates: Implement a system where translations are continually updated to reflect changes in source content so that international audiences always have access to the latest information.
            - done<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
        - Rapid feedback: The incorporation of feedback mechanisms (e.g., suggestions from users, opinions of professional translators, etc.) allows for quick identification and correction of translation errors and inconsistencies, resulting in higher quality translations over time.
            - Ah, I see. This is so hard to achieve with Scrapbox.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
        - Quality Assurance Establish a process to automatically test translations and verify accuracy and fluency before delivering them to end users.
            - I wonder if "automatically test translations" means that the LLM reads them and gives feedback on what he/she doesn't understand?<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
        - Collaboration: Developers, translators, and other stakeholders work together to create an environment that seamlessly integrates the translation process into the content creation workflow.
            - This is the same developer and translator now, so I wouldn't worry about it.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
- Ongoing translation enables organizations to efficiently deliver up-to-date, accurate, and high-quality translated content to global audiences, improving communication, enhancing user experience, and strengthening international relationships.
    - Efficiently deliver up-to-date, accurate, high-quality translated content to a global audience" sounds like a good mission.

This of [[pScrapboxAutoTrans2023-04-18]].
- > I wish I could quantitatively determine if it's getting better.
- Considering that continuous execution is now possible and we are in the quality improvement phase, it is strange that there are no [[metrics]] to measure the quality (software engineering context).

-----
2023-04-27
- I wrote [Polis Experience Report: Should we investigate the causes of terrorism?
- I noticed that there are some misalignment of icons and such, so I better go read it and write down what kind of problems and Possible solutions I have.

Title.
- `Polis Experience Report: Do you want to investigate the causes of terrorism?`
- Do you want to do it? It's like, "Do you want to do it?
    - Japanese tends to omit the subject, especially in titles with a limited number of characters.
- `Polis Experience Report: Should we investigate the causes of terrorism?`

Icon Location
- ![image](https://gyazo.com/8c26d2dce272cfd3573c9463bb3ebff4/thumb/1000)
- I guess this "putting an icon at the beginning" and "putting an icon at the end" is a kind of syntax.

Link
- ![image](https://gyazo.com/b0cbdfcb20198372aa4d1cb59af89e9e/thumb/1000)
- why?
- Long links are broken up by spaces in the middle of the link.
- `[detail https://scrapbox.io/nishio/Polis:%E3%83%86%E3%83%AD%E3%81%AE%E5%8E%9F%E5%9B%A0%E7%A9%B6%E6%98%8E%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6%E3%81%AE%E8%AD%B0%E8%AB%96#643d39f4aff09e0000dd6581]`

translation
- ![image](https://gyazo.com/479f8baa670a2425d72bb765f0c5f4b6/thumb/1000)
- ![image](https://gyazo.com/38fdf5e75dfbd7dabedabf70e39d320f/thumb/1000)

These are mistakes that can be understood without reading the English text.

Then view the English text at DeepL
- No? - No. Surprisingly, that's not a problem.
- Where I thought it was strange, I checked and the English-Japanese translation failed.

fixed
- run local_batch
- Check the results when you return from English conversation school.

It's not over at all.
:

```
  9%|███████▍                                                                              | 1279/14848 [2:45:52<21:35:30,  5.73s/it]
  503 Server Error: Temporary Error for url: https://api.deepl.com/v2/translate
 14%|███████████▊                                                                          | 2037/14848 [4:19:43<77:17:07, 21.72s/it]
 ('Connection aborted.', ConnectionResetError(54, 'Connection reset by peer'))
 26%|██████████████████████▎                                                               | 3862/14848 [7:05:29<13:20:20,  4.37s/it]
```

The translation ran for 3 hours, with an estimate of 15 hours remaining (this was written when I got home).
- (It's finally running for 7 hours and showing 13 hours remaining.)
- The whole retranslation is rare and it's due to the fact that it's not fast enough, but I don't know what to do with it.
policy
- Either way, at the current pace, we're going to run into periodic translations, so we'll have to stop for a while.
- Implement parallelization and stop the current translation and replace it.


<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>The code below sends a request to the API of the translation service. The current code below is slow because API access is serialized. Please parallelize it to make it faster.
python

```
for page in pages:
    for line in lines:
        line["text"] = translate(line["text"])
```

<img src='https://scrapbox.io/api/pages/nishio-en/gpt-4/icon' alt='gpt-4.icon' height="19.5"/>As you have requested, you can use Python's concurrent.futures library to parallelize and accelerate requests to the translation API. Sample code is shown below.
python

```
import concurrent.futures

def translate_line(line):
    return {"text": translate(line["text"])}

# Parallelize translation requests
with concurrent.futures.ThreadPoolExecutor() as executor:
    for page in pages:
        # Send translation request for each line
        translated_lines = list(executor.map(translate_line, lines))
        
        # Restore translated lines to original list
        for i, translated_line in enumerate(translated_lines):
            lines[i].update(translated_line)
```

Convenience

:

```
cache length: 273667
 40%|████████████████████████████████████████████████████▏                                                                            | 6003/14848 [18:22<4:18:18,  1.75s/it]503 Server Error: Temporary Error for url: https://api.deepl.com/v2/translate
 50%|████████████████████████████████████████████████████████████████▊                                                                | 7461/14848 [38:26<1:00:26,  2.04it/s]503 Server Error: Temporary Error for url: https://api.deepl.com/v2/translate
 51%|██████████████████████████████████████████████████████████████████                                                               | 7606/14848 [41:43<1:25:02,  1.42it/s]503 Server Error: Temporary Error for url: https://api.deepl.com/v2/translate
100%|██████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████| 14848/14848 [53:34<00:00,  4.62it/s]
total 29370658 no_cache 1581996 ratio 0.05386314463911568
translate: 3218.0509019168094
```

Oh, the rest was done in less than an hour.
- ![image](https://gyazo.com/3697e4b0198c4e52445b0f798f5f64a7/thumb/1000)
- About 3,000 yen.

next [[pContinuousTranslation2023-06-01]]


---
This page is auto-translated from [/nishio/pContinuousTranslation2023-04-27](https://scrapbox.io/nishio/pContinuousTranslation2023-04-27) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
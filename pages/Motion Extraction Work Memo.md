---
title: "Motion Extraction Work Memo"
---

- [[Motion Extraction]]
Just rebooted after a system update, so note from nothing.
- Open the project directory in a terminal
    - I'm having a hard time deciding whether to separate the repositories or not, but I'm going to create a subdirectory in an existing project.
    - I named him ugoki.
- vscode startup
    - `$ source venv/bin/activate`
    - `$ pip install mecab-python3==0.996.5`
    - `$ pip freeze > requirements.txt`
    - Oh, I could use this too.
        - `$ pip install -e git+https://github.com/nishio/rich_tokenizer#egg=rich_tokenizer`
- Create logs/find_ugoki.py for now
    - Extract the human speech part from the appropriate log file rich_tokenizer.tokenizer(text)
        - I'd like to test, test, input, voice, input, since there are a lot of people who say, `[Ah, it would be, nice, if, you could, use, this, system, with, voice, input, so, I'd, like, to, test, voice, input, on]`.
        - Incidentally, extracted keywords: {'voice': 100, 'voice input': 80, 'ah-ko system': 70, 'people': 39}
            - It's not good enough to have filler in it, but it's not the same as this goal, so I'll hold off.
:

```
In [20]: for x in xs:
    ... : if x.feature.startswith("verb"):.
    ...:         print(x, x.feature)
    ...: 
    ...: 
Use verb,independent,*,*,one-step,continuous,usable,tsukae,tsukae
say verb,independent,*,*,5dan,wagyo urinative particle,basic form,say,iu,iu
There is verb,independent,*,*,one-step,basic form,there are,il,il
Shi verb, self-supporting,*,*,sa variant, suru, continuous form, to do, shi, shi
mi verb, non-self-standing,*,*,one-stanza, continuous form, miru, mi, mi
思い verb, independent,*,*,五段・ワ行促音便,連用形,思う,オモイ,オモイ
```

        - The only one of these that sounds like a good keyword is "use".
        - I could simply filter on a single verb word, but the fact that it is a form of "it would be nice to use" is highly valued, and even if "to do" by itself is not good, if it were "to test" it would be a good keyword, so I would incorporate the surrounding several words into the feature.
- [[ppoi]]  [[ppoi improvement plan]]
    - Rather than using it as is, let's edit it and use it.
    - The naming of ppoi, now that I think about it, is not so interesting.
    - This assumes there's one case per line in unknown.txt, but I'd like to make that from the raw log data.
        - I made it.
        - Pluggable mechanism for user-defined unknown generation
    - Tapped interactive, but learning ran and error
        - Huh? Why do you need to run the study?
        - Just call it in _get_scored_lines.
        - I'd put calling this before learning in the "features we'd like to add", but I'm not sure if it's been implemented yet.
    - I'm assuming that what's in the Unknown is a one-line string.
        - It's easy to be an object here.
        - Let's use JSON when exporting to teacher data.
    - After all, it's better to have the initialization hit first.
:

```
Right now I'm taking a walk and using my AirPods for voice input.
0.1667
negative(z), neutral(x), positive(c), quit(q)>z
Right now I'm taking a walk and using my AirPods for voice input.
1.1429
negative(z), neutral(x), positive(c), quit(q)>z
```

- Active learning is now working.
    - I'd like to see "do X" cut out all together, and "no X" included up to "no."
    - Take a walk." "Do a test."
    - Not enough." "Not enough."
- For multi-word cutouts, either generate at the candidate stage
- It was surprisingly easy.
:

```
>>> get_ugoki("If you want to do it with audio, the system should repeat back with audio only and not look at the screen.")
(0.99963593, 'repeat back with audio only')
(0.9981591, 'repeat back')
(0.9901821, 'Should be in the system')
(0.95455027, 'would like to')
(0.9340714, 'do')
```


I noticed that the new method of extracting keywords that include verbs, if we simply connect them, the number of keywords extracted will naturally increase, and then all the places that require a certain number of keywords to be extracted will be triggered earlier than they are now.
    - [[Keyword appearance speed]]
- Never mind, we decided to integrate.

done
- [[Conversation log: testing new features]]

I decided to play what I could on a rule basis, such as particles appearing on the boundaries.


---
This page is auto-translated from [/nishio/動きの抽出作業メモ](https://scrapbox.io/nishio/動きの抽出作業メモ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "pIntEn Lost motivation to translate"
---

from  [[Project for English-language intellectual production techniques for engineers (-20190522)]]
pIntEn Lost motivation to translate
2019-02-20
- I've been thinking "I have to translate" for the past few days, but I'm not feeling motivated to do it.
- Learning by observing the process of intellectual production is also the goal of this project
- Use one pomodoro to write a commentary so that your future self can read and understand what the current situation is.
- In addition, I am at a familiar Internet cafe.
- I had an opportunity to present at a conference on the morning of 2/15, so I wanted to have at least chapter 0 released by then, so I allocated time for that.
- To begin with, 2/5 [[20190205KJ method experiment by Mr. Tachikawa]] 2/6 Visit to a certain company 2/7 Attendance at a certain committee meeting, which has been taking up a lot of my time since the second week of February.
- Originally, the goal of "finishing the translation by the end of March" was a stretch goal that was somewhat difficult to set.
- I dared to stretch it in the OKR sense.
- We gradually shortened the scheduled completion date and somehow managed to finish by the end of March.
- That's where the e-book conversion process took up a lot of my time.
    - ![image](https://gyazo.com/17dad7540c8ff4715a6d5cd1d2b18fd7/thumb/1000)
    - The scheduled end date was shifted back one month.
- First of all, this is one "cause of demotivation."
- One more thing about the e-book conversion process
    - 2/19.
        - > Unlike our initial expectations, the "e-book creation work" was not a monotonous task, but rather more like programming.
    - He writes.
    - I thought of it as a type of task that doesn't use much of the brain's thinking power and works in an unobtrusive manner.
    - I also thought that if I knew how to do it, I could outsource it.
    - In reality, it wasn't.
- 2/4 exactly what we are considering.
    - > I have finished translating the first two chapters of the book, and my plan is to convert the book into an e-book and measure the time required, but I feel that the process of "translation," which has become a repetitive and routine task, and the task of "e-book conversion," for which it is unclear what to do, should be mixed together (what?).
    - > I'm thinking that tomorrow I'll have a meeting or an experiment to do at night that will cut into my time, so I'll try digitizing in my spare time, but I'm not sure if I can do a task with an unclear "to do" in my spare time.
    - > →
    - > I've been thinking about it.
    - > Now, translations are logged on a "daily basis" and worked on a pomodoro basis.
    - > How about performing typesetting work in a fraction of the time?
    - > Lumps of time are allocated for translation, and the body of work is done in small chunks of time.
    - > Typing for a break from writing.
    - > We don't want to have translation and typesetting competing for resources and losing motivation over "which should we do?
    - > Basically, if there's time for one pomodoro, we'll move forward on the translation side.
- Currently, there is a situation where translation and typesetting are competing for resources, and people are losing motivation to do either.
- The reason for this was that the typesetting work was not "something that could be performed in a small amount of time.

- typesetting
    - matters for consideration
        - Now, given a list of page title list, there is a program that retrieves it via Scrapbox's API, combines it in Markdown format and outputs
            - I saw the results of that output.
            - Wouldn't it be better to have blank lines before and after the heading?
            - Why don't you change the number of sharps in the heading by looking at a number like "1.2.3.4" in the heading? Now I have to manually fix it.
                - But there are columns and stuff.
                    - Then it would be good if the "list of page titles" was indented.
        - Working with links to images is tedious.
            - This time, I had some images locally that I used for the book, so I figured I'd use those.
            - But in the process of translating one chapter, I had to add quite a few images.
            - And in the future, we'll translate the Japanese in the images, too.
            - Added automatic local download of links to Gyazo on Scrapbox
            - It would be useful if image tags were automatically output accordingly.
        - The bold output is buggy and seems to be a link.
            - We need to figure out what caused this.
        - I have an entire chapter in one file, but the Typola preview is buggy and I can't see the part I want.
            - Too big? Do you want to split it up?
            - Wouldn't it be better to have one page of Scrapbox output to one file?
                - Is that too small?
                - It's a pain to convert the title to a valid string as a file name.
        - Scrapbox -> Markdown and as a separate phase, we need to run a script that licks the links and generates a cross-linked page


translation work
- I had left a tab open or something for a long time, but I restarted and closed it.
- If the procedures and preparations are clearly defined, next time you can say, "Let's just prepare for now.
- Where is it being translated now? (I forgot)
- Open [/intellitech-en-private](https://scrapbox.io/intellitech-en-private) (en-pr) where the Japanese manuscript is located.
- Put the translation in [/intellitech-en](https://scrapbox.io/intellitech-en) (en) and open it
    - You can see at a glance how far you've translated by sorting by update time.

- open (e.g. business, etc.)
        - [[Improvement for English version (chapters 2 and 3)]]
    - [/intellitech-en-private](https://scrapbox.io/intellitech-en-private)
    - [Grammery](https://app.grammarly.com/ddocs/431265635)
    - [Google Translate English-Japanese](https://translate.google.co.jp/?hl=ja),
    - [Japanese/English](https://translate.google.co.jp/?hl=ja#view=home&op=translate&sl=en&tl=ja),
    - [/intellitech-en](https://scrapbox.io/intellitech-en)
    - [Eijiro](https://www.alc.co.jp/),
    - [OALD](https://www.oxfordlearnersdictionaries.com/)
    - [https://ejje.weblio.jp/](https://ejje.weblio.jp/)
    - [progress sheet](https://docs.google.com/spreadsheets/d/1escWYnowRf9ieorGEETZNimRsTzbmDS7QU64kF3Kaxs/edit#gid=0)
- Paste sentences that have not yet been translated from en-pr to Grammery, hide assistant.
- Read from the top and see if there are any English sentences that are difficult for you, a non-native English speaker, to understand.
- If you find a sentence that is difficult to understand OR grammatically incorrect
    - Option 1: Correct the original text
        - Write here: [Improvement for English version (~1 chapter)
    - Option 2: Correct the English text
        - Re-explain the Japanese content in English
        - Grammery's grammar check takes place in real time, which is convenient
- When the translation is done, paste it into en and clear Grammery.

I'm a little more motivated now that I've given it some thought.
- The scheduled end date has to be delayed, and without motivation, it will only be delayed further.
- I am not motivated because I feel that setting a goal to do a task that is scheduled to be completed by the end of April according to the current estimate by the end of March is unrealistically unfeasible. If this is the case, the goal should be changed.
        - [[Setting unattainable goals discourages motivation.]]
- I looked at the estimated date and time of the end of Chapter 4, and at the current pace, the translation is scheduled to end on March 12.
- At this pace, the interim goal is to finish the translation by March 12 and digitize it in the remaining days.

- I just noticed that Eijiro and OALD offer better service by registering as a member, etc.

- Need to remember to bring sun visor and muffled headphones.

- Number of translated pages reaches 100

- As for the issue of inefficiency if you're not sure whether to translate or create an e-book version.
    - Basically translate when there is internet
    - When I don't have internet (on the train to work), I make e-book versions.
- I thought it would be good to
- We are still in the phase of creating support tools through trial and error rather than concentrating on the work.

---
This page is auto-translated from [/nishio/pIntEn 翻訳やる気喪失](https://scrapbox.io/nishio/pIntEn 翻訳やる気喪失) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
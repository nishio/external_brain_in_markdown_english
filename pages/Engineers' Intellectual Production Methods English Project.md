---
title: "Engineers' Intellectual Production Methods English Project"
---

- Project to translate [[The Intellectual Production of Engineers]] into English
- Translation Complete
    - [[Engineer's way of creating knowledge]]
    - (Completed = wording in the illustration and grammar checks yet to be done)

[[pIntEn History]]
    - [[pIntEn Translation completed up to chapter 6]]
    - [[pIntEn Translation completed up to chapter 7]]

2022-02-09
Translation finished, so I split the page.

next action
- Make it readable in Scrapbox Reader
    - If you can read or not, you can still read.
    - Fix the domain so that incoming links are not wasted.
        - And if you don't do that quickly, you can't Tweet.
    - Create a Table of Contents
        - On Scrapbox, maybe?
    - Add a link to the next content.
        - On Scrapbox?
        - Or on Reader?
            - I want there to be a "previous page" link at the beginning of the content.
            - Bread crumbs would be nice.
            - But I'm not sure I want to do this in Scrapbox.
- Chapters 6 and 7 reflect [Corrected differences for the 4th printing
    - Multiply chapters 6 and 7 with a grammar check in Grammery
- Typesetting of chapters 6 and 7
    - It's not that important, but I'm inclined to DONE and be done with it.
    - This process also has the advantage of mechanical checks for broken links, etc.
- I have a few manuscripts I'd like to add.
    - The publisher refuses to include changes that would change the page count.
    - I'll add that to the English version on my own.
    - Write a story about Scrapbox, Keichobot and Kozaneba
- Toward a better network structure on Scrapbox
    - This is of interest, but the definition of complete is unclear

I'll talk to Keichobot tomorrow.

2022-02-10
    - [[Next Action for the Engineer's Intellectual Productivity English Translation Project should be decided.]]
    - [[It would be good if Scrapbox could decide which is the priority among creating a table of contents, reflecting the 4th edition and typesetting.]]
- next action
    - Create a table of contents for Scrapbox
    - However, instead of making it manually, fork from the ePub generation script to make it mechanically possible to generate it.

Q: Where is the script?
- It was in the Chatbot Experimental Repository.
    - How about that arrangement, took me a while to find it.
    - He's written about it in the past.
    - > get_scrapbox/scb2leanpub.py is a subtle name [src [https://scrapbox.io/nishio/pIntEn_5%E7%AB%A0%E3%81%BE%E3%81%A7%E3%83%AA%E3%83%AA%E3%83%BC%E](https://scrapbox.io/nishio/pIntEn_5%E7%AB%A0%E3%81%BE%E3%81%A7%E3%83%AA%E3%83%AA%E3%83%BC%E) 3%82%B9#61e94945aff09e000079f581]
    - It's because the chatbot is diverting code to read Scrapbox.

> If pages are added: print_sorted_titles()
- Hmmm, this is a code that takes the 1000 most recent updates in the project and arranges the titles in dictionary order.
- When the translation was done in a separate project, every page was basically eligible for book inclusion.
    - Only some of them are ignored in the IGNORE LIST.
- I don't know what to do with the large amount of other stuff I've merged into this project...
    - Keyword descriptions and other pages are problematic.
    - Well, okay? (Is it okay?)
    - Either way, there should be a new keyword connected by merging into this project, and we can hit the API to get the content and record it if it has an en icon.

> Finalize Domain
    - [[Custom Domains with Vercel]]
- [[mem.nhiro.org]]
- Easily done.

Having nishio in the URL is redundant.
- Other projects should not be subject to static hosting, and
- what to do about it
- English without language specific information? No conversion without language specific information?
- Machine translation has not yet been implemented to a level where it can be put into operation.
- It's funny how ja is untranslated when the original is written in English.

Automatic navigation to previous and next content, done.
- ![image](https://gyazo.com/f6a88243660738b8950fdc810118d429/thumb/1000)

In the meantime, we've got the URL finalized, so we'll tweet this out and let Google crawlers pick it up.
[https://mem.nhiro.org/Engineer's_way_of_creating_knowledge](https://mem.nhiro.org/Engineer's_way_of_creating_knowledge)

2022-02-13
    - [[NEXT Engineer's Intellectual Production Techniques]] I made it.
    - At the time of writing, I used to write paper stickies on my commute to work, but I no longer commute in the new Corona, and there's no advantage to using paper stickies now that I'm making Kozaneba and such.
    - I thought the equivalent of a paper sticky note on my commute was writing on Scrapbox on my phone while walking around.
    - Explicit need for a place to store unstructured fragments of output in random order without scattering them
    - I think it would be ideal to be able to put this directly into Kozaneba.
        - Instead of writing out a lot and then importing it into Kozaneba, once you've written it out, you can organize it on Kozaneba and use it as a stimulus to come up with more ideas.
            - This may not be the case, the stickies that came out earlier are already structured, and if you look at them and create a structure, you may end up reproducing [[Existing Structure]]!
                    - [[Early verbalized language is merely a reproduction of existing structures.]]
            - availability bias
        - Now is not the right time to use it from a phone, no way around it.
    - I started adding numbers to the [[Intellectual Production of Engineers All Levels Table of Contents]] because it was inconvenient not to have them.
    - There should be a unique number for the column.
    - [[Experience is multi-schematic, diary is temporal scheme]]
    - This page will continue to be glossed over in the temporal schema.

The table of contents of the Japanese version is numbered in the same way as the English version.
- In the process of creating the English translation on Scrapbox, I thought, "Let's assign unique numbers to the headings. The reason:.
    - It's hard to reference by page number when it's in digital form instead of a paper book.
    - Headings are natural to use as titles, but there are headings that appear multiple times, such as "Summary
- This was so useful that we did the same for the table of contents of this Japanese version
    - When there is a mention on Scrapbox, it will be a blue link
    - We have decided to put the added articles not included in the book version in the table of contents as additional content.

1.3.3.2
Read the source code
Reading documents that are not one-dimensional

When I'm done making the table of contents, I'll add links to the places you mention in the page designations on this Scrapbox.

3.1
A story about how the development of VR has made it easier to create mind palaces.
Mind Palace of this book on Micra

4.1.1.4
Talk about one-dimensionality, I'm writing about it here.

4.3.1.3
photo-reading
I didn't follow the procedure, but it's defensive.
I'd like to put the defending and breaking in there somewhere.

Did I mention [[First, measurement]] in 4.3.2.1 or somewhere else?

[[(6.3.1) Minimum Viable Product]]
>  If you don't know who your customers are, you don't know what quality is 209
>  What should be verified depends on the objective 210
It's listed in the table of contents in Japanese, but not in English.

[[(7.2.1) Exploring strategies to find targets you want to learn]]
> (7.2.1.1) Widen search area
This is also not in English.

Now that we have a table of contents, we'll change this mention on Scrapbox to one that uses this number.
Notes of interest in the process
    - [[The Phantom Chapter of the Engineer's Intellectual Production Technique]]
    - [[Creating a common language for the framework]]
        - [[The Intellectual Production of Engineers]] focused on the intellectual production of a single individual.
    - When thinking about multi-person organizations, [[framework]] has the effect of creating [lingua franca
    - Form with added benefits
    - [[Intellectual production techniques for teams]]
    - [[Multiple people think]]
    - [[(4.3.2.1) Measure and control speed]]
        - [[First, measurement]]
    - [[Intellectual Production Techniques of Engineers_Additions]]
- `Where to put the proposed additions?

2022-02-14
Next Action List
- ✅ Make it readable in Scrapbox Reader
    - Bread crumbs would be nice.
- Chapters 6 and 7 reflect [Corrected differences for the 4th printing
    - Multiply chapters 6 and 7 with a grammar check in Grammery
- Typesetting of chapters 6 and 7
    - It's not that important, but I'm inclined to DONE and be done with it.
- I have a few manuscripts I'd like to add.
    - Write a story about Scrapbox, Keichobot and Kozaneba
        - [[NEXT Engineer's Intellectual Production Techniques]].
- Toward a better network structure on Scrapbox
    - This is of interest, but the definition of complete is unclear
(PS: I felt it was strange to write "Next Action" when there are several, so I rewrote it as "Next Action List", but I thought it was an "Action List" to begin with.

2022-02-14
`Where to put the proposed additions?
- [[Intellectual Production Techniques of Engineers_Additions]]
- [[Proposed additions to p. 150 - p. 168, Intellectual Production of Engineers]]
These are scattered about with no clear idea of where to put them.
This could also be a link using a numbered table of contents.

2022-02-15
Keichobot, [[ELIZA]],  [[client-centered therapy]] ,  [[Experiential Processes and the Creation of Meaning]]

The Scrapbox article is in [[(5.4.3-2) Scrapbox]] and is fairly simple

Wouldn't it be nice to have a Kozaneba on "The Intellectual Production of Engineers" by the author himself?
Both to keep my mind clear and as a demonstration of Kozaneba for our readers.

liquidation
- `Where to put the proposed additions?
    - Place the fragment in the proper position and this page disappears.
    - [[Proposed additions to p. 150 - p. 168, Intellectual Production of Engineers]]
    - The fragments were distributed and what was put out in the table of contents.
    - I left this page as a hub.
    - [[Intellectual Production Techniques of Engineers_Additions]]

2022-02-24
- Tasks
    - Log of sentences rewritten during the process of English translation and make a list of corrections for the fifth edition.
    - Syntax check with Grammery after chapter 5
    - Bread crumb on mem.
    - Add an advertising section to mem.
    - Resumed machine translation project that was "suspended to give priority to English translations".

- Bread crumb on ✅mem.
    - ![image](https://gyazo.com/22f62c0c101b0541279a50b90d51ce1b/thumb/1000)
- Add a publicity section to ✅mem.
    - ![image](https://gyazo.com/40d0656664a2d4304256388f96b2043f/thumb/1000)
- ✅2Do not show headings when there are no hop links
- ✅Allowed users to specify pages not to display related pages.
- Columns do not currently participate in the back and forth or hierarchical structure.

> Resumption of Machine Translation Project "Suspended to Prioritize English Translation
    - [[ScrapboxAutoTrans Development Diary 2022-01-20]]
- Anything with an English flag is not translated.
- For non-flagged items
    - Translate all?
    - Excluding code regions, etc.?
    - Retranslate the whole thing upon change?
    - Want to specify the translation of a link?

- Translation is required in advance because the title and links have to be determined.
- When a page is displayed, it must link to a translated page and a page originally in English.

2022-02-25
- [[It would be good to have a policy on how to proceed with the ScrapboxAutoTrans project going forward.]]
- What they value is "connection.
    - There are two kinds.
        - Connections that help me think
        - Connections that help readers read and understand
    - The former "connection for me" is the more valuable "connection"
        - The latter "connection for the reader's understanding" cannot achieve its purpose if it is machine-generated in large quantities.
            - It should be a small number of useful links that have gone through a selection process by the author.
        - The former connection for me is beneficial in making sure I don't overlook the latter connection option
    - With that in mind, it is better to merge the Scrapbox project in terms of providing a connection for authors
In light of this previous discussion.
- Machine translation results should go into Scrapbox instead of caching machine translation results in Firebase and mem displaying link joins

[/villagepump/2022/02/25](https://scrapbox.io/villagepump/2022/02/25)
- Scrapbox translation project, after reviewing and thinking about my conversation with Keichobot, I came to the conclusion that "machine translated material should be put in the same project in Scrapbox," and I said, "Really, that's true?" and I'm holding off.
    - Maybe you could make a separate one with everything thrown into the same project and try it out.<img src='https://scrapbox.io/api/pages/nishio-en/takker/icon' alt='takker.icon' height="19.5"/>
    - certainly<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
        - I exported everything and estimated that it would cost [[60,000 yen to translate everything...]] since it has 24M characters.
        - Maybe one hop from the most recently updated page or something...
        - All I'm talking about is Dominion.
        - My wife said, "Sixty thousand yen? That's cheap."
        - Well, I want to start small because it's hard when you try and "fail".
- When I translated article X
    - Different Titles Y
        - When you query X for a translation, you must know that it has already been translated and that it is Y
            - If the last update time of X is before the translation time of Y, there is no need to re-translate
    - Same title
        - Scrapbox cannot have multiple pages with the same title, so they need to be merged pages
        - You have to know how much is machine translation and how much is Japanese.
- In the meantime, let's put it in DeepL by hand and make some samples.
    - [https://twitter.com/nishio/status/1497221200795549696](https://twitter.com/nishio/status/1497221200795549696)
    - The way this link is displayed, I'm not sure I'd be inclined to click on it.
    - Twitter Card implementation should be a priority.
- I'm done for the day as I'm no longer getting responses from DeepL

reference
- [https://xkcd.com/](https://xkcd.com/)
- [https://wiki.c2.com/?ThreadMode](https://wiki.c2.com/?ThreadMode)


[[Twitter Card]] now displayed.
The related pages are now on the right.
- I did that with this project as well.
- It's not a card UI.

It is a metaphor for vegetative growth that these tasks take precedence over work to improve translated content
- A small but growing search inflow is starting to occur.
- It's no use keeping an eye on it, so I leave it in a state where it can grow on its own.

I looked at the most viewed and made a list, removing those that were unique to Japan or were temporary buzz.
- [[Translation Candidates]]
- Surprisingly long ones.

I was thinking of translating a series of blind spot cards or pictures of two people saying different things...
- Well, do both and observe the actual amount of access.

The problem is when you see a translation and want to fix it a little.
- I don't feel comfortable enough to change it to en if I don't rework the whole thing, but if I leave it as jaen, it will be overwritten if I update the ja side.
    - Maybe we shouldn't be thinking about this in the abstract, we should be observing concrete problems as they arise.
- Cases where the title is originally in English and the translation results in the same title
    - I decided to list them side by side [[Memex]].
    - It's hard to say whether machine translation is better or Japanese.
        - The correct answer depends on the attributes of the reader.
        - Ideally, it would be better to identify whether the reader is an English or Japanese speaker, but Scrapbox does not have such a function.

I tweeted back now that I can get the image out.
- [https://twitter.com/nishio_en/status/1497864554378043393?s=20&t=E0xGY6-kY75_RMvsEPLUKQ](https://twitter.com/nishio_en/status/1497864554378043393?s=20&t=E0xGY6-kY75_RMvsEPLUKQ)
Cache clear
- [https://cards-dev.twitter.com/validator](https://cards-dev.twitter.com/validator)
[[pIntEn]]

---
This page is auto-translated from [/nishio/エンジニアの知的生産術英語化プロジェクト](https://scrapbox.io/nishio/エンジニアの知的生産術英語化プロジェクト) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
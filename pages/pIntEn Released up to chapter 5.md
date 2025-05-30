---
title: "pIntEn Released up to chapter 5"
---

from  [[Project for English-language intellectual production techniques for engineers (-20190522)]]
pIntEn Released up to chapter 5
2019-03-05
- The `[MOTIVATION](-)` in chapter 0 is misbehaving, causing a mysterious phenomenon in the PDF version where all subsequent links become footnotes.
    - It is better to modify and reconvert on Scrapbox, but chapter 0 needs careful work since some manual modifications were made.
    - For now, fix on Scrapbox and manually fix the file at hand.
- 1.1 figure caption is wrong in epub
    - This is because the internal links to the rows have changed to highlighting because there are no other common links, and only the RL-like parts of them are links
    - The line link is not a good idea to begin with, but what can we do?
    - I put it on another page.
        - [/intellitech-en/learning cycle](https://scrapbox.io/intellitech-en/learning cycle)

- Figure caption in 1.1.1 is connected to the bullet in the next line
    - The preview on Typola shows line breaks, but they are not interspersed with blank lines, so they are merged when converted to epub.
- The code in chapter 1 is broken.
    - The code only appears in a few places, so it's easier to fix it manually.
    - Need a mechanism to manually modify the current converted file and re-apply that modification to the reconverted file.

2019-03-12
Example of diff
:

```
134,135c134,138
< code:Example of a tuple
< - （1,  2,  3）
---
> Example of a tuple
> 
> ```
> (1, 2, 3)
> ```
139c142
< Lists and tuples are very similar. What is different? This question becomes the driving force of learning. The driving force let you query what is different on a [search engine](ref-673f998), rewrite the list in the program to tuples, and vice versa. These activities bring you new knowledge. I describe these activities with creating a new box and put it on two boxes.
---
> Lists and tuples are very similar. What is different? This question becomes the driving force of learning. The driving force let you query what is different on a search engine, rewrite the list in the program to tuples, and vice versa. These activities bring you new knowledge. I describe these activities with creating a new box and put it on two boxes.
```


The top hunk is a modification of the converted file that was edited by hand to make it a code block, the bottom hunk is a modification of the converted file that added the link in Scrapbox, which I would like to see merged 3-way!
→I got it.

-----
Procedure memo
- main()
- merge_all()
- If conflicts are occurring, open the editor and fix them.
- copy_all_merged_file()

point of concern
- Vague fears that I will eventually make a mistake in the procedure and something complicated will happen.
- It is not good to have copy_all_merged_file() and copy_all_file()
    - Since the latter is used in the first step, it is implemented first and has a shorter file name, but this overrides base/X and manuscript/X, so if you use it in the middle by mistake, complications may arise!
    - What can be broken will be broken and we need to do something about it.
        - →Do you want to put it all on Dropbox?
- Crawls the specified file in main(), but does not crawl when a new page is added
    - I have a feeling that this should be automated as well.
    - This step takes about 4 minutes.
    - I wonder if it could be automated, including the creation of previews.
        - There is a creation API [https://leanpub.com/help/api](https://leanpub.com/help/api)

Issues
- Round numbers are not alphabetical, so they will be in Japanese font.
    - Appropriate?
    - If the English font also has round numbers, add round numbers to the English letters.
    - If the English font seems to be garbled with rounded characters, replace it.
    - →In the first place, the Japanese language is somehow corrupted.
- I can't follow the link.
    - Duplicate IDs in cross-links.
    - I tried to assign the same ID to those that are lower case and identical, but the case is not consistent when putting them in the set.
    - However, we can't lowercase it to put it in SET.
        - A matter of appearance as it is a string that appears in the index
    - Name -> ID is easily computed, so name is put in the list, but we should create a function ID -> name and put ID in the list

The time to create the preview should be measured.

Downloading images, it is better to run them together at crawl time since the system is designed to download only those that do not exist.
Easily forgotten.

13:40 Download images and command regeneration of previews.
Find out when you will receive email notifications later.

An email notification was received at 13:51. All the errors about missing images were gone.

Duplicate ID bug fixed.
- 18:49 Preview generation starts
- →19:02 Duplicate ID bug fixed.
- At any rate, since a large number of errors have been resolved, it's nothing to hide, so let's release it!
- ![image](https://gyazo.com/707b96433676da1c86c49b07426790f1/thumb/1000)
- Increased from 210 to 423 pages.
    - Is it significant that you added pages that are not in the chapters?

Issues
- All additional pages are in the largest section.
- If there is no blank line at the start of a bullet, all subsequent bullets will be collapsed.
    - It looks like I only need the 0 to 1 part, so I guess I'll have to use a script to deal with it.
- I've solved the duplicate ID problem, but there are links I can't jump.
    - Wasn't it a good idea to add individual pages as pages?
        - I guess I just don't get the error message about duplicate IDs when it's obvious they're duplicates...
        - It seems that for some reason the chapter titles are also included in the index, and the IDs are duplicated there.

impressions
- Scrapbox is easy to connect links and easy to look up to connect them, so there is a phenomenon that the English version is richer in links than the original book. w
    - There are many links in the original book, but there are three means of linking to that information: "page 123," "explained in chapter 1," and "compared to the Whone Mind System. "The first one is a direct jump, but the other two implicitly assume that the reader's brain is still linked to that information.
    - By writing in a Scrapbox-like manner, the assumption that "the link must be left in the brain" is eliminated by the thought that "someone may come in through search" and the power to make it explicit is applied.

What is the original title of Schopenhauer's "On Reading"?
- ÜBER LESEN UND BÜCHER.

It would be interesting to add a picture to a page without a picture.

2019-03-20
- Finished translating 4 chapters yesterday and will start checking them for digitization.
- Fixed a bug where cross-linking was not working properly
- Tofu Japanese during cross-linking

The cycle of fix, build, wait (more fixes during this time), see the results, and so on goes around, but at this time, there seems to be some confusion about what to fix and what to check.

- 1
    - I forgot to add an additional page.
        - Result:.
            - ![image](https://gyazo.com/ace7397db82d2c2721ed5d0656885ea4/thumb/1000)
            - I don't like the way this outline is done.
            - You can either make a big bundle and put them in it.
            - In the first place, isn't the size of the heading now determined by the number of numbers (X.X.X)?
    - You forgot to add a column.
    - The keyword page was not updated, just the past was used as is.

- 2
    - Sometimes `Japanese` is tofu.
        - Should I make it a link, 0.2.1 and 0.3 I changed it to try it out, need confirmation.

sort order
- I would like to add a colon like `2: `, but since a colon comes after a number in ASCII code, this would cause 2 to come after 2.1.
    - However, this order is not a big problem since it is only specified once manually in titles.txt.
    - There are other places where the sort order must be mechanically tweaked. Upper and lower case letters are in different positions in the index.

-----
I changed the sort order of the keyword page on the train on the way home.
18:38 Preview creation started
18:46 Completed
ID not found for column.

19:21 → x
- The column has been incorporated, but it's in the table of contents at the top level.
    - →Modified the conversion script to make the second step
19:52
- The column is now in the second column, and it's now in chapter 4.
    - →Add a new section at the beginning of columns.md
        - In addition, I made the same modification to keywords.md.
20:09
On the way home, it occurred to me [[Multilingual development based on machine-friendly English]].

----
I felt confused about parallel tasks, so I talked to my wife: [[how to turn around improvements that do not see immediate results]].

2019-03-22
- I did this morning what I wrote out Wednesday night.
- Inconvenient to specify location by PDF page number
    - The actual work to be done requires opening the appropriate page in Scrapbox

Due to problems with round numbers and different fonts for body text and chapter headings by default.
If the font is not Japanese, it will not be corrupted in the body text, but it will be corrupted in chapter headings.

The depth of headings in the TOC can also be adjusted.
- If I put it all out there, I'd have to narrow it down a bit because it's all overkill, even the cross-linking.


2019-03-26
- If you are viewing a PDF in Preview on a Mac Back is `Cmd+[`

---
2019-03-27
I just finished looking through the entire PDF.
- Change the representation of chapters [[Representation of chapters on Scrapbox]].
- No special treatment of external links, but they are displayed as they are, as a title/URL pair, so no real harm is done.
    - The URL will appear, but if it is written in the book PDF, it is better to have the URL so that it is clear that it is a link outside of the PDF.
    - However, it is not nice to be included in the index, so only remove indexes that contain http
- Problem with some images not displaying
    - Caused by the fact that some of the files downloaded from Gyazo are PNGs
    - How to Resolve
        - Align the file at hand to JPEG
            - Every time I download a new file from Gyazo, I need to convert it and ensure it is a JPEG
                - This can be automated.
        - Change the extension only for PNG files and change the link from Markdown
            - Cannot determine if it is a PNG or JPEG from the Gyazo URL alone
                - I need to look at the response or look at a local file.
                - Why not just look at the local files?
                    - You can also notice problems such as missing files
                - When downloading a file, determine its type and add the appropriate file extension, and when outputting Markdown, look at the local file and change the output based on which extension is present.
    - →The following is a policy to identify the type of image at the time of downloading and add an appropriate file extension, and to change the output depending on which file is present at the time of Markdown output.

2019-03-29
Now, the links are actually represented in the form of electronic links, in case you're reading it electronically (since it's LeanPub), but as a result, what's 140 pages in a paper book is 400 pages in an A4 PDF, so I think it's a quandary to have this printed on-demand in KDP.

Well, but we'll have to wait until the electronic version is completed to figure out what to do with it.

I forgot to mention that I finished checking up to chapter 4 and did a release build.
![image](https://gyazo.com/e3ee85131f91ff48ab1682cdc6a41726/thumb/1000)

2019-04-03
- I've stopped for a while to work on the first half (~4 chapters) of the e-book, but I'll continue to work on the translation of the rest of the book.

2019-04-10
    - [[Draft addition to "Group Formation Requires a Change of Mindset"]]
- Addendum.
- Let's translate this.

2019-04-16
    - [[Work and practice]]
- For me [I want to do something that is cognitively burdensome.
- If I hadn't done it, I wouldn't be familiar with Wittgenstein.

2019-04-30
- Update e-book version as chapter 5 translation is finished.
- The name get_scrapbox/scb2leanpub.py is subtle.
- When I looked at help(), it said to run main(), so I did, but first I had to make the contents of chapter 5 a crawl target.
- There are several "Column:" titles, but "(Column)" is correct.
- Not incorporating Vicki's fix again.

2019-05-01
- Search by "Column:".
    - revision (e.g. of a rule, regulation, etc.)
    - There is one forgotten translation.
- After working on the merge and doing the preview build, I realized I forgot to update the book.txt file.
- rebuild
- No errors.
    - Your word count is 92057 words.
---
This page is auto-translated from [/nishio/pIntEn 5章までリリース](https://scrapbox.io/nishio/pIntEn 5章までリリース) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
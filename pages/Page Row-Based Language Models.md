---
title: "Page Row-Based Language Models"
---

When I gorged myself on the rule base as a preliminary step to learning, it was surprisingly easy to take out just the headline and the body of the text.
As an unanticipated but pleasant side effect, the back matter, table of contents, and index were also deemed "not headings or text".
→ Then go to [[Extracting text from book PDFs using machine learning]] to make it work for another book.

2018-09-30
- [[line continuation model]] [[line continuation judgment]] wrong in thinking
Here's what the actual data looks like
:

```
^L Purpose of this book

iii

Purpose of this book

　I would like a good reference book on intellectual production techniques. I teach intellectual production techniques to others.
Sometimes I would like to have a book to recommend.
　I have been engaged in intellectual productivity research at Cybozu for 10 yearsNote 1.
As part of my duties, I organize my thoughts and ideas at the Kyoto University Summer Design School.
```

The difference is whether it can be incorporated into a "sentence" before the lines are connected or not.
The only way to determine whether lines are connected or not is to "connect them directly or connect them with spaces", so if you create a language model after morphological analysis of the connected items into a word sequence, the model will fray from there.


-----
- Character-based, word-based
- Understanding Books
- A line beginning with "Note" at the end of a page is a footnote
- column (e.g. in newspaper)
    - Footnotes occur in the middle of the page

LSTM Output
- > I prefer to do 50mm x 38mm fusen Chapter 1: The driving force that turns the cycle to learn new things:Motivation 8 Chapter 1: The three ways of information gathering to learn new things, how to allocate the three ways of information gathering, as you want to continue where you turn the conversation, you may learn the 1964. This is the birth of the phrase "30 seconds per book", which means 30 seconds for just one page, and the two hours will be over.

Part of original data
> ... But it is not. First of all, the top priority is excellence, and that Chapter 7: Deciding What to Learn Yourself Management Strategies 234.
> Chapter 7: Deciding What to Learn is a Self-Management Strategy 235 and thus an opportunity for growthNote 15....
Ah, I see. So that's how it is.
Chapter titles and other page numbers at the end of even-numbered pages and at the beginning of odd-numbered pages

- [[page model]]   [[line model]]   [[line-based language model]]

---
This page is auto-translated from [/nishio/ページの行ベース言語モデル](https://scrapbox.io/nishio/ページの行ベース言語モデル) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
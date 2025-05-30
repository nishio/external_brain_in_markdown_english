---
title: "howm's come-from link"
---

In [[howm]], the notation ">>> aaa" is a link to aaa.
- This link is goto link
    - The link is realized by "search and list by that keyword" as an implementation.

If you write "<<<< aaa", all occurrences of the keyword in all sentences will be links to it.
- This is the come-from link
- How to declare, "If a link for this keyword is pressed on another page, it will come here."
        - [[Calling together links]]
    - Opposite to "goto" which is "go where you are going".
- This is useful for use cases like definitions in mathematics, where you want to be able to "easily navigate from where this concept is mentioned elsewhere to here": [[come-from links and mathematics]].
- A case study that I knew we needed a come-from link.
    - At the end of the page, I wrote "[[Expansion of pertinent judgment]]", it would be nice if it was a link to the explanation page [so that first-time readers know what this means
    - However, if we make each of these links that appear on various pages, the current Scrapbox specification will cause a [[2-hop link]] between those pages.
        - If you want to avoid that with the current spec, you need the bad know-how of using icon notation and external links.

[http://www.bookshelf.jp/texi/howm-tutorial-html/howm-tutorial.howm.b.html](http://www.bookshelf.jp/texi/howm-tutorial-html/howm-tutorial.howm.b.html)
- Gone. see [WebArchive [https://web.archive.org/web/20111111063142/http://www.bookshelf.jp/texi/howm-tutorial-html/howm-tutorial.howm.b.](https://web.archive.org/web/20111111063142/http://www.bookshelf.jp/texi/howm-tutorial-html/howm-tutorial.howm.b.) html]

:

```
= <<< goto link

In howm, you can use the "howm" function to show the relationship between memos, files, etc., and to move them around.
Two types of links are used for First, the most basic goto link
This section describes the following

A goto link, for a simple example, is an html <a href="..." ><a href="..." ></a>
The goto link is used as follows

> 
>>> Testing
> 

The goto link is actually implemented using the search mode. For example, the above
Press `RET' on the link,

    M-x howm-list-grep
    Search all (grep): test

the same thing happens as if you had used howm's search mode.


Also,

> 
> >>> /etc/services
> 

If you specify a file that actually exists as a goto link, such as
Press `RET' to search, and `RET' again to open the file.
The link can be created in the same way as a link to a website.

Apart from this, URLs beginning with file:// or http:// are also treated as links.
If you press `RET' on a link, the file scheme will be defined in Emacs itself, using the http ski
The browse-url-browser-function can be used to directly open the browse-url-browser.

In the file scheme, `C-u RET' will split the window and open it.


= <<< come-from link

Next, let's look at a slightly different kind of come-from link: come-from
Links automatically link to all words in other memos. For example

> 
> <<< apple
> A delicious red fruit. In Japan, Aomori is famous for its production.
> 

and write it in other notes.

> 
> I love apples.
> 

the "apple" part will be underlined, whereupon you press `RET'.
The system will automatically jump to a memo with a description of the apples.

It is a little quirky to use compared to goto links, but it is very useful, so learn to use it!
Let's leave it at that.
```


---
This page is auto-translated from [/nishio/howmのcome-fromリンク](https://scrapbox.io/nishio/howmのcome-fromリンク) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
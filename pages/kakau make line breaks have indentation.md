---
title: "kakau make line breaks have indentation"
---

> [nobkz](https://twitter.com/nobkz/status/1433682212466016256): I've been wondering about this for a while, so I'll try to use it. kakau.app First, I'll try using it without reading the introductory article, etc. twitter.com/pokarim/status...

> [nobkz](https://twitter.com/nobkz/status/1433683709572517888): I successfully logged in from the login page, it's an alpha version so it's normal that the first page lacks information. I would not have put a link to a blog, etc. on the first page, but you are very kind. I'm looking forward to seeing what you do with this first page.

> [nobkz](https://twitter.com/nobkz/status/1433687822980960257): I see, that's interesting.
> There are four rows of frames, and the left two rows are for content navigation, guides, and so on. And the right two columns are content. pic.twitter.com/Mcb55rw3vv

> [nobkz](https://twitter.com/nobkz/status/1433688422082756611): I found the interactions interesting, roughly the two left column frames, but from left to right, I was hoping there would be an input/output relationship, but the cursors are left to right, both I was expecting that there would be a left to right input/output relationship, but the cursor was on both the left and right, and both were editable. I think this is probably a characteristic of Reactive, but I also think it is like Direct Manipulation for me.

> [nobkz](https://twitter.com/nobkz/status/1433688911616696325): because "you can play with the output as it is, and that is reflected in the input" is exactly what Direct Manipulation is.

> [nobkz](https://twitter.com/nobkz/status/1433689730445549569): However, some of the details are a bit confusing. I had some difficulty anticipating line breaks and indentation. (Of course, I'm sure you can get used to it).

> [nobkz](https://twitter.com/nobkz/status/1433690161917825031): if you are someone who is used to tab and shift+tab in markdown and other tools, it sounds fine.

> [nobkz](https://twitter.com/nobkz/status/1433691270463967234): i see! pic.twitter.com/2mFz15mgjp

> [nobkz](https://twitter.com/nobkz/status/1433691507945467910): I'm starting to think we could do something similar with VSCode extensions.

> [nobkz](https://twitter.com/nobkz/status/1433692942246371328): Is this a product in the pattern of asking people to think of their own usage scenarios?

> [nobkz](https://twitter.com/nobkz/status/1433695078837485583): In my opinion, it looks kind of good for thought description of tree-structured patterns. However, I'm a bit concerned that I don't see any links, etc. between documents. Is there?

> [nobkz](https://twitter.com/nobkz/status/1433695704183029765): I'll read your blog later. I've figured out the functionality, so I guess I'll be using it for a while.

> [nobkz](https://twitter.com/nobkz/status/1433738462155325445): I have a feeling that there is a clear best use case for this, but I can't seem to grasp it. I'm not sure if I'm getting it right, or if I'm just not getting it.

> [nobkz](https://twitter.com/nobkz/status/1433740682041061380): I can see the topological equality of information by having left and right editors. It's like the topological tree structure contributes to editing and readability by changing the way it looks, while maintaining the structural equality of the topological tree structure. But I feel that there is a clear and concrete scene where the value of proper handling of such information structures is easily understood.

> [pokarim](https://twitter.com/pokarim/status/1433775587223502861): I'm going to talk about elemental technology or data format. Mainly for Nobukazu-san.

> [pokarim](https://twitter.com/pokarim/status/1433776487543435264): The data structure in the kakau specification is in the form of plain text with extended control characters. By having the indentation depth as an integer in the newline character, it is possible to create a tree structure like an outliner without using spaces or tabs, but only with newlines.

> [pokarim](https://twitter.com/pokarim/status/1433776936262660100): At this point, the feel is somewhere between plain text and an outliner.
> That allows control character expansion to add other attributes, not just indentation depth.

> [pokarim](https://twitter.com/pokarim/status/1433777254060879877): Think of these attributes as the equivalent of HTML attributes and tag names. In other words, since a tree structure can be created using only control characters such as line feeds and attributes, the expressive power of the data structure is similar to HTML and XML.

> [pokarim](https://twitter.com/pokarim/status/1433777663454289921): The main difference with HTML is that unlike HTML, which is based on plain text and marked up with tags, the tree structure is represented by control characters (mainly line breaks) and their (conceptual) indentation) to represent a tree structure.

> [pokarim](https://twitter.com/pokarim/status/1433778185544503303): The major difference from HTML tagging in terms of feel is that there is no correspondence between start and end tags. Therefore, even if you delete an arbitrary character, it will not be broken. The tree structure can be manipulated with an indent-like feel, and since it is directly connected to the data structure, it is a direct manipulation operation.

> [pokarim](https://twitter.com/pokarim/status/1433778931966955523): if we consider HTML, or mainly XML, XML does not have a specific use. it can be XHTML or MathML. kakau's The underlying data structures have basically the same properties. So the sense that the optimal usage scenario is elusive may come from that.

> [pokarim](https://twitter.com/pokarim/status/1433779796106887169): kakau already has curly brackets and tables, which correspond to MathML in XML or to each vocabulary in MathML. MathML in XML or each vocabulary in MathML. If you see a use that could be well supported, you can add vocabulary for it.

> [pokarim](https://twitter.com/pokarim/status/1433780044069965827): There is another point where the ideology differs from HTML, and that is that we dare not aim to separate the document structure from its appearance. I think you will find that the data structure XML itself is not tightly coupled with that philosophy.

> [pokarim](https://twitter.com/pokarim/status/1433780568378916868): In kakau, the goal is not to describe the meaning or document structure and then adjust the appearance later. We are aiming for something that corresponds to the meaning exactly as it is written, rather than writing the meaning or document structure and then adjusting the appearance. This may be a kind of WYSIWYG, but in a more primitive or different way from what is often called WYSIWYG.

> [pokarim](https://twitter.com/pokarim/status/1433781284250087426): Because of these characteristics, kakau may seem somewhat elusive to Nobukazu, who has a deep technical understanding of HTML, plain text, and other editors. who has a deep technical understanding of HTML, plain text, and other editors, may find kakau somewhat elusive. That's all for now.
---
This page is auto-translated from [/nishio/kakauは改行にインデントを持たせる](https://scrapbox.io/nishio/kakauは改行にインデントを持たせる) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
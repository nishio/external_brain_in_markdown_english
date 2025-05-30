---
title: "Negative variability"
---

I heard an introduction to the book "[[Multiparadigm Design]]" and thought it sounded like an interesting concept, so I looked into it.

[Chapter 3 Variability Analysis - Issue #3 - phpmentors-jp/mpdosaka](https://github.com/phpmentors-jp/mpdosaka/issues/3)

[PHP Mentors - Translated Debasish Ghosh's blog post "Domain-driven design: managing variability" [https://phpmentors.jp/post/129261828893/ddd-managing-](https://phpmentors.jp/post/129261828893/ddd-managing-) variability]
- September 18, 2006

[Multi-paradigm design](https://www.ogis-ri.co.jp/otc/hiroba/technical/MPD/)
- August 2000 "Multi-Paradigm Design and Implementation in C++."
    - > In connection with this article, I have received permission to translate the presentation material "Multi-Paradigm Design and Implementation in C++" that the author has used at the Object-Oriented Symposium 2000 (held by the Software Engineering Society of Japan in August 2000). The author has received permission to translate the presentation material "Multi-Paradigm Design and Implementation in C++". This document (written by the author himself, of course) explains the whole picture of multi-paradigm design in a compact manner.
        - Japanese translation of material by author James O. Coplien
        - Domain disappeared as of 2005.
        - [WebArchive](https://web.archive.org/web/20020910055641/http://www.rcnchicago.com/~jcoplien/Nippon/MPD/ThesisIntroduction_jpn.html) and identical to [here](https://sites.google.com/a/gertrudandcope.com/info/Publications/Mpd/ThesisIntroduction-jpn).
            - > The most common abstraction is "hierarchy. This is appropriate when the system is simple enough to be divided into layers or hierarchies. In the object paradigm, there is a tendency to think in this way and to try to build both class hierarchies and implementation hierarchies. However, the complex structures inherent in modern systems are not inherently attributable to hierarchical structures. First, there is the question of scale. A line of code may be on the order of 100, or 1000, or 100 million, or 1 billion, or 10 billion. Such a scale cannot be properly analyzed with a simple hierarchical structure.
        - The linked PDF is password protected.
    - Given the time of year and the author, I'd say this is it [PDF](https://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.84.7630&rep=rep1&type=pdf).
        - It looks like a doctoral dissertation, so it's likely to be written in a more rigorous manner than books for the general public.
        - Book is 1998, this is 2000.
        - > Chapter 2 Commonality Analysis
        - > 3.3 Positive and Negative Variability
        - I do the analysis first to find commonalities and then look at the differences. For example, I think the message has a header and a body. This is commonality.
            - But if you analyze it in detail, you'll say, "The ACK message doesn't have a body!" or something like that.
            - This kind of variability that breaks commonality is negative variability.
            - In this example, we could eliminate the negative variability by saying "ACK has a body of length 0," but that's not a good idea
                - What is the checksum of the ACK?"
                - Having an interface that is not needed increases cognitive load.
                - There can be overhead in time and memory consumption.
            - Small negative variability can be handled by ifdef, but it does not scale, so consider splitting the domain

> > Maybe [[Multiparadigm Design]] negative variability and [[Liskov Replacement Principle]] should be considered as a set. The Liskov Replacement Principle should be broken when negative variability is considered with class inheritance.
> I think the manifestation of negative variability is an opportunity to create a new domain (and more importantly, existence). [https://github.com/phpmentors-jp/mpdosaka/issues/3#issuecomment-84257234](https://github.com/phpmentors-jp/mpdosaka/issues/3#issuecomment-84257234)
[https://twitter.com/iteman/status/1171097073082486785](https://twitter.com/iteman/status/1171097073082486785)
- It says on p. 89.
    - > Positive variability is the preferred mode of design under multi-paradigm design because it most often leads to design support by additional formalisms. For example, one can use the Liskov substitutability principle when applying inheritance to express positive variablity. Multi-paradigm accommodates negative variability as well, often by appealing to existing techniques such as inheritance with cancellation.

> Templates, `#ifdef`, are not inherently object-oriented language elements. However, C++ programmers are, or are expected to be, familiar with them. For example, when should you define a regular class and when should you use a template?

---
This page is auto-translated from [/nishio/負の可変性](https://scrapbox.io/nishio/負の可変性) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
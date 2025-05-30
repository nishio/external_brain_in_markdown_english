---
title: "Politech Enhancement Proposal"
---

In the world of technology, there are mechanisms for refining knowledge, such as RFCs (Request for comments) and PEPs (Python Enhancement Proposals). Can we introduce a similar mechanism in politics?

The purpose of this text is to provide information and seek comments.

- What is RFC?
    - Publication format of technical specifications by IETF (Internet Engineering Task Force)
    - The facilitation of Internet communications required that disinterested, mutually unenforceable parties form a consensus on the details of the technical specifications for communications.
    - RFC stands for "request for comments," a request to publish a technical document and solicit comments on it.

- What is PEP?
    - Public form of technical specifications for the Python programming language
    - Changes in programming language specifications can either benefit or harm existing users, depending on how they use the language. Users with conflicting interests need to bring use case information to each other to help determine new specifications.
    - PEP stands for Python Enhancement Proposal.
    - For more information [PEP 1 -- PEP Purpose and Guidelines | Python.org](https://www.python.org/dev/peps/pep-0001/)
    - Japanese translation by volunteers [Python Enhancement Proposal: 1 - Japanese User Group of Sphinx, a Python documentation builder](http://sphinx-users.jp/articles/pep1.html)
        - Translation as of 2010
    - The PEP mechanism worked well for a long time and was later adopted by other languages such as Erlang.

- How PEP works (roughly)
    - Come up with an idea
    - (Recommended): Discuss within the community.
        - A `python-ideas mailing list` has been prepared in advance as a place to discuss drafts.
    - Create a PEP with 1 idea 1 PEP and submit it in a pre-determined manner
        - At this time, we need to identify individuals (champions) who will write the PEP according to the format, look through the discussions that take place in the appropriate forums, and make an effort to reach consensus in the community on the ideas put forth
        - PEP editors have the right to reject proposals if the focus of the PEP is blurred or too broad
        - A number is assigned when the editor approves.
    - Discussion of the PEP will take place and opinions will be collected.
        - Example: In [PEP 3104](https://www.python.org/dev/peps/pep-3104/) there was a discussion about how to declare variables to be bound to the external scope, and after a wide variety of keywords were proposed, the keyword nonlocal was chosen after a survey of occurrences to find the one that would not break backward compatibility the most. A survey of the number of occurrences was conducted and the keyword nonlocal was chosen
    - When you are ready for a review, get it reviewed by Python author Guido von Rossum.
        - Python is Guido's dictatorship; he decides if it is acceptable or not.
        - When applied to Politech, it is important to know how to connect with the current system.

- Miscellaneous Notes
    - It should be uniquely numbered and can be mentioned in short words such as [RFC 2616](https://tools.ietf.org/html/rfc2616) or [PEP 236](https://www.python.org/dev/peps/pep-0236/).
    - It should be in text or similar easily searchable format
    - Good to be published on the Internet and available for anyone to refer to.
    - Rejected items should also be publicly available. Example: [PEP 245](https://www.python.org/dev/peps/pep-0245/)

    - Awareness of the issue: Regarding the formulation of specifications for orders from government agencies, it is necessary to have dynamics that move in a technologically better direction from the perspective of "avoiding lock-in by specific vendors" and "making it easy to integrate with other systems. An open discussion mechanism is necessary to avoid specifications that are convenient for specific companies.

- relevance
    - [Open System Dependability (OSD) | DEOS Overview | DEOS](http://deos.or.jp/summary/about_osd-j.html)
        - > Structured record and history of consensus building on requirements and realizations throughout the lifecycle
        - [International standard IEC 62853 Open systems dependability, by project leader Prof. Yoshiki Kinoshita (Department of Information Science, Faculty of Science and Programming Science Laboratory) of the University, was published on June 13, 2018! -- Kanagawa University - SankeiBiz](https://www.sankeibiz.jp/business/news/180625/prl1806251514098-n1.htm)
            - > "International Standard IEC 62853 Guidance for the total dependability of open systems" was published on June 13, 2018.
            - > IEC 62853 provides guidance for the overall dependability of open systems. Traditionally, the correct implementation of system specifications has been considered the basis for total reliability. IEC 62853 is a groundbreaking international standard that places the basis for total reliability on accountability and implementation.

---
This page is auto-translated from [/nishio/Politech Enhancement Proposal](https://scrapbox.io/nishio/Politech Enhancement Proposal) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
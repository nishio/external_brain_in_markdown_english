---
title: "ontology diagram"
---

- After discussing with [[Kenji Hiranabe]] about trying [Word frequency in source code
- I calculated the frequency by including all calls, not just the definitions, but some said I should limit it to just the definitions, which do you think is better?
    - It seems like a good idea to analyze not only the function and class definitions, but also the calls
    - It's the ones that appear more frequently, including the calls, that are the most important concepts.
- I've divided the addItem-like methods into add and item and tabulated them, what do you think?
    - Separated items are closer to "[[Domain Words]]".
- What do you think? I think we should analyze everything together, not only classes and methods, but also comments and CSS.
    - should do so
    - Analyze everything people see and everything that describes the program
- supplement
    - It is a process of "retrieval" and "meaning making."
        - Extract "strings that seem to correspond to important concepts" and verbalize their meanings.
    - What is depicted here is a diagram of the relationships between concepts, an "ontology diagram" if you will.
    - The goal is not to draw a diagram, but to arrive at the current situation, a little divergent.
- consideration
    - Age of aggregation by dividing method names into words, data on which method the word came from is available for correspondence.
        - The item is listed in the ranking, and from there the link is "List of identifiers that use this word: addItem, removeItem".
        - And while we're at it, it would be nice if we could jump to the code from that list of identifiers.
        - Could this be accomplished as a vscode extension?
    - I feel that a "dictionary" describing the meaning of words should be easily looked up while writing a program.
        - Manage with source code?
        - For example, you could write it in a fixed format in the root directory of the project.

relevance
    - [[Dictionary creation assistance]]
---
This page is auto-translated from [/nishio/オントロジー図](https://scrapbox.io/nishio/オントロジー図) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
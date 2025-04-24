---
title: "Annotation of range"
---

    - What should be the [[annotation]] of [[Scope.]] in [[corpus]]?
- For example, in [[book corpus]], "This range is source code."
- Proposal to include specific (unlikely to appear) characters before and after the range.
        - [[Private Use Domain]] and so on.
    - Need tools to make it easier for humans to input data.
        - I like the idea of range selection and one click or shortcut.
    - Cannot be read directly by the human eye
- Insert a specific string before or after the range
    - `<span class='code'>...</span>`
    - It's good because it can be removed with a regular HTML parser.
    - It is also possible to extract only the annotated range with a normal HTML parser.
    - Somewhat redundant.
    - I think this is the right thing to do.
    - Related [microformat - Wikipedia [https://ja.wikipedia.org/wiki/%E3%83%9E%E3%82%A4%E3%82%AF%E3%83%AD%E3%83%95%E3%82%A9%E3%83%BC%E3%83%9E%E3%](https://ja.wikipedia.org/wiki/%E3%83%9E%E3%82%A4%E3%82%AF%E3%83%AD%E3%83%95%E3%82%A9%E3%83%BC%E3%83%9E%E3%) 83%83%E3%83%88] [[microformat]].

---
This page is auto-translated from [/nishio/範囲のアノテーション](https://scrapbox.io/nishio/範囲のアノテーション) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
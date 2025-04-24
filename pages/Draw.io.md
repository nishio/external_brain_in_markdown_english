---
title: "Draw.io"
---

[I heard Draw.io is now available in VSCode! #VSCode - Qiita](https://qiita.com/riku-shiru/items/5ab7c5aecdfea323ec4e)
- [[Illustrative Tools]]
[[vscode]]

[[Using Markdown](https://otepipi.hatenablog.com/entry/2020/05/25/192844) Editing SVG files of Markdown documents in real time with Draw.io Visual Studio Code - System and Modeling]
This article explains how to use the Draw.io Integration, a Visual Studio Code extension, to edit SVG files in a Markdown file in real time. The main points can be summarized as follows
1. install the Visual Studio Code extension "Draw.io Integration
2. create a new SVG file with extension `.drawio.svg` in any directory
3. the Draw.io edit screen will open, so use the GUI to draw a shape
4. create a Markdown file in the same directory and insert the SVG file you just created in the format `! [](filename.drawio.svg)` format.
5. confirm that the inserted SVG image is displayed in the Markdown preview
6. when you edit and save an SVG file on Draw.io's edit screen, the Markdown preview is updated in real time

The Draw.io Integration extension also supports Mermaid.js, which introduces the advantage of being able to display Mermaid diagrams in Markdown viewers that do not normally support Mermaid notation.

The article provides useful information for Visual Studio Code users.
---
This page is auto-translated from [/nishio/Draw.io](https://scrapbox.io/nishio/Draw.io) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
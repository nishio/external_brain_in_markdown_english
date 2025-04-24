---
title: "Morphological analysis maintaining Scrapbox notation"
---

2022-04-07
![image](https://gyazo.com/05d8ee0d4c4a5f47ace96e804e2cb77a/thumb/1000)
- Use [mecab does not split part of the input
- However, in the case of Scrapbox, there are multiple notations to be protected, so it is difficult to do the pre-processing with regular expression replacements
- This time, I decided to use [[scrapbox-parser]] in [[Deno]] only for the preprocessing part.
ts

```typescript
data.pages.forEach((page: ScrapboxPage) => {
  const text = page.lines.map((line: ScrapboxLine) => line.text).join("\n");
  const blocks = parse(text);
  const mecab = [] as string[];
  blocks.forEach((block) => {
    if (block.type === "line") {
      const indent = " ".repeat(block.indent);
      mecab.push(`[${indent}]\tSCRAPBOX_INDENT`);

      let trailing_space = "";
      block.nodes.forEach((node) => {
        if (node.type === "plain") {
          const m = node.text.match(/(.*?)(\s*)$/);
          mecab.push(m![1]);
          trailing_space = m![2];
        } else if (node.type === "link" || node.type === "icon") {
          const tag = node.type === "link" ? "SCRAPBOX_LINK" : "SCRAPBOX_ICON";
          mecab.push(`${trailing_space}${node.raw}\t${tag}`);
          trailing_space = "";
        }
      });
      mecab.push("[NEWLINE]\tNEWLINE");
    }
  });
  page.mecab = mecab.join("\n");
});
```



---
old version
ts

```typescript
const blocks = parse(text);

const mecab = [] as string[];
blocks.forEach((block) => {
  if (block.type === "line") {
    const indent = " ".repeat(block.indent);
    mecab.push(`[${indent}]\tSCRAPBOX_INDENT`);
    block.nodes.forEach((node) => {
      console.log(node);
      if (node.type === "plain") {
        mecab.push(node.text);
      } else if (node.type === "link") {
        mecab.push(`${node.raw}\tSCRAPBOX_LINK`);
      } else if (node.type === "icon") {
        mecab.push(`${node.raw}\tSCRAPBOX_ICON`);
      }
    });
    mecab.push("[NEWLINE]\tNEWLINE");
  }
});
```


- error `tokenizer.cpp(368) [new_node->feature]`
- Due to downstream MeCab specifications, text immediately preceding link or icon notation must not end in whitespace.
    - [mecab constrained parsing (partial parsing) errors - aayletric](https://eieito.hatenablog.com/entry/2021/09/24/090000)
        - > This error occurs only when a single-byte space immediately precedes a constrained text string.
    - We'll add that whitespace to the notation side this time, since we can't restore it if we simply delete it.
---
This page is auto-translated from [/nishio/Scrapboxの記法を維持して形態素解析](https://scrapbox.io/nishio/Scrapboxの記法を維持して形態素解析) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
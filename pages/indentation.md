---
title: "indentation"
---

![image](https://gyazo.com/8c97e243a80186b66c0bb08263b2232c/thumb/1000)

---
from [[settings]]
indentation
[/villagepump/indent to show vertical lines](https://scrapbox.io/villagepump/indent to show vertical lines).
![image](https://gyazo.com/975c7f58f27e392f359772089398418d/thumb/1000)
style.css_deprecated

```
.app:not(.presentation) .indent-mark .char-index:not(:nth-last-child(1)):not(:nth-last-child(2)) {
 	position: relative;
 }
.app:not(.presentation) .indent-mark .char-index:not(:nth-last-child(1)):not(:nth-last-child(2))::before {
	content: " ";
	position: absolute;
	left: 50%;
	margin: -12px -1.6px;
}
.app:not(.presentation) .indent-mark .char-index:nth-child(2n+1)::before {
	border-left: 2px solid #eee; /* specify color */
}
.app:not(.presentation) .indent-mark .char-index:nth-child(2n+2)::before {
	border-left: 2px solid #ddd;
}
```

---
- Is that the kind of thing that breaks off on a line that becomes multiple lines? Or am I using it wrong?
    - ![image](https://gyazo.com/e6cb1570eb0f813b67ceea1270bb0f7d/thumb/1000)
    - Oh, that's what you mean by "When I put in automatic line breaks or vertical lengthening notation (image embedding, etc.), the lines were broken, so I made a method that did not use `::before`<img src='https://scrapbox.io/api/pages/villagepump/Mijinko_SD/icon' alt='/villagepump/Mijinko_SD.icon' height="19.5"/>".

new version
style.css

```
 .indent-mark {
 	height: 100% !important;
 }
 .indent-mark .pad {
 	height: 100% !important;
 	overflow: unset !important;
 }
 .indent-mark span:nth-child(2n+2) .pad {
 	background: #f8f8f8;
 }
```



a
- b
    - c
        - d
            - f
                - g
                    - h
                        - i

![image](https://gyazo.com/8c97e243a80186b66c0bb08263b2232c/thumb/1000)
seemingly good

---
This page is auto-translated from [/nishio/インデント表示](https://scrapbox.io/nishio/インデント表示) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
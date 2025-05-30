---
title: "Examples of Bad Know-How"
---

In IE6-11 CSS
- Only in IE6, an underscore in front of a property name is considered identical.
- Only in IE6 and 7 is an asterisk in front of the property name considered identical.
- IE6-10, adding \9 at the end of the value does not affect the value.
- In IE6-8, :not(:target){ ~ } is not interpreted
- In IE6-9, @media all and (-ms-high-contrast: none) { ~ } is not interpreted
Change CSS depending on browser version by combining
- [Try this hack for each version of IE | cly7796.net](http://cly7796.net/wp/css/hack-of-each-version-of-internet-explorer/)
css

```
.sample {
    background: #000000;
    background: #888888\9;
    *background: #777777;
    _background: #666666;
}
.sample:not(:target) {
  background: #999999\9;
}
@media all and (-ms-high-contrast: none) {
    .sample:not(:target) {
        background: #bbbbbb;
        background: #aaaaaa\9;
    }
}
```

- This should change the behavior in each of 6-11, but I haven't checked because I'm too lazy to verify with old IE.

---
This page is auto-translated from [/nishio/バッドノウハウの具体例](https://scrapbox.io/nishio/バッドノウハウの具体例) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
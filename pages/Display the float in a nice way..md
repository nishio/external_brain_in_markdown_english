---
title: "Display the float in a nice way."
---

[[Unity]]
- I was supposed to be able to use `$"FPS: {frameCount / timeDelta : F1}"`, but Unity is upset because "that feature is not available in C#4.0".
- I had no choice but to convert it using toString.
    - [$ - String Interpolation (C# Reference) | Microsoft Docs](https://docs.microsoft.com/ja-jp/dotnet/csharp/language-reference/tokens/interpolated)
    - [standard numeric format string | Microsoft Docs [https://docs.microsoft.com/ja-jp/dotnet/standard/base-types/standard-numeric-format-strings#](https://docs.microsoft.com/ja-jp/dotnet/standard/base-types/standard-numeric-format-strings#) FFormatString]

JS
- [Number.prototype.toFixed() - JavaScript | MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/toFixed)
---
This page is auto-translated from [/nishio/floatをいい感じに表示する](https://scrapbox.io/nishio/floatをいい感じに表示する) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
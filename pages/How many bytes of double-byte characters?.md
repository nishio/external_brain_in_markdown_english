---
title: "How many bytes of double-byte characters?"
---

👨‍👩‍👦 is a full-width (East Asian Wide) character (user-perceived characters, grapheme clusters) and 24 bytes for UTF-7

> [@kuwaccho0711](https://twitter.com/kuwaccho0711/status/1605408243689623553?s=46&t=5XPcp5O9XCrSUKkLORvGGQ): How many bytes are full-width characters?
> The answer to this question will provide some insight into the type of work the engineer has done in the past.

> [@nishio](https://twitter.com/nishio/status/1605528444795703297?s=20&t=oi37AaY87BoJTMiIAzbuKA): "How many bytes of double-byte characters?" If someone asks you "How many bytes of double-byte characters?" and you answer without checking what those "double-byte characters" are, you're making some kind of unspoken assumption.
> [@nishio](https://twitter.com/nishio/status/1605528899458199552?s=20&t=oi37AaY87BoJTMiIAzbuKA): Of all the definitions that could be said "this is a double-byte character" based on some standard, which one is the most likely to increase the number of bytes? I'm feeling like "I'm not sure which one can increase the number of bytes". I'm feeling like this.
> [@nishio](https://twitter.com/nishio/status/1605529701266509824?s=20&t=oi37AaY87BoJTMiIAzbuKA): well, I guess it would be easier to show that [[combined pictographs]] is a double-byte character I guess it's easier to show that [[combined pictographs]] are double-byte characters...
- ![image](https://gyazo.com/0e6c8d06975b41a46e523853e18ad073/thumb/1000)
    - [Zero-width joiner - Wikipedia](https://en.wikipedia.org/wiki/Zero-width_joiner)
    - I'm talking about connecting the pictograms with ZWJs to make one pictogram, which would be the longest...
    - ZWJ="\xE2\x80\x8D"
python

```
>>> print(b"\xF0\x9F\x91\xA8\xE2\x80\x8D\xF0\x9F\x91\xA9\xE2\x80\x8D\xF0\x9F\x91\xA6".decode("utf-8"))
👨‍👩‍👦
```

    - 18 bytes per character
- > grapheme clusters (“user-perceived characters”) --- [UAX #29: Unicode Text Segmentation](https://unicode.org/reports/tr29/)
    - Use the definition that user-recognized "character" is [[grapheme cluster]].

## [[East Asian width]]
> [@hrjn](https://twitter.com/hrjn/status/1605533390572113920?s=20&t=oi37AaY87BoJTMiIAzbuKA): full-width half-width is no longer a font issue...
> [@hrjn](https://twitter.com/hrjn/status/1605533475490082818?s=20&t=oi37AaY87BoJTMiIAzbuKA): any character can be half-width or full-width
- I think it would be better to use "East Asian width" for the definition of full-width and half-width.
- > [@nishio](https://twitter.com/nishio/status/1605535291141488646?s=20&t=oi37AaY87BoJTMiIAzbuKA): @hrjn >Unicode assigns every code point an "East Asian width" property.

> [@kazuho](https://twitter.com/kazuho/status/1605772081538269184?s=46&t=5XPcp5O9XCrSUKkLORvGGQ): On a very serious note, Unicode has a definition of full-width and half-width characters. In the context of Japanese processing, characters with East_Asian_Width attribute of W or A are full-width.... Wikipedia says so [East Asian character width - Wikipedia](https://ja.wikipedia.org/wiki/東アジアの文字幅).
- > [@kazuho](https://twitter.com/kazuho/status/1605774154644348929?s=20&t=-992ptNNIT8D9zREo7QN8w): f you forgot. This is why people who know as much as they read wikipedia...

How the East Asian Width of the combined pictograms is defined.
- > 5 Recommendations ...
- >  `[UTS51]` emoji presentation sequences behave as though they were East Asian Wide, regardless of their assigned East_Asian_Width property value.
    - [UAX #11: East Asian Width](https://www.unicode.org/reports/tr11/tr11-39.html)

another solution
> [@sakamotoh](https://twitter.com/sakamotoh/status/1605543944955351042?s=20&t=oi37AaY87BoJTMiIAzbuKA): [[surrogate pair (of characters)]] With the "Variant character (IVS) selector", "full-width characters" are 8 bytes.
    - [[variant character selector]]

[[UTF-7]] would be longer."
- Indeed!
python

```
>>> b"\xF0\x9F\x91\xA8\xE2\x80\x8D\xF0\x9F\x91\xA9\xE2\x80\x8D\xF0\x9F\x91\xA6".decode("utf-8").encode("utf-7")
b'+2D3caCAN2D3caSAN2D3cZg-'
```

24bytes

Make it four.
> [@sou7___](https://twitter.com/sou7___/status/1606265691392221184?s=20&t=I6FunGmb-H4mRZ2U5IrNcw): @nishio You can make it longer if you specify 4 skin colors!
> [@nishio](https://twitter.com/nishio/status/1606267624941305858?s=20&t=I6FunGmb-H4mRZ2U5IrNcw): @sou7___ I output a family of 4 to a Mac terminal and one of them ran away from home. I decided not to challenge myself to see how far I could stretch it.
python

```
>>> print(b"\xF0\x9F\x91\xA8\xE2\x80\x8D\xF0\x9F\x91\xA9\xE2\x80\x8D\xF0\x9F\x91\xA6\xE2\x80\x8D\xF0\x9F\x91\xA7".decode("utf-8"))
👨‍👩‍👦‍👧
```

![image](https://gyazo.com/6f6aaf97f14efd7bf902f0e5e46f6f74/thumb/1000)
Well, but he's running away from home, but the cursor moves four people at once, so if you argue that "it may look like two letters, but it's one letter because it's one grapheme cluster..."

python

```
>>> print(b"\xE2\x80\x8D".join([b"\xF0\x9F\x91\xA8", b"\xF0\x9F\x91\xA9"] * 10).decode("utf-8"))
👨‍👩‍👨‍👩‍👨‍👩‍👨‍👩‍👨‍👩‍👨‍👩‍👨‍👩‍👨‍👩‍👨‍👩‍👨‍👩
```

I think you mean this one letter.

---
This page is auto-translated from [/nishio/全角文字は何バイト？](https://scrapbox.io/nishio/全角文字は何バイト？) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
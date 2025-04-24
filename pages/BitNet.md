---
title: "BitNet"
---

2024-02-28
[[1-Bit LLM Impact! 8.9x faster at 70B All inference with addition only!]]

Regarding the feeling that it's been there for a while.
> [goto_yuta_](https://twitter.com/goto_yuta_/status/1762766893990240463) Regarding BitNet b1.58, 1-bit BitNet in the true sense of the word originally existed. I guess "BitNet b1.58" is a variant of BitNet b1.58. I guess that by adding 0 to the parameter that the original 1-bit BitNet had, the resulting average amount of information handled is 1.58, which is called "BitNet b1.58".
- I see.
- > [mr_bay_area](https://twitter.com/mr_bay_area/status/1762767949277155820) I think the 1-bit LLM story happened a long time ago, and I think it was this paper, but I didn't see it cited.
- >  Binarized Neural Networks: Training Deep Neural Networks with...


> [goto_yuta_](https://twitter.com/goto_yuta_/status/1762755172089090537) There's an implementation on Github, and there's an architecture diagram, but it looks like what it's doing is seriously the same, just adding Bit to the Transformer component to make it bit additive. I think it's really the same thing.
>  Why is the accuracy going up...
>  ![image](https://gyazo.com/c5dc75a94a586f2380d18f9ab4593308/thumb/1000)

>  >[goto_yuta_/status/1762753632028807552/photo/1 [https://twitter.com/goto_yuta_/status/1762753632028807552/photo/1/status/](https://twitter.com/goto_yuta_/status/1762753632028807552/photo/1/status/) 1762753632028807552/photo/1] BitNet, announced by Microsoft, is too much, too much to be half-true but too great to be true and too much to be expected.
>  I heard that they make the matrix content 1 bit (0 or 1 only) to speed up the matrix operation by eliminating the need for multiplication.
>
>  I understand the logic behind the speedup, but according to the paper, somehow the accuracy is also improved.
>  Too much work to do, so we'll see how it goes.


---
This page is auto-translated from [/nishio/BitNet](https://scrapbox.io/nishio/BitNet) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
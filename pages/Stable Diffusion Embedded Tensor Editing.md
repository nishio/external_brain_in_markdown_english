---
title: "Stable Diffusion Embedded Tensor Editing"
---

![image](https://gyazo.com/d2fccb42c4aed55486e8f02e613aaec0/thumb/1000)
- The image at the top center of this page is the image generated when "cat" is entered.
    - The bottom center is the image generated when the word "kitten" is entered.
- If you take this as a "word," it's a skipped value, but it actually corresponds to a vector of 768 dimensions.
    - then we can mix those vectors.

[https://scrapbox.io/files/63365812630afe001deea2b0.mov](https://scrapbox.io/files/63365812630afe001deea2b0.mov)
- 400 divisions between cat kitten and video at 20 frames per second.
- There is a period of about 4 seconds when it is difficult to tell what has changed, and then the screen suddenly flops back and forth.
- Some parts change smoothly, some parts change violently, which means that the mapping from the space of the prompt to the space of the image is not so smooth
    - Not much control works with this, if you change it this way, will it do this? and tinkering with it will result in unpredictable movement when it enters the realm of a rustling storm.

- Add "tabby" (tiger cat) to "cat" and the pattern became darker and darker, and when I subtracted it, it became a white cat.
    - ![image](https://gyazo.com/3d5701e780e44d9294af65226e00e117/thumb/1000)
    - There are areas that can be interpreted in this way that make sense.
    - On the other hand, if you subtract tabby from kitten, you get a monster. On the other hand, unpredictable phenomena like "kitten minus tabby
        - ![image](https://gyazo.com/53bad72c88c5d308ae9c5e56dd0f5586/thumb/1000)
    - Image of a yacht that is controllable on calm seas but gets messed up when a storm comes in.

--- log
> [@nishio](https://twitter.com/nishio/status/1570329982844698625?s=20&t=gkBdZ3SIHmjj7Wer9WDyOA): instead of a human writing the prompt in a string in Stable Diffusion directly edit the vector in which it is embedded. It's more expressive than strings. It is possible to specify something like "a cat that is a little more than a tiger cat and half a kitten.
> ![image](https://pbs.twimg.com/media/FcruvumacAE1QHu.jpg)
- I misspelled "vector" and actually wrote [[Stable Diffusion's prompt will be a 77 x 768 dimensional tensor]].
    - There is an article that thinks it is a "vector" in word2vec understanding, which I also misunderstood, but if you check it properly, you will see that it is not true.
    - If the "prompt is one word" as in this example, the result will be the same even if you assume the tensor is a vector and process it.
- > [@nishio](https://twitter.com/nishio/status/1570331819740123136): center top row is normal "cat", bottom row is "kitten", right end is +3/7 tabby. minus tabby makes the pattern disappear. The left half is an area not covered by existing words, so there is less data, and the odd shape is created in the lower left corner, where the amount of editing is the largest.

> [@nishio](https://twitter.com/nishio/status/1570336104678838274): "a drawing of *"
> ![image](https://pbs.twimg.com/media/Fcr0SvZaMAEkVE_.jpg)
- Only certain words in a sentence can be edited.
- If you "process as a vector" in a multi-word prompt like this, the first "a" vector is edited, so it's not good.
- The above example includes the BOS token and edits only the 4th vector at 0 origin
    - In this experiment, the index is specified by hand, but you can also use the tokenizer in [[CLIP]] to specify and edit tokens in a way that is easy for humans to understand.

Aside [[NSFW filter behavior for Stable Diffusion]].

2022-09-29
> [@nishio](https://twitter.com/nishio/status/1575474901779357703): I used Stable Diffusion tensor editing to split the cat and kitten into a hundred segments and put them together into a 5 second movie at 20FPS. I didn't crossfade between frames, so you can directly observe what kind of output you get.
>  [https://scrapbox.io/files/633591af63315f001d639b71.mov](https://scrapbox.io/files/633591af63315f001d639b71.mov)

> 4 times more accurate decomposition (400 divisions between CAT and KITTEN)
>  I don't know if you can see it on Twitter without problems.
>  [https://scrapbox.io/files/63365812630afe001deea2b0.mov](https://scrapbox.io/files/63365812630afe001deea2b0.mov)
> There is a period of about 4 seconds when it is difficult to tell what has changed, and then the screen suddenly switches to a flurry of images.
>  Actually, even areas that appear to be unchanged can be shown to be changing if you jump or something with the seek bar. In other words, the difference is whether the change is occurring in a human-perceivable place.
>  There is a single whisker flicker at around 10 seconds. This is a subtle change in value that is flickering because it is just on the edge of the boundary between drawing a mustache and not. It happened to be a flicker so humans noticed it right away, but if it were a smooth change, most people wouldn't notice it.
>  The output image changes significantly despite the fact that the input prompt is smoothly changed by 400 times finer control of the vector that humans represent by the messy means of words. This is because the mapping is not smooth. The control seems to work in calm zones in places, but there are stormy zones in between.

relevance
> [@sugyan](https://twitter.com/sugyan/status/1566801639717056512): morphing with stablediffusion: Kyoto <-> Tokyo
- ![image](https://gyazo.com/9c0b6c3ed0c5280ef54b29673887643b/thumb/1000)![image](https://gyazo.com/f27e9d79538d7942eb2a66d41c051d8a/thumb/1000)

[Stable Diffusion prompts to add and subtract meaning](https://zenn.dev/td2sk/articles/eb772103a3a8ff)


---
This page is auto-translated from [/nishio/Stable Diffusion埋め込みテンソル編集](https://scrapbox.io/nishio/Stable Diffusion埋め込みテンソル編集) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
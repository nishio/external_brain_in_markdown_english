---
title: "split"
---

![image](https://gyazo.com/ca518f0eb596de0dab29478bfea4d52a/thumb/1000)
[https://twitter.com/wonderful_panda/status/1406850885171380225](https://twitter.com/wonderful_panda/status/1406850885171380225)

> @koizuka
> If you only follow the specification "return the result of splitting a given string with a comma in an array", it can't be 0, can it? There would be one more additional specification with conditions such as an empty string.
[https://twitter.com/koizuka/status/1407234519065776128](https://twitter.com/koizuka/status/1407234519065776128)
- Me too.

> @mattn_jp
> I have looked into it a bit and found that JS/Python/Go/C# is 1 and Ruby/Perl is 0, so it seems that opinions differ depending on the programming language you are using.

Why does Ruby have such specifications?
- Seems to implicitly remove the trailing empty element.
Ruby.rb

```
> "a,".split(",")
=> ["a"]
> ",a".split(",")
=> ["", "a"]
```

- Well, that's a certain kind of rationale.

> [@kinaba](https://twitter.com/kinaba/status/1407392725448544260?s=20)
>  `"".split(',')` is a favorite of `[]`, but again I wonder why, I guess I'm in the same mood that I naturally accept the notation that `[1,2]` is a two-element list and `[1]` is a single element and `[]` is an empty list. And I'd like you to take the minimum when there are multiple candidates because "a list that returns when joined and does not contain `','` in any element" is a request when I'm in a declarative mood.
>
>   @nishio
>  "1," is it like you want it to be 1 element?
>
>  @kinaba
>  I feel like I want this to be 2 elements because I want the join to go back to the original. (In relation to the first half of my statement, I have a feeling that common language specifications that make `[1,2,3,]` a 3-element list are very unnatural, but are forced to be this way for convenience.)
- I thought it was the same as Ruby, but it wasn't.
- I want you to get back on track with the JOIN" is the priority.

Which means there are at least three models so far.
:
|  | "" | "a" | "a," | "a,b" |
| -- | -- | -- | -- | -- | -- |
| (A) | 1 | 1 | 2 | 2 | Python |
| (B) | 0 | 1 | 2 | 2 | kinaba |
| (C) | 0 | 1 | 1 | 2 | Ruby |

---
This page is auto-translated from [/nishio/split](https://scrapbox.io/nishio/split) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "Estimated number of tokens 2024-05-17"
---

2024-05-17
:

```
num book 336
num page 98526
num char 63668699
num token gpt4o 46738772
num token gpt4 62413985
```


gpt4 : gpt4o = 1.34 : 1
char : gpt4o = 1.36 : 1

The Intellectual Production of Engineers in one book.
:

```
num page 273
num char 249144
num token gpt4o 178800
num token gpt4 236547
```


tokenizer
py

```
gpt4o = tiktoken.encoding_for_model("gpt-4o")  # <Encoding 'o200k_base'>
gpt4 = tiktoken.encoding_for_model("gpt-4")  # <Encoding 'cl100k_base'>
```


text-embedding-3-small is cl100k_base, 336 books, 98526 pages with 62M tokens, now $0.02 / 1M tokens so $1.25
On 2023-03-24 in [Story study session about connecting my Scrapbox to ChatGPT.
> 17,229,603 tokens for this Scrapbox.
>  Embedding API costs $0.4 / 1M Token
>  That means about $7.
>  $0.13 with embedded "technology behind the coding" in its entirety
>  (Amazing that this Scrapbox is for 54 books...)
In a little over a year, the cost of the Embedding API has dropped to 1/20th of the cost of a book.

price
| gpt-4o | $5.00 / 1M tokens | $15.00 / 1M tokens |
| -- | -- | -- |
| gpt-3.5-turbo-0125 | $0.50 / 1M tokens | $1.50 / 1M tokens |

This Scrapbox is 17M tokens(cl100k), 13M tokens(o200k), so $8.5 for GPT3.5 to read, $65 for GPT4o.


---
This page is auto-translated from [/nishio/トークン数見積り2024-05-17](https://scrapbox.io/nishio/トークン数見積り2024-05-17) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
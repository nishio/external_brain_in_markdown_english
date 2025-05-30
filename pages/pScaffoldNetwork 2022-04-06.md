---
title: "pScaffoldNetwork 2022-04-06"
---

[[pScaffoldNetwork]]
Creating a [[Scaffolding Network]] from a book, done.
- If the page does not have a title, such as in a book, it would be more interesting to put the page for eliminating notational quirks on top, rather than the content page on top.
    - ![image](https://gyazo.com/3433781e56ea22b09dc6c192aa7c685b/thumb/1000)
    - ![image](https://gyazo.com/716235f54a965d1ef2914dd1c5e98051/thumb/1000)

:

```
:len(docs) 223
:all body length 144072
:average body length 646.0627802690583
convert to tokens 0.416135923
 construct SA 0.12402529000000001
height_to_group 0.09916798400000015
filter groups 0.020757480999999967
:len(list(groups)) 2004
calc score / per page grouping 0.0030685299999999582
select good links 0.021269355000000045
:len(selected_links 987
generate variant pages / make links 0.019899406999999814
output 0.031460328999999954
python3 scaffold_network.py  1.13s user 0.10s system 97% cpu 1.260 total
```


With 140,000 characters (223 documents, average 646 characters) as input, it takes about 0.6 seconds for morphological analysis and suffix array creation.
Pick up all ambiguous substrings between documents, discard those that appear only in one document, and extract 2000 candidate links, here in 0.1 second.
Score the link candidates and group them by page to select the top few and make it about 1,000, here in 0.02 seconds.
0.05 seconds to generate JSON for Scrapbox

I've broken it down into small steps, but on this scale, it's blazing fast, and it only takes 1.1 seconds all in.

:

```
:len(docs) 425
:all body length 311207
:average body length 732.2517647058824
convert to tokens 1.441826367
 construct SA 0.325575006
height_to_group 0.17009132000000005
filter groups 0.10468057400000008
:len(list(groups)) 6197
calc score / per page grouping 0.011452530000000127
select good links 0.057980431000000276
:len(selected_links 2032
generate variant pages / make links 0.05053440300000034
output 0.0688222439999997
python3 scaffold_network.py  2.96s user 0.26s system 90% cpu 3.575 total
```


A little more than twice the size of the input takes a little more than twice as long, 3 seconds.
It's the pre-processing part that's eating time, the core part is still about 0.1 second.

:

```
:len(docs) 983
:all body length 698607
:average body length 710.6887080366225
convert to tokens 2.6240625730000002
 construct SA 0.7093633160000001
height_to_group 0.5530669490000006
filter groups 0.2120671629999995
:len(list(groups)) 13209
calc score / per page grouping 0.0323648960000007
select good links 0.14454357399999918
:len(selected_links 4751
generate variant pages / make links 0.1216121930000007
output 0.16785022500000046
python3 scaffold_network.py  6.59s user 0.53s system 93% cpu 7.605 total
```


And doubled again, but about twice the time, about linear.
The coefficients of the nonlinear part are small and unnoticeable.
700 words and 1000 documents in 7 seconds, so realistic.
---
This page is auto-translated from [/nishio/pScaffoldNetwork 2022-04-06](https://scrapbox.io/nishio/pScaffoldNetwork 2022-04-06) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
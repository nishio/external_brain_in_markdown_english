---
title: "words.npz"
---

format note
python

```
>>> x = np.load("words.npz")
>>> x['words']
array([2201,   13,   54, ...,   12,    3, 2201])
>>> len(x['words'])
84035
>>> x['count']
array([['、', '3894'],
       ['of', '3781'],,
       ['is', '3368'],.
       ...,
       ['rooted', '1'],.
       ['prayer', '1'],.
       ['fun', '1']], dtype='<U23')
>>> x['w2i'].item()['Nishio'] # w2i is a dictionary
2166
>>> x['i2w'][2166]  # i2w is an array of string
>>> x['words'][100:200]
array([  29,   11,   56,    8,    5,  918,  116,   15,    6,  918, 1765,
         32,   28,    3, 1279,    2,  121,    9,    7,   22,    0,  231,
        121,    9,   11,    1,    8,    5,  383,    5,  122,    8, 3009,
         32,   28,    3,   54,    1,  918,  116,   15,    6,   76,  384,
          4, 1147,   11,   45,    6, 1762,   14,    3,   13,  156,    0,
       2203,  133,   45,    6,   21,   28,   14,    3,   55,   20,   76,
        384,   77, 1476, 1766,   19,   65,  275,    1,  158,  919,  165,
         44,  215,   14,    6,    0,   43,    5, 2204,    1,   45,   14,
          3,  191,   37,   18,  232,    5,  146,  156,  621,  665,   14,
          6])
>>> i2w[_]

       'n', '.' 
       'ta', 'no', 'de', 'ha', 'all', 'ha', 'read', 'de', 'get', 'no', 'no', '. ,
       'I', 'of', 'tell', 'want', 'thing', 'is', '1', 'volume', 'to', 'put together', 'put together', 'book', 'book'
       'but', 'want', 'is', '.' , '\004', 'but', ',', 'just', 'good', 'book', 'is', '.
       'no', 'no', 'is', '.' , 'what', 'or', '1', 'book', 'only', 'o', 'recommend', 'do', 'to', 'to', 'to', 'to', 'to', 'to', 'to', 'to', 'to', 'to', 'to', 'to', 'to', 'to'
       
       'this', 'is', '1966', 'of', 'book', 'is', '. ', 'abstract', 'mental', 'idea', 'idea', 'idea', 'idea', 'idea', 'idea', 'idea', 'idea', 'idea', 'idea', 'idea', 'idea'
       'is', 'now', 'but', 'enough', 'valid', 'is', 'but'], dtype='<U23')
```




---
This page is auto-translated from [/nishio/words.npz](https://scrapbox.io/nishio/words.npz) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
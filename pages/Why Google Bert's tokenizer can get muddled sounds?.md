---
title: "Why Google Bert's tokenizer can get muddled sounds?"
---

If you enter the string "model" for example in Google Bert's tokenizer, the muddled sound is removed and the string becomes "motel".
This is the function below that is intended to remove accents, since all those in the category `Mn` (Mark, nonspacing) are discarded, but turbid signs, etc. are also included in this genre.
python

```
  def _run_strip_accents(self, text):
    """Strips accents from a piece of text."""
    text = unicodedata.normalize("NFD", text)
    output = []
    for char in text:
      cat = unicodedata.category(char)
      if cat == "Mn":
        continue
      output.append(char)
    return "".join(output)
```


python

```
>>> chars = list(unicodedata.normalize("NFD", "model"))
>>> chars
['mo', 'te', '゙', 'le'].
>>> [unicodedata.category(c) for c in chars]
>>> ['Lo', 'Lo', 'Mn', 'Lo']
```



---
This page is auto-translated from [/nishio/Google Bertのtokenizerで濁音が取れる理由](https://scrapbox.io/nishio/Google Bertのtokenizerで濁音が取れる理由) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "NSJSONSerialization"
---

:

```
    NSString* jsonPath = @"/Users/nishio/Dropbox/lacaille.json";
    NSData *data = [NSData dataWithContentsOfFile:jsonPath]; 
    NSError *error = nil;
    id json = [NSJSONSerialization JSONObjectWithData:data
                                              options:kNilOptions
                                                error:&error];
```


![image](https://gyazo.com/2e10fc31dfcbda29626d139d326dd975/thumb/1000)

[[ObjectiveC]]
[[JSON]]

---
This page is auto-translated from [/nishio/NSJSONSerialization](https://scrapbox.io/nishio/NSJSONSerialization) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
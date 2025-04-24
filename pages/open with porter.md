---
title: "open with porter"
---

Switch from Safari to Porter from the Scrapbox page in [/porterapp/Safari](https://scrapbox.io/porterapp/Safari).
from the Page Menu

![image](https://gyazo.com/d4c84afa1b488a1b4766ae6aa1295a9f/thumb/1000)

script.js

```javascript
const onClick = () => {
  location.href = location.href.replace('https','sbporter');
};

scrapbox.PageMenu.addMenu({
  title: "Porter",
  image: "https://gyazo.com/d4c84afa1b488a1b4766ae6aa1295a9f/raw",
  onClick,
});
```



---
This page is auto-translated from [/nishio/open with porter](https://scrapbox.io/nishio/open with porter) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "iPad may ignore focus"
---

from [[pRegroup-done-2019]]
iPad may ignore focus
- BUG: When adding a sticky, the focus is on the text area on the PC version, but not on the iPad for some reason.
    - I'm doing textarea.focus() in useEffect.
- [I looked into the strange focus() on Mobile Safari on iOS - mixi engineer blog](https://alpha.mixi.co.jp/entry/2012/10807/)
- [iPhone's Safari does not give focus to the input field | GWT Center](https://www.gwtcenter.com/iphone-safari-doesnt-get-focus)
- Well, if focus is not heard except when called directly from within an event handler, then there is nothing we can do in this case, where the state is updated in the event handler and React sees the state update and removes the display:none.
- Touchstart on buttons to display & focus directly instead of letting React do it
- →done

---
This page is auto-translated from [/nishio/iPadはfocusを無視することがある](https://scrapbox.io/nishio/iPadはfocusを無視することがある) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
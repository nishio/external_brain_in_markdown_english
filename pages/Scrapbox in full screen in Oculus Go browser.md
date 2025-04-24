---
title: "Scrapbox in full screen in Oculus Go browser"
---

![image](https://gyazo.com/cc5ddd452d0bb457c94b1a47a6e40111/thumb/1000)
[video](https://www.facebook.com/nishiohirokazu/videos/10215545450485911/?notif_id=1528744657189025&notif_t=feedback_reaction_generic) [Discussion in share at](https://www.facebook.com/ohkubo.kohei/posts/10155752048016476) Summary: [/nishio/want-big-walls](https://scrapbox.io/nishio/want-big-walls)

- [[Scrapbox]] in Oculus browser [[full screen display]]
- This is about the size of the full screen.
    - I really want to place it around [[Spherical 180 degree]].
- Scrapbox itself does not have a way to make it full screen without transitioning to presentation mode, so make it full screen with JS.
    - [[webkitRequestFullscreen]] [https://developer.mozilla.org/en-US/docs/Web/API/Fullscreen_API](https://developer.mozilla.org/en-US/docs/Web/API/Fullscreen_API)
- For some reason, scrolling on the touchpad doesn't work.
script.js

```javascript
 var elm=document.createElement('span');
 elm.append("ZoomOut")
 elm.onclick = ()=>{
   		document.getElementsByClassName("page-list")[0].setAttribute('style', 'zoom: 0.5')
     	document.getElementsByTagName('body')[0].webkitRequestFullscreen()
 }
 document.getElementsByClassName("search-form")[0].parentElement.append(elm) 
```


Sequel [[View Scrapbox in WebVR]].

---
This page is auto-translated from [/nishio/ScrapboxをOculus Goのブラウザで全画面表示](https://scrapbox.io/nishio/ScrapboxをOculus Goのブラウザで全画面表示) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
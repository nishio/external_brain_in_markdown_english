---
title: "Kozaneba Development Diary 2021-09-28"
---

![image](https://gyazo.com/75a5ad73d5d4b768de7bf1f3ea7864c2/thumb/1000)

![image](https://gyazo.com/770e188862ebe1db8ceacb691a973eaf/thumb/1000)
![image](https://gyazo.com/f95bb0b29f554dc5cff8f50562c26e67/thumb/1000)

![image](https://gyazo.com/6171788291508fb9b50ad32b72b1e284/thumb/1000)

![image](https://gyazo.com/586064921a9b07e9ebd8774370bc7bb9/thumb/1000)

FAQ
- Q: Wheel zooms in and out too quickly
- A:
    - The wheel and touchpad have different appropriate sensitivities, and Kozaneba is set by default for the touchpad.
    - It would be best if it could detect when a user is using the wheel and switch, but I am not sure how.
    - This identification function is named `kozaneba.is_touchpad` and is customizable, so if you are interested, please experiment with it.
    - If you are not interested in the identification method, and you are fine with the judgment that it is always "not a touchpad" because you use a wheel, you can use `kozaneba.is_touchpad = () => false;`.
    - UserScript Dialog
        - ![image](https://gyazo.com/f6f57a933c79715b1b2a9e0fb5d2f3d1/thumb/1000)
        - It can be opened from `EDIT USERSCRIPT` in the User dialog.
        - ![image](https://gyazo.com/c4d9aa3f9f1fe65c031038cb8d3553ae/thumb/1000)


2021-09-28
- The arrow addition menu is now an image, making it easier to visualize what will happen.
    - ![image](https://gyazo.com/5b240c04a1f83c891eba3a279609964b/thumb/1000)
    - 2021-09-16, "Add the ability to pull arrows together in a user script."
    - On 2021-09-17, "Added to the menu because of the frequency of use of the double-headed arrows," and "Also, the menu for adding arrows up to now clearly states that the right one is the head."
    - These three have been transformed into a menu of images.

next  [[Kozaneba Development Diary 2021-10-01]]

---
This page is auto-translated from [/nishio/Kozaneba開発日記2021-09-28](https://scrapbox.io/nishio/Kozaneba開発日記2021-09-28) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
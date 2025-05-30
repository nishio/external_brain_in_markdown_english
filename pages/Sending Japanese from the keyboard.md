---
title: "Sending Japanese from the keyboard"
---

Reprinted in part from an email I sent.

ErgoDox EZ uses a microcontroller board called Teensy, which you can buy for 3000 yen.
[https://www.switch-science.com/catalog/2447/](https://www.switch-science.com/catalog/2447/)
The microcontroller on board was an AVR.
The schematics are publicly available.
[https://github.com/ErgoDox-EZ/docs](https://github.com/ErgoDox-EZ/docs)
Firmware is also available to the public,
Rewriting keymaps, for example, is a mechanism for users to update the farm.
I'm trying it on Linux, but in the form of writing in C and building with gcc-avr.

Since the keyboard sends Keycode to the OS
Japanese characters and Unicoode pictograms cannot be sent directly.
The string you want to enter is also in Japanese.
There are people who are challenging this matter in the form of "I want to make a key to enter emoji
[http://qiita.com/miyaoka/items/969864e5219349f01be3](http://qiita.com/miyaoka/items/969864e5219349f01be3)
In Windows, you can either tweak the registry to turn on direct Unicode input
Install WinCompose, a software for Unicode direct input,
WinCompose was recommended.
The tricky way to do it is if you have a limited number of things you want to input.
It was also possible to register it in the kana-kanji conversion dictionary.

I have tried to use WinCompose to type Japanese characters in succession.
I am troubled by the disgusting phenomenon that if you put a space in between, it succeeds, but if you cut it out, it fails.
[https://github.com/nishio/qmk_firmware/commit/71ebd6ee60779dc0506e1857ccd980e5b5a2f90c](https://github.com/nishio/qmk_firmware/commit/71ebd6ee60779dc0506e1857ccd980e5b5a2f90c)

I will let you know if I learn anything.

-----

I guess I didn't get the message, so I'll add this.
Existing open source farms can be used up to the point where they behave as keyboards.
The microcontroller board that this farm runs on can speak I2C.
The BLE is a microcontroller that can talk BLE, so if you connect it to a microcontroller that can talk BLE separately via I2C and write a little relay code, you can achieve what you are looking for.
This was the intention.

Q: Isn't it possible to achieve this without modifying the host in IME's code input mode?

Yes, and Ergodox has also mentioned this as a way to achieve this,
They recommend WinCompose for compatibility reasons.
So I have not verified this, but depending on the OS version, the IME code input mode may not work.

---
This page is auto-translated from [/nishio/キーボードからの日本語送信](https://scrapbox.io/nishio/キーボードからの日本語送信) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
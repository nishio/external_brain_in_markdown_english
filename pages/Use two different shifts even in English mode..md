---
title: "Use two different shifts even in English mode."
---

2020-01-13
- [[I want to type round brackets and braces at home position.]]
I tried to [[Lacaille Modification]] that it should be possible to use two types of shift in English mode.
![image](https://gyazo.com/5fb2cac4c146c50f115310af63f1a413/thumb/1000)



[step1](https://github.com/nishio/Lacaille/commit/9481e93d71480a1fb1534da7d7e33299e35baef9)
- At any rate, I was able to modify Lacaille to change characters with two different thumb shifts in non-kana input mode (although now I get braces no matter which shift I use on any key).
- The next step is to figure out how to specify the keymap I want to do.
- One problem: if the space key first time disable is on, it is inconvenient to have to press it twice for space, which is frequently used in programs and commands.

[step2](https://github.com/nishio/Lacaille/commit/0b898f8585bd9e16f1d0a948075b9c473716b56f)
- In English mode, I could go so far as to press q on the right thumb shift to get Q, and on the left thumb shift to get 1, with each key producing a letter on two different shifts.
    - However, when we try to use this in actual operation, it conflicts with orz in Karabiner, so we need to stop doing it in Karabiner and change it to orz in Lacaille alone.
    - Note that we do not plan to do a binary release of this version because you cannot change the keymap without compiling it yourself.
- The Mac key code, why the sequence asdfhgzx, is a mystery to me, but I guess it's just something I have to think about because of the historical background.

[step3](https://github.com/nishio/Lacaille/commit/0b898f8585bd9e16f1d0a948075b9c473716b56f)
    - [[Lacaille stand-alone thumb shift]] Got it.
- The goal is to write an explanatory article using this
- Up to step2, it was flick input, but from here, Lacaille alone thumb shift
- Glad to see Scrapbox brackets are easier to type (shift left of v).
- Lacaille stand-alone thumb shift can be achieved without rewriting the program.
    - ![image](https://gyazo.com/dead818f34f8b832ecd1249e838e7b07/thumb/1000)
    - I thought about doing it this way, but it was weird to have part of the keymap in source code and part in GUI settings (saved in plist), so I decided to make it all in source code.
        - So the above GUI is currently just a decoration.

Explanation of the mechanism
- Lacaille does various cases in a function called keyUpDownEventCallback, which is a little more than 300 lines long.
- Branching by kana mode or not is also done here.
- This time, I modified it so that it judges "simultaneous pressing of two shifts" in English mode as well as Kana mode.
- There are many branches to determine simultaneous presses, but finally read getKeyDataForOya(keycode, gOya) in [timerFired to get the key after conversion [https://github.com/nishio/Lacaille/commit/9481e](https://github.com/nishio/Lacaille/commit/9481e) 93d71480a1fb1534da7d7e33299e35baef9#diff-79d99ad47582971be0987cf69f1b8a68L1561-R1587]
    - I put a branch here depending on whether it is kana mode or not.
- The keymap is [hardcoded in an array of 3 bytes per key [https://github.com/nishio/Lacaille/commit/cc7e2b19097f839892e497deaf3420de882f2061#diff-79d99ad47582971](https://github.com/nishio/Lacaille/commit/cc7e2b19097f839892e497deaf3420de882f2061#diff-79d99ad47582971) be0987cf69f1b8a68R1494]
    - So you can't send more than 4 bytes.
- These 3 bytes are not an ASCII string, but a sequence of keycode
    - It's too hard for a human to edit directly, so I created a script to generate it.

I want to do in the future
- Direct bracket input even in Kana mode] in (alphanumeric)(open square brackets)(Kana)
- If we could remove the 3-byte limit, we could do a lot of interesting things.
        - [[I want to input Unicode symbols.]]
    - direct hexadecimal input
- Keymap to JSON
    - [https://dev.classmethod.jp/smartphone/parse-json-without-library/](https://dev.classmethod.jp/smartphone/parse-json-without-library/)

old
![image](https://gyazo.com/645f9e0ce5ffb33e0bdf243f3edfbe2b/thumb/1000)
- Failing to map the inequality sign.


:

```
[[" !1", " \"2", " #3", " $4", " %5", "   ", " &6", " '7", " (8", " )9", " 00", " =-", " ~^"], ["1Qq", "2Ww", "3Ee", "4Rr", "5Tt", "|&!", "6Yy", "7Uu", "8Ii", "9Oo", "0Pp", " `@"], ["\u00a5Aa", "/Ss", "=Dd", "{Ff", "}Gg", " _-", "(Hh", ")Jj", "\u2423Kk", "\"Ll", " +;", " *:"], ["?Zz", "+Xx", "-Cc", "[Vv", "]Bb", "^$@", "*Nn", "_Mm", " <,", " >.", "#?/"]]
```

[[keylayout]]

---
This page is auto-translated from [/nishio/英字モードでもシフト2種類使う](https://scrapbox.io/nishio/英字モードでもシフト2種類使う) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
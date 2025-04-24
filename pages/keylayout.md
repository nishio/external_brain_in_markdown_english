---
title: "keylayout"
---

- An application that nicely displays a keyboard layout with two different shifts, such as [[thumb shift]].
![image](https://gyazo.com/2470327d9b76bf315d2b9da536fd5073/thumb/1000)
[https://nishio.github.io/keylayout/build/](https://nishio.github.io/keylayout/build/)
Source code is here
[https://github.com/nishio/keylayout/blob/master/src/App.tsx](https://github.com/nishio/keylayout/blob/master/src/App.tsx)

2021-06-18
- New repository.
- How to deploy
- Github Pages for past

2021-06-11
- Problem: When there is an error in the input layout data, the screen does not update and the service appears to be not working.
    - At a minimum, error messages should be displayed in the event of an error
    - It's hard to show where you're wrong, but I can give you "how far you're right".
- The fix was easy, but the build doesn't work.
    - `$ npm run build`
:

```
Could not find a required file.
	Name: index.js
```


2020-01-17 Made `"egaka"` and `["e", "ga", "ka"]` acceptable.
:

```
"🤔".length
2
```

- to display characters that are considered two characters, such as
        - [[🤔Key]]


:

```
[["?  shi", "nade", "jugeke", "mozese", "", "bamiha", "dooto", "ginoiki", "pyoi", "", ":"], ["ü ne", "ubihi", "rozusu", "yabufu", "Ibehe", "", "punume", "zoyuso", "pemu", "piwa." , " ", "o-"]]
```


---
This page is auto-translated from [/nishio/keylayout](https://scrapbox.io/nishio/keylayout) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
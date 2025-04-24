---
title: "Pasta Logic vs."
---

:

```
3:3 [>Bug][AddFlag][Subroutine][MoveFlag][Increment]

-----put flags-----

3:3 [>Bug][AddFlag][Subroutine][MoveFlag o][Increment]

3:3 [>Bug (x)][AddFlag][Subroutine][MoveFlag o][Increment]

3:3 [>Bug (x)o][AddFlag][Subroutine][MoveFlag o][Increment]

3:3 [>Bug (x)o][AddFlag x][Subroutine][MoveFlag o][Increment]

3:3 [>Bug (x)o][AddFlag xo][Subroutine][MoveFlag o][Increment]

3:3 [>Bug (x)o][AddFlag xo][Subroutine][MoveFlag o][Increment x]

-----run program-----

3:3 [>Bug (x)o][AddFlag xo][Subroutine][MoveFlag o][Increment x]

play by x

2:3 [>Bug (x)o][AddFlag xo][Subroutine][MoveFlag o][Increment x]

vvvvvvvvvv

2:3 [>Bug x(o)][AddFlag xo][Subroutine][MoveFlag o][Increment x]

play by o

2:2 [>Bug x(o)][AddFlag xo][Subroutine][MoveFlag o][Increment x]

vvvvvvvvvv

2:2 [Bug xo][>AddFlag (x)o][Subroutine][MoveFlag o][Increment x]

play by x

2:2 [Bug xox][>AddFlag (x)o][Subroutine][MoveFlag o][Increment x]

vvvvvvvvvv

2:2 [Bug xox][>AddFlag x(o)][Subroutine][MoveFlag o][Increment x]

play by o

2:2 [Bug xox][>AddFlag x(o)][Subroutine][MoveFlag oo][Increment x]

vvvvvvvvvv

2:2 [Bug xox][AddFlag xo][Subroutine][>MoveFlag (o)o][Increment x]

play by o

2:2 [Bug ox][AddFlag xo][Subroutine][>MoveFlag (o)o][Increment xx]

vvvvvvvvvv

2:2 [Bug ox][AddFlag xo][Subroutine][>MoveFlag o(o)][Increment xx]

play by o

2:2 [Bug oxo][AddFlag x][Subroutine][>MoveFlag o(o)][Increment xx]

vvvvvvvvvv

2:2 [Bug oxo][AddFlag x][Subroutine][MoveFlag oo][>Increment (x)x]

```



---
This page is auto-translated from [/nishio/パスタロジック対戦記](https://scrapbox.io/nishio/パスタロジック対戦記) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
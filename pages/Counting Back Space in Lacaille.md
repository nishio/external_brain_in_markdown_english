---
title: "Counting Back Space in Lacaille"
---

The mod to show the number of backspace times probably now works properly.
This is the display after typing the above sentence
![image](https://gyazo.com/bd74ca145d3ffd15754d6104f4c39128/thumb/1000)
The display is updated when the settings screen is opened.
Reset values by restarting the application.
Maybe a reset button could be added.

![image](https://gyazo.com/0c419ab35bc7bee38bd5edbaa3a22e98/thumb/1000)
Too many corrections.

I've added a reset button so you can see the measurement results only during the example practice.
![image](https://gyazo.com/acd0f75cc65d1b7782977cc8350a8814/thumb/1000)
Release [https://github.com/nishio/Lacaille/releases/tag/v2](https://github.com/nishio/Lacaille/releases/tag/v2)

-----memo

In the meantime, I was able to modify the [[Lacaille]] source so that the backspace count is accumulated and debugged output, but where should I display it?

objc

```
bool isCtrlH = (
    CGEventGetIntegerValueField(event, kCGKeyboardEventKeycode) == 4 &&
    CGEventGetFlags(event) == 0x40101);
bool isBackSpace = (
    CGEventGetIntegerValueField(event, kCGKeyboardEventKeycode) == 51 &&
    CGEventGetFlags(event) == 0x100);

if (type != kCGEventKeyDown && (isCtrlH || isBackSpace)){
    backSpaceCount++;
    debugOut(@"[BackSpace] %d\n", backSpaceCount);
}
```


---
objc

```
static CGEventRef keyUpDownEventCallback(CGEventTapProxy proxy, CGEventType type, CGEventRef event, void *refcon)
```


objc

```
    debugOut(@"[EV] Keycode=%d, Flags=<%llx>, Type=%d, gTargetPid=%d\n",
             (CGKeyCode)CGEventGetIntegerValueField(event, kCGKeyboardEventKeycode),	(CGEventFlags)CGEventGetFlags(event), type, gTargetPid);
```


ctrl H

```
[EV] Keycode=4, Flags=<40101>, Type=10, gTargetPid=9953
[RetP] Type=10 Keycode=4

[EV] Keycode=51, Flags=<100>, Type=10, gTargetPid=9953
[RetP] Type=10 Keycode=51
```


---
This page is auto-translated from [/nishio/Lacailleでバックスペースをカウント](https://scrapbox.io/nishio/Lacailleでバックスペースをカウント) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
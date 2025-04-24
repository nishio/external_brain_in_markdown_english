---
title: "Set up Thinklet"
---


from [[THINKLET]]
Set up Thinklet
[[LINKLET]]

2024-12-13
[Take a video clip | THINKLET App Developer](https://fairydevicesrd.github.io/thinklet.app.developer/docs/startGuide/useCamera)
:

```
 % scrcpy
scrcpy 3.0.2 <https://github.com/Genymobile/scrcpy>
* daemon not running; starting now at tcp:5037
* daemon started successfully
ERROR: Could not find any ADB device
ERROR: Server connection failed
```

forgetting to turn on the power
:

```
% scrcpy
scrcpy 3.0.2 <https://github.com/Genymobile/scrcpy>
INFO: ADB device found:
INFO:     -->   (usb)  P16M116D5252823                 device  THINKLET_LC01
/opt/homebrew/Cellar/scrcpy/3.0.2/share/scrcpy/scrcpy-server: 1 file pushed, 0 skipped. 6.1 MB/s (90396 bytes in 0.014s)
[server] INFO: Device: [QUALCOMM] FD THINKLET LC01 (Android 8.1.0)
[server] WARN: Audio disabled: it is not supported before Android 11
INFO: Renderer: metal
WARN: Demuxer 'audio': stream explicitly disabled by the device
INFO: Texture: 1080x1920
2024-12-13 21:41:52.149 scrcpy[57506:30128462] +[IMKClient subclass]: chose IMKClient_Modern
2024-12-13 21:41:52.149 scrcpy[57506:30128462] +[IMKInputSession subclass]: chose IMKInputSession_Modern
```


- I happened to see the chat application in the background.
    - Well, it's not a clean read, but it's a resolution that shows what kind of project and what kind of channels.


[Let's make a recording application | THINKLET App Developer](https://fairydevicesrd.github.io/thinklet.app.developer/docs/startGuide/buildRecord)

[Android Studio
- [Download Android Studio and App Tools - Android Developers | Android Developers [https://developer.android.com/studio?gad_source=1&gclid=Cj0KCQiA0--6](https://developer.android.com/studio?gad_source=1&gclid=Cj0KCQiA0--6) BhCBARIsADYqyL9cEDzcMG1XZUsilfZUySjdIpoL6qHqs7yxl-kde66B9Cs3_s0EjlwaAjGkEALw_wcB&gclsrc=aw.ds&hl=en]

sample code
[FairyDevicesRD/thinklet.app.developer](https://github.com/FairyDevicesRD/thinklet.app.developer/tree/main)

> Run debugging from Android Studio and install this app in THINKLET.
> However, when debugging for the first time, we have not implemented Permission to allow it, so it just launches an app that can't do anything.
I ran debugging build.gradle and nothing happened? I thought it was the application that started and terminated, but I can't do anything about it?
> 23:12:29: Executing...
> 23:12:30: Execution finished.

<img src='https://scrapbox.io/api/pages/nishio-en/o1 Pro/icon' alt='o1 Pro.icon' height="19.5"/>Running "build.gradle" does not install the application; you must actually build the application and install it on the device (THINKLET) by pressing the "Run" (or "Debug") button from the top toolbar of Android Studio.
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>The "Run" (or "Debug") button, grayed out.
<img src='https://scrapbox.io/api/pages/nishio-en/o1 Pro/icon' alt='o1 Pro.icon' height="19.5"/>Lack of proper Run Configuration
Select "Edit Configurations..." from the top toolbar. from the top toolbar and check if there is a Run Configuration for the "app" module. If not, create a new one.
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
>  Select "Edit Configurations..." from the top toolbar. from the top toolbar and check if there is a Run Configuration for the "app" module. If not, create a new one.
How do you do it?
<img src='https://scrapbox.io/api/pages/nishio-en/o1 Pro/icon' alt='o1 Pro.icon' height="19.5"/>
From the top bar of the Android Studio menu, open "Run" -> "Edit Configurations..." from the top bar of the Android Studio menu.
Click the "+ (plus button)" in the upper left corner of the dialog that appears.
Select "Android App" (or "Android Application") from the list.
Select the "app" module of your project in the "Module" field.
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
> Select the "app" module for your project in the "Module" field.
I can't choose.
<img src='https://scrapbox.io/api/pages/nishio-en/o1 Pro/icon' alt='o1 Pro.icon' height="19.5"/>Possible reasons for not being able to select the "app" module include
Individual files and subfolders are open, not the project root directory
Please "Open" the root directory of the entire cloned GitHub project (the directory where settings.gradle is located) in Android Studio.

I was able to do it!
![image](https://gyazo.com/a66536f17227cff98750a2900af35028/thumb/1000)
I'm an amateur Android developer, so I opened the project the wrong way. w

I was even able to record it.

[edit key config | THINKLET App Developer](https://fairydevicesrd.github.io/thinklet.app.developer/docs/startGuide/buildKeyConfig)
`% adb shell am start -n com.example.fd.camera/com.example.fd.camera.MainActivity`
Starting: Intent { cmp=com.example.fd.camera/.MainActivity }

Key configurations were also made!
- Now you can start recording without a PC.

next:
    - [[Putting a life logging app in the LINKLET]]
---
This page is auto-translated from [/nishio/Thinkletをセットアップ](https://scrapbox.io/nishio/Thinkletをセットアップ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
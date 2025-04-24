---
title: "Putting a life logging app in the LINKLET"
---

![image](https://gyazo.com/6357de17b18027861f8c2373fdea8fbb/thumb/1000)Thumbnail

from  [[Set up Thinklet]]
Putting a life logging app in the LINKLET
---
2025-03-05
[FairyDevicesRD/thinklet.app.lifelog: THINKLET Lifelog App](https://github.com/FairyDevicesRD/thinklet.app.lifelog)

![image](https://gyazo.com/d5ef7d577255907bce3ff715364a13e9/thumb/1000)
once through

> Could not GET '[https://maven.pkg.github.com/FairyDevicesRD/thinklet.app.sdk/ai/fd/thinklet/sdk-audio/0.1.6/sdk-audio-0.1.6.pom'.](https://maven.pkg.github.com/FairyDevicesRD/thinklet.app.sdk/ai/fd/thinklet/sdk-audio/0.1.6/sdk-audio-0.1.6.pom'.) Received status code 401 from server: Unauthorized
<img src='https://scrapbox.io/api/pages/nishio-en/o3-mini-high/icon' alt='o3-mini-high.icon' height="19.5"/>
This error is caused by missing credentials when retrieving the library from GitHub Packages. Please follow the steps below to address this issue.
Creating a GitHub Personal Access Token
- Create a new token on GitHub under "Settings" -> "Developer settings" -> "Personal access tokens".
- Be sure to grant "read:packages" permission when creating the file.
Add authentication information to local.properties ...

That's the one in the README.

![image](https://gyazo.com/2bc6018940666acaa8c1c3ff63b381f9/thumb/1000)
<img src='https://scrapbox.io/api/pages/nishio-en/o3-mini-high/icon' alt='o3-mini-high.icon' height="19.5"/>
> Please test on a compatible device.
> Check if it is recognized by using the adb devices command.

`% adb devices`
List of devices attached
emulator-5554	device

Oh, just because it's connected and has a red light doesn't mean it's activated, I see.
Started up and went from light blue to green.

`% adb devices`
List of devices attached
P16M116D5252823	device
emulator-5554	device

OK

---
:

```
2025-03-07 13:58:51: Launching app on 'QUALCOMM THINKLET LC01'.
Starting: Intent { act=android.intent.action.MAIN cat=[android.intent.category.LAUNCHER] cmp=ai.fd.thinklet.app.lifelog/.MainActivity }

Open logcat panel for QUALCOMM THINKLET LC01 (P16M116D5252823)
Connected to process 3550 on device 'qualcomm-thinklet_lc01-P16M116D5252823'.
```


It's done.

![image](https://gyazo.com/12f76352976fb62153a2d6d22e321f64/thumb/1000)

Talk about not [[beamforming]] if you're going to pick up the conversation at a social gathering.
- [FairyDevicesRD/thinklet.app.sdk: SDK for THINKLET application](https://github.com/FairyDevicesRD/thinklet.app.sdk?tab=readme-ov-file#%E8%A9%A6%E9%A8%93%E7%9A%84%E6%A9%9F%E8%83%BD-%E9%9F%B3%E5%A3%B0%E5%87%A6%E7%90%86)
- [disable_beamforming.patch](https://gist.github.com/nishio/1295526320d27da8c6aea80d75525f97)
    - [[Fixes you don't understand]]

Nothing was saved at all. I need to set the permissions.
![image](https://gyazo.com/81f992c6b46314ca99c2a3223e98aa3c/thumb/1000)![image](https://gyazo.com/10bd32578804bd182d77e1f90d8bcaef/thumb/1000)

`$ adb shell am start -n ai.fd.thinklet.app.lifelog/.MainActivity --ez enabledMic true`
`$ adb shell ls /sdcard/DCIM/lifelog/19740103/              `
19740103_045124.raw
19740103_045125.gif

<img src='https://scrapbox.io/api/pages/nishio-en/o3-mini-high/icon' alt='o3-mini-high.icon' height="19.5"/>
There are two main transfer methods
- How to use the adb command
    - Execute the following command in a terminal to copy files stored in the specified directory to your PC.
    - `$ adb pull /sdcard/DCIM/lifelog/ [directory path on destination PC].`

- How to use MTP mode
    - Connect the device to USB and switch to "File Transfer (MTP)" mode from the notification area.
    - Access the device's internal storage with PC Explorer (for Windows) or Finder (for Mac) and copy the files in the DCIM/lifelog/ folder.

:

```
% adb shell ls /sdcard/DCIM/lifelog/19740103/              
19740103_045124.raw
19740103_045125.gif
% adb pull /sdcard/DCIM/lifelog/ ~/Downloads 
/sdcard/DCIM/lifelog/: 2 files pulled, 0 skipped. 27.3 MB/s (78614272 bytes in 2.748s)
```


`$ ffmpeg -f s16le -ar 48000 -ac 2 -i ~/Downloads/lifelog/19740103/19740103_045124.raw output.wav `

I'll have to try actually walking and talking with it on.

2025-03-08
- Test operation of [LINKLET
    - I thought maybe I shouldn't muffle it, but surprisingly it's not a problem.
    - ![image](https://gyazo.com/6357de17b18027861f8c2373fdea8fbb/thumb/1000)

:

```
% adb shell ls /sdcard/DCIM/lifelog/19740104
19740104_005846.raw
% adb shell ls /sdcard/DCIM/lifelog/19740103
19740103_045124.raw
19740103_045125.gif
19740103_233158.raw
19740103_233159.gif
```


Hmm? Was this internally dated?
`% adb pull /sdcard/DCIM/lifelog/ ~/Downloads`
About 19 images were taken.
Maybe once every five minutes?

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>How many pictures are taken every minute? Check.
<img src='https://scrapbox.io/api/pages/nishio-en/Roo/icon' alt='Roo.icon' height="19.5"/>To summarize the survey results:
1. default setting: once every 300 seconds (5 minutes)
    - Definition at line 21 of file LifeLogArgs.kt
    - `intervalSeconds = max(bundle?.get("intervalSeconds")?.toString()?.toIntOrNull() ?: 300, 10)`
2. minimum interval: 10 seconds
    - Also in LifeLogArgs.kt, line 21, a minimum value of 10 seconds is set
- Configuration by configuration file:
    - `keyConfigs/2592_1944_withMic.json`: once every 120 seconds (2 minutes)
    - `keyConfigs/1440_1080.json`: once every 30 seconds

Which setting is actually used depends on how the app is launched. If the app is launched using a configuration file, the interval in that configuration file is applied. If the app is launched without a configuration, the default of 300 seconds (5 minutes) is applied.

---

As for the audio, I'll have to take a picture tomorrow.

2025-03-09
:

```
% adb shell ls /sdcard/DCIM/lifelog/19740105/
19740105_033437.gif
19740105_033437.raw
19740105_050124.raw
19740105_062813.raw
19740105_075501.raw
19740105_092149.raw
19740105_104838.raw
```

That's a lot of audio files.
`$ adb pull /sdcard/DCIM/lifelog/ ~/Downloads`
`$ ls -l ~/Downloads/lifelog/19740105`
:

```
total 10122120
-rw-r--r--  1 nishio  staff    11603521  3  9 23:52 19740105_033437.gif
-rw-r--r--  1 nishio  staff  1000000512  3  9 23:51 19740105_033437.raw
-rw-r--r--  1 nishio  staff  1000000512  3  9 23:53 19740105_050124.raw
-rw-r--r--  1 nishio  staff  1000000512  3  9 23:54 19740105_062813.raw
-rw-r--r--  1 nishio  staff  1000000512  3  9 23:52 19740105_075501.raw
-rw-r--r--  1 nishio  staff  1000000512  3  9 23:52 19740105_092149.raw
-rw-r--r--  1 nishio  staff   130837248  3  9 23:53 19740105_104838.raw
```

I see, so the audio file is split at 1GB.
Raw files can be imported with [[Audacity]] or converted with ffmpeg
Let's observe in Audacity
![image](https://gyazo.com/0030b9dad8b2ead55b9b0c8743237664/thumb/1000)

![image](https://gyazo.com/bfc03d2ee156b77269b098a1ade20ab6/thumb/1000)
1 GB for 1.5 hours
120MB for MP3
Throw to [NotebookLM
- small proportion
    - ![image](https://gyazo.com/7afc773fe6d2de8af3911e2f920ab06e/thumb/1000)
    - There are difficulties in transcribing words like "Noda Crystal" and "plurality," but I think it's worthwhile to be able to look back and say, "Yes, that's what we talked about!" but it's worthwhile to be able to look back on what we talked about, since I often talk too much at once at these meetings and my memory overflows!
    - They should be able to dig into just the interesting stories and have them explained.

2025-03-10
![image](https://gyazo.com/5c1db5e609309c0028fcfe7d571658c4/thumb/1000)
- I'll think about it next time I do it.

bash

```
for f in ~/Downloads/lifelog/19740105/*.raw; do
  ffmpeg -f s16le -ar 48000 -ac 2 -i "$f" "${f%.raw}.wav"
done
```


[https://app.devin.ai/sessions/02e8ade3a448425b9c6c178e0db0e236](https://app.devin.ai/sessions/02e8ade3a448425b9c6c178e0db0e236)

2025-03-15
> [nishio](https://x.com/nishio/status/1900559337145213210) I don't have any good pictures, but I was wearing LINKLET, a neck-mounted Android device loaned to me by FairyDevices, at the recent Unexplored Conference Unexplored Night. I left it on for 7.5 hours and it was working fine, capturing audio and images.
>  ![image](https://pbs.twimg.com/media/GmAkIijbsAAjhKz?format=png&name=small#.png)

> [nishio](https://x.com/nishio/status/1900559891317903762) Perspective of the person giving the talk
>  ![image](https://pbs.twimg.com/media/GmAlIeLawAA_R46?format=png&name=medium#.png)

> [nishio](https://x.com/nishio/status/1900560416574672982) Reception
>  @ukkaripon
>  @teramotodaiki
>  ![image](https://pbs.twimg.com/media/GmAlkf6aoAAK__o?format=png&name=medium#.png)

> [nishio](https://x.com/nishio/status/1900562039598456988) It was an after-party, not a reception. I was glad to see many people at the reception, so I could say, "Oh yeah, I talked with Mr. Whatsapp. And unlike a simple lifelog camera, there are 5~6 microphones on the camera, so it's good that you can separate your voice from the other person's voice if you process it afterwards.


---
This page is auto-translated from [/nishio/LINKLETにライフログアプリを入れる](https://scrapbox.io/nishio/LINKLETにライフログアプリを入れる) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
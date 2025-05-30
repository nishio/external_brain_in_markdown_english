---
title: "raspberry (any plant of genus Rubus, esp. Rubus palmatus var. coptophyllus)"
---

[[Builderscon 2018]]
- [https://speakerdeck.com/kazuph/builderscon-tokyo-2018-day1-chan-ye-degatili-yong-sareruraspberry-pifalsehua](https://speakerdeck.com/kazuph/builderscon-tokyo-2018-day1-chan-ye-degatili-yong-sareruraspberry-pifalsehua)
- CI even in embedded systems
    - Push to the repository and Jenkins will create a binary.
    - Raspi direct connection to microcontroller of installed device (JTAG)
    - Raspi writes to microcontroller
        - Jenkins slave running on Raspi
        - There is an ARM binary for J-Link.
        - J-Link has binaries for ARM, so you can write microcontrollers from RasPi.
- Raspi collects logs and throws them over the net.

- For hobby purposes, ESP systems that connect to Wifi are popular, but they eat electricity.
    - I like the BLE microcontroller called nRF52.
- Arduino excels when it comes to servos and sensors
- Flow JSON over serial
    - Arduino library is available.

---
This page is auto-translated from [/nishio/ラズパイ](https://scrapbox.io/nishio/ラズパイ). If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
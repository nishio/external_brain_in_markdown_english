---
title: "Builderscon2018nafuda"
---

![image](https://gyazo.com/66e8059b7562df5f0bc249400e0b9661/thumb/1000)

- [[digital nameplate]] received at [[Builderscon 2018]].
- I don't want to go into detail on the digital nameplate page, so I've split it up.
- [Unusual Efforts in Electronic Name Tag Development or How I Stopped Worrying and Started Making 'Mystery Gadgets' - builderscon::blog](https://blog.builderscon.io/entry/2018/08/09/100000)

2018-09-11
- [electronic_badge_2018/HOW_TO_LOGIN.md at master · builderscon/electronic_badge_2018](https://github.com/builderscon/electronic_badge_2018/blob/master/docs/HOW_TO_LOGIN.md)
- > Login password : It is found in default_passwd.txt in the NAFUDA drive.
    - I'm getting an error message saying default_passwd.txt missing.
- Viewing the three connection methods, select Serial
    - `touch /Volumes/NAFUDA/enable_g_serial`
    - After rebooting, /dev/cu.usbmodem1421 does not appear
- After touch, after visualizing the existence of enable_g_serial in Finder, remove it, power off, reconnect the power supply, and see the following screen
    - ![image](https://gyazo.com/118b34584be90ff796238979b6b81069/thumb/1000)
- Hmm, change to serial mode does not seem to be working properly
- I guess we'll just have to connect UART.
- I tried to generate default_passwd.txt and rebooted it, just to see if it would work.
    - The existence of the password was recognized.
- Once again `touch /Volumes/NAFUDA/enable_g_serial`.
    - Still in g_mass_strage mode
- To be continued at UART.
- feedback
    - > After rebooting, are the enable_g_serial files correctly erased from the NAFUDA drive?
    - >  If the file disappears correctly but is not reflected, try waiting 20 seconds after touch on the Mac before starting the eject operation! We are aware of the phenomenon!
- Try this first next time

What we want to do
- Wait 20 seconds and try eject first
- Login via SSH.
    - Log in with UART
- Install Jenkins
- I want the source code in RasPi to be updated when I push to Github (without having to connect cables and write and stuff).
- fasten a button
- turn on an LED
- Make it a Pomodoro Timer

---
This page is auto-translated from [/nishio/Builderscon2018nafuda](https://scrapbox.io/nishio/Builderscon2018nafuda) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
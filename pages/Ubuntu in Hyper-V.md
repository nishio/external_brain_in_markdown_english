---
title: "Ubuntu in Hyper-V"
---

- Create virtual internal switch
- Designated as guest network device
- This is not enough to SSH the guest, but don't be in a hurry.
- Confirm the reason why SSH is not available to the guest by ipconfig on the host side
- > Autoconfigure IPv4 Address . . . . . . . . : 169.254.53.146
- This is due to the absence of a link-local address, i.e., DHCP
- Multiply Internet connection sharing to virtual internal switches without worrying about
- Now the DHCP server will stand up, the IP will be assigned, and everything will be solved.

- It mysteriously goes wrong during the process, but the saying "Windows, when it goes wrong, reboot" is recited.

---
This page is auto-translated from [/nishio/Hyper-Vの中のUbuntu](https://scrapbox.io/nishio/Hyper-Vの中のUbuntu) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
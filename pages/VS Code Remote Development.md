---
title: "VS Code Remote Development"
---

- [[[Fast Setup]] Using VS Code's Remote Development to Edit Files on an SSH-Connected EC2 ｜ Developers.IO [https://dev.classmethod.jp/etc/vs-code-remote-development-ec](https://dev.classmethod.jp/etc/vs-code-remote-development-ec) 2/?fbclid=IwAR1OFTI57_SSOWQPqMGttmF_FW8cLtq19Y2pC55RizGGGCOwJsqzX3KSGSE]
- It's already available in the regular version.
- Insert Remote Development extension
    - Remote - SSH goes in with it.
![image](https://gyazo.com/6e6b0c72e8b59ad98e7e4d437a476cf4/thumb/1000)

- Check ssh commands
    - `$ ssh -i /Users/nishio/.ssh/***.pem ubuntu@54.**.**.**`
    - Add this to SSH targets (plus button)
        - Written to SSH config file
        - May be edited as needed (gear button)
- Plus window button to connect
    - If you open a terminal with View > Terminal, you can use it like normal SSH.
        - [Integrated Terminal in Visual Studio Code](https://code.visualstudio.com/docs/editor/integrated-terminal)
    - Console can open multiple tabs.
        - But it does not maintain a tmux-like session, so closing this window in VSCode will kill the process.
    - You can specify which directory to open on the remote, maybe home by default.

[[VSCode]] Remote Development

---
This page is auto-translated from [/nishio/VS Code Remote Development](https://scrapbox.io/nishio/VS Code Remote Development) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
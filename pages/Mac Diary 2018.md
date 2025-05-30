---
title: "Mac Diary 2018"
---

2018-08-20
- I'm back to Mac after about 5 years, so notes
- I was relieved that most Unix commands are included, but beware that when you try to use Git, it asks you to install additional commands.
- The default Python included is 2.7 series
- The position that MacPorts used to occupy is now occupied by homebrew.
- I remembered that Cmd+Shift+4 can take a screenshot of a specified range, but it saves the file to the desktop.
    - Adding Ctrl goes directly to the clipboard.
        - → Touch bar to change the destination.
- Live conversion now converts more and more while typing, convenient!
    - However, there are cases where a mistake is made and the momentum is even converted.
    - I have a habit of hitting the space key after typing a paragraph.
    - Hitting the space key when the correct candidate has already been converted by Live Conversion will convert to a different candidate.
    - Up arrow to return
- Ctrl+Space is mapped to input switching in the default key bindings, so I removed it.
    - I had trouble with range selection in Emacs until I noticed this.
    - ![image](https://gyazo.com/ae05eb9f7684209f2feccf568df3d77c/thumb/1000)
- What is the shortcut equivalent to Win+D that displays the desktop?
    - F11 or four-finger diagonal spread gesture
- It seems like they've introduced two different strengths for the touchpad touch, but I'm still getting used to it.
- I'm not sure how it behaves when the window is maximized.
    - Maybe maximizing the window treats it as a virtual desktop.
    - So when hovering over a file on the desktop to the dock icon, it says "no window available".
    - If it's not maximized and just hidden by another window, it will appear properly.

- I memorized "Hey Siri, Remind me tomorrow at 10:00."

- Install Slack
    - I almost accidentally create a new account.
    - If you already have an account, log in
    - Where you designate a workspace, even if you know what you're doing, you say, "I don't know.
    - Enter your email and you will receive a link to a list of workspaces you belong to.

- voiced sound separation problem
    - Probably due to the fact that when I open a PDF in Preview on my Mac and copy and paste it, the Mac does an [[NFD normalization]] that separates the punctuation marks
    - [https://qiita.com/takuyabe/items/ac13aa99306ad69743e7](https://qiita.com/takuyabe/items/ac13aa99306ad69743e7)
        - [[Shortcut key to neologd.normalize]]

    - [[Circle symbol with backslash]]

- The reason brew install doesn't work is because there is a proxy on the company network.

- Didn't Crtl+gesture zoom? I thought so, but it was off by default.
    - ![image](https://gyazo.com/e971cab5ca56daf337d8ea8f8eece026/thumb/1000)

2018-09-13
- I frequently forget to press Ctrl to put screenshots into the clipboard, and there are far more times when I put screenshots into the clipboard than when I save them to a file, so I've replaced the shortcut keys.
    - ![image](https://gyazo.com/aeec2905b44489131f3981957c922c6c/thumb/1000)
    - I thought the behavior used to be "save to file but also go into the clipboard".

- When I try to move between desktops, "Back in browser" is triggered.
    - Uncheck "Trackpad" -> "Other Gestures" -> "Swipe between pages" in System Preferences.
    - ![image](https://gyazo.com/45298fb7840083a70f79d2afcfeee107/thumb/1000)

- [ASCII.jp: Techniques to customize and utilize the Touch Bar on MacBook Pro (1/2)｜Tomonobu Yanagitani's "PC Utilization Techniques You'll Want to Copy"](http://ascii.jp/elem/000/001/459/1459096/)
    - To do or not to do (muddled feeling)

- ESC is moving to the touch bar, weird feeling when copying and pasting in Emacs.
    - Configure Cmd to map to Meta.
    - Some say it's a bad idea to use Emacs.
        - I can't throw it away for when I'm working on the terminal, but I have a theory that you're using Emacs even in cases where you could use a GUI editor.
        - What is a good text editor?
            - (Supplemental 2019) [[Visual Studio Code]].
                - open foo.py" from the terminal opens it as a new tab in the running VSCode

- Turn off automatic quote and line changes.
    - ![image](https://gyazo.com/4295d1ad63ed68a477ac8e89f7ba19fb/thumb/1000)
    - Mystery why it's in the user dictionary tab.

- Discard CapsLock
    - Keyboard→Keyboard→Modifier Keys
    - ![image](https://gyazo.com/4d422ad5d62322bb7bb217f67ef9c6c2/thumb/1000)

- Use C-[ instead of Esc
    - > I recommend TouchBar MBP because it forces you to C-[! I was finally able to correct it.
        - [Why Ctrl-[becomes Esc in terminal apps - Humanity](http://tyru.hatenablog.com/entry/2018/10/04/151740)
    - I completely forgot, yes I did.
    - So the question of whether to map Cmd to Meta was concluded to be C-[.

- Finder Preferences
    - I want to display the extension
    - When searching, I want to search from the current folder, not the entire Mac.
    - ![image](https://gyazo.com/585756a5a9973f06ad404e279757cc5a/thumb/1000)

- Turn off guess candidate conversion
    - ![image](https://gyazo.com/378fdbb3d35ef2aa179b48c9257177d4/thumb/1000)
        - It's inconvenient because of the mysterious conversions that occur.
        - ![image](https://gyazo.com/1ae5159fbdde063217018c716d72a54f/thumb/1000)
        - ![image](https://gyazo.com/1302dd75a128dc08d443407896475b84/thumb/1000)



---
This page is auto-translated from [/nishio/Mac日記2018](https://scrapbox.io/nishio/Mac日記2018) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.